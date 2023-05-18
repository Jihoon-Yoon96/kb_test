<template>
    <div class="container">
        <form name="formNoticeList" id="formNoticeList" method="post">
            <input name="firstIndex"  id="firstIndex"   type="hidden"   value="0">
            <input name="pageIndex"   id="pageIndex"    type="hidden"   value="1">
            <input name="pageUnit"    id="pageUnit"     type="hidden"   value="10">
            <input name="ntcNo"       id="ntcNo"        type="hidden" >
            <input name="searchNtcFg" id="searchNtcFg"  type="hidden" >
            <div class="inners" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">소식</h2>
                <div class="tabArea">
                    <div class="tabList round">
                        <ul>
                            <li name="ntcFgLi" :class="[{'on' : noticeType==='all'}]" @click="clickTab('all')"><a href="#" name="ntcFgTab" class="tab" cmCd="" id="ntcFgAll"><span>전체</span></a></li>
                            <li name="ntcFgLi" :class="[{'on' : noticeType==='notice'}]" @click="clickTab('notice')"><a href="#" name="ntcFgTab" class="tab" cmCd="300117" id="300117"><span>공지사항</span></a></li>
                            <li name="ntcFgLi" :class="[{'on' : noticeType==='news'}]" @click="clickTab('news')"><a href="#" name="ntcFgTab" class="tab" cmCd="300118" id="300118"><span>언론보도</span></a></li>
                            <li name="ntcFgLi" :class="[{'on' : noticeType==='event'}]" @click="clickTab('event')"><a href="#" name="ntcFgTab" class="tab" cmCd="300119" id="300119"><span>이벤트</span></a></li>
                        </ul>
                    </div>
                    <div class="tabContArea">
                        <div class="tabCont on" >
                            <h4 class="blind">전체 내용</h4>
                            <div class="thumbnail_ist">
                                <ul>
                                    <li id="" v-for="(li, i) in noticeLists" :key="i">
                                        <nuxt-link :to="{path:`/notice/${li.id}`}" class="item">
                                            <div class="img">
                                                <img :src=li.img alt="" width="180px" v-if="li.thumb">
                                                <img src="@/public/img/noImg.png" alt="" width="180px" v-else>
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">
                                                    <div class="flag red">{{li.type === 'notice' ? '공지사항' : (li.type === 'news' ? '언론보도' : '이벤트')}}</div>
                                                </div>
                                                <div class="title">{{li.title}}</div>
                                                <div id="date" class="date">
                                                    {{li.writer?.name}} <br>
                                                    {{dateFormat(li.date_created)}}
                                                </div>
                                            </div>
                                        </nuxt-link>
                                    </li>
                                </ul>
                            </div>

                            <!--paging-->
                            <div class="paging">
                                <ul>
                                    <div class="number">
                                      <li :class="[{'on' : page === index}]" v-for="index in maxPage"><a href="#" @click="getLists(index)">{{ index }}</a>&#160;</li>
                                    </div>
                                </ul>
                            </div>

                        </div>
                    </div>
                </div>
                <!-- 상세 : e -->
                <div class="btnBottomArea tac">
                    <nuxt-link to="notice/createNotice" class="btnText recruit"><span>등록 하기</span></nuxt-link>
                </div>
            </div>
        </form>
    </div>
</template>

<script setup lang="ts">

let noticeType: string = ref<string>('all')
function clickTab(type: string) {
    noticeType.value = type
}

let noticeLists = ref([])
const limit: number = 9 // 페이지 당 컨텐츠 갯수
let page: number = 1 // 현재 페이지 넘버
let total: number = 0 // 총 컨텐츠 갯수
let maxPage: number = 0 // 최대 페이지

async function getLists(num: number){
    page = num
    const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_notice_list?fields=*.*&meta=*&limit=${limit}&page=${page}`)
    console.log(data)
    if(data.value){
        // 데이터 주입
        noticeLists.value = data.value.data
        noticeLists.value.forEach(el=>{
            if(el.thumb){
                el.img = `http://125.131.88.58:8055/assets/${el.thumb.id}`
            }
        })

        // 페이징 처리
        total = data.value.meta.total_count
        maxPage = total > 9 ? Math.ceil(total/limit) : 1
    }
    else{
        console.log(error)
    }
}


// 날짜 포맷 변경
function dateFormat(date: string){
    let day = new Date(date)
    let formed = `${day.getFullYear()}-${day.getMonth()}-${day.getDate()} ${day.getHours()}:${day.getMinutes()}`
    console.log('date',day.getMonth())
    return formed
}

getLists(1)

</script>

<style scoped>

</style>