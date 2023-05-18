<template>
    <div class="container">
        <div class="inner" id="contents">
            <!-- 상세 : s -->
            <h2 class="subTopTitle pcOnly">소식</h2>
            <div class="boardViewWrap">
                <!--상단 제목-->
                <div class="titleArea">
                    <div class="flagArea">
                        <div class="flag yellow">{{type === 'notice' ? '공지사항' : (type === 'news' ? '언론보도' : '이벤트')}}</div>
                    </div>
                    <div class="title">{{title}}</div>
                    <div class="date">{{writer}} <br> {{date}}</div>
                </div>
                <!--상단 제목-->
                <!--본문-->
                <div class="pre-wrap boardContent" v-html="content"></div>
                <!--본문-->

            </div>
            <div class="btnBottomArea">
                <nuxt-link to="/notice" class="btnText yellow"><span>목록</span></nuxt-link>
            </div>
            <!-- 상세 : e -->
            <div class="btnTopArea">
                <nuxt-link :to="{path:'/notice/updateNotice',query:{id:id}}" class="btnText recruit" style="margin-right: 10px;"><span>수정</span></nuxt-link>
                <a href="" @click="deleteRecruit()" class="btnText recruit"><span>삭제</span></a>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";
const router = useRouter()
const id = router.currentRoute.value.params.noticeDetailId // 체용공고 상세 ID

let type: string = ''
let title: string = ''
let content: string = ''
let date: string = ''
let writer: string = ''

const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_notice_list/${id}?fields=*.*`)
console.log(data)
if(data.value){
    type = data.value.data.type
    title = data.value.data.title
    content = data.value.data.content
    date = dateFormat(data.value.data.date_created)
    writer = data.value.data.writer?.name

}
else{
    console.log(error)
}

// 날짜 포맷 변경
function dateFormat(date: string){
    let day = new Date(date)
    let formed = `${day.getFullYear()}-${day.getMonth()}-${day.getDate()} ${day.getHours()}:${day.getMinutes()}`
    console.log('date',day.getMonth())
    return formed
}
</script>

<style scoped>

</style>