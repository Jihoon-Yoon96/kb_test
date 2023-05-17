<template>
    <div class="container">
        <form name="formFAQList" id="formFAQList" method="post">
            <input name="firstIndex" id="firstIndex" type="hidden"   value="0">
            <input name="pageIndex"  id="pageIndex"  type="hidden"   value="1">
            <input name="pageUnit"   id="pageUnit"   type="hidden"   value="10">
            <input name="inqTpNo"   id="inqTpNo"   type="hidden" >
            <input name="totalCnts"   id="totalCnts"   type="hidden" value="14">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">자주묻는 질문</h2>
                <div class="tabArea">
                    <div class="tabList round">
                        <ul>
                            <li name="inqTpLi" :class="[{'on' : faqType==='all'}]" @click="clickTab('all')"><a href="#" name="faqTab" class="tab" cmCd="" id="inqTpNoAll"><span>전체 (<span id="all_num">{{listOfAll.length}}</span>) </span><span class="blind">선택됨</span></a></li>
                            <li name="inqTpLi"  :class="[{'on' : faqType==='user'}]" @click="clickTab('user')"><a href="#" name="faqTab" cmCd="400003" id="400003"  class="tab"><span>회원(<span id="user_num">{{listOfUser.length}}</span>)</span></a></li>
                            <li name="inqTpLi"  :class="[{'on' : faqType==='app'}]" @click="clickTab('app')"><a href="#" name="faqTab" cmCd="400004" id="400004"  class="tab"><span>앱(<span id="app_num">{{listOfApp.length}}</span>)</span></a></li>
                            <li name="inqTpLi"  :class="[{'on' : faqType==='service'}]" @click="clickTab('service')"><a href="#" name="faqTab" cmCd="400005" id="400005"  class="tab"><span>서비스가입(<span id="service_num">{{listOfService.length}}</span>)</span></a></li>
                        </ul>
                    </div>
                    <div class="tabContArea">
                        <div class="tabCont on">
                            <h4 class="blind">전체 내용</h4>
                            <ul class="faqList">
                                <li v-for="(li, i) in listOfQNA" :key="i" @click="li.open = !li.open">
                                    <!--title-->
                                    <a  :class="['item', {'open' : li.open}]">
                                        <div class="box q">Q</div>
                                        <div class="titleArea">
                                            <span class="kind">{{li.type === 'user' ? '회원' : (li.type === 'app' ? '앱' : (li.type === 'service' ? '서비스가입' : ''))}}</span>
                                            <span class="title">{{li.title}}</span>
                                        </div>
                                    </a>
                                    <!--title-->
                                    <!--content-->
                                    <div class="aContentWrap" :style="{display: `${li.open ? 'block' : 'none'}`}">
                                        <div class="inner">
                                            <div class="box a">A</div>
                                            <div class="aContentArea" v-html="li.content"></div>
                                            <div class="btnTopArea">
                                                <nuxt-link :to="{path:'faq/updateFAQ', query:{id:li.id, type:li.type}}" class="btnText recruit"><span>질문 수정</span></nuxt-link>
                                            </div>
                                            <div class="btnTopArea">
                                                <a :to="{path:'faq/updateFAQ', query:{id:li.id, type:li.type}}" class="btnText recruit" @click="deleteFAQ(li.id, li.type)"><span>질문 삭제</span></a>
                                            </div>
                                        </div>
                                    </div>
                                    <!--content-->
                                </li>

                            </ul>

                            <!--paging-->
<!--                            <div class="paging">-->
<!--                                &lt;!&ndash; 변수 매핑 &ndash;&gt;-->
<!--                                &lt;!&ndash; 이전 버튼 &ndash;&gt;-->
<!--                                <a href="#" class="pagingPrev off">이전페이지</a>-->
<!--                                <ul>-->
<!--                                    <div class="number">-->
<!--                                        <li class="on">-->
<!--                                          <a href="#" >1</a>&#160;-->
<!--                                          <li>-->
<!--                                            <a href="#" onclick="fnPageChange(2); return false;">2</a>&#160;-->
<!--                                          </li>-->
<!--                                        </li>-->
<!--                                    </div>-->
<!--                                </ul>-->
<!--                                &lt;!&ndash; 다음 버튼&ndash;&gt;-->
<!--                                <a href="#" onclick="fnPageChange(2)" class="pagingNext">다음페이지</a>-->
<!--                            </div>-->
                            <!--//paging-->
                        </div><!--tabCont-->
                    </div> <!--tabContArea-->
                </div><!--tabArea-->
                <!-- 상세 : e -->
            </div>
        </form>

        <div class="btnBottomArea tac">
            <nuxt-link to="/faq/createFAQ" class="btnText recruit"><span>자주묻는 질문 추가하기</span></nuxt-link>
        </div>
    </div>
</template>

<script setup lang="ts">
import {useFetch} from "#app";

// 자주묻는 질문 가져오기
const listOfAll = ref([])
const listOfUser = ref([])
const listOfApp = ref([])
const listOfService = ref([])

// 질문가져오기
async function getFAQ(){
    const {data, pending, error, refresh} = await useFetch('http://125.131.88.58:8055/items/kb_faq?fields=lists.item.*')
    console.log(data.value.data[0].lists)
    listOfAll.value = [...data.value.data[0].lists]
    listOfAll.value.forEach(el=>{
        // response 포맷 통일
        Object.assign(el, el.item)
        delete el.item

        // UI용 데이터 추가
        el.open = false

        // type별 데이터 분리
        if(el.type === 'user'){
            listOfUser.value.push(el)
        }
        else if(el.type === 'app'){
            listOfApp.value.push(el)
        }
        else if(el.type === 'service'){
            listOfService.value.push(el)
        }
    })
}
await getFAQ()

console.log(listOfAll)

// 자주묻는 질문 tab 클릭 이벤트
let faqType: string = ref<string>('all')
let listOfQNA = ref([])
listOfQNA.value = listOfAll.value
async function clickTab(type: string) {
    faqType.value = type

    if(type === 'user'){
        listOfQNA.value = listOfUser.value
    }
    else if(type === 'app'){
        listOfQNA.value = listOfApp.value
    }
    else if(type === 'service'){
        listOfQNA.value = listOfService.value
    }
    else if(type === 'all'){
        listOfQNA.value = listOfAll.value
    }

}

// 질문 삭제
async function deleteFAQ(id: number, type:string){
    const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_${type}/${id}`,{
        method: 'DELETE'
    })
    console.log(`data`, data)
    console.log(`error`, error)
    if(data.value === ''){
        alert('질문 삭제 성공!')
        await getFAQ()
        clickTab(faqType.value)
    }
    else{
        alert('질문 삭제 실패')
        console.log(error)
    }
}

onMounted( ()=>{
    // clickTab('all')
})


</script>

<style scoped>

</style>
