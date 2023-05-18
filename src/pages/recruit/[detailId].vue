<template>
    <div class="container">
        <form name="formRecruitDetail" id="formRecruitDetail" method="post">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle pcOnly">채용</h2>
                <div class="recruitView">
                    <div class="btnTopArea">
                        <a href="javascript:selectRecruitWrite()" class="btnText recruit"><span>입사지원</span></a>
                    </div>
                    <!--본문-->
                    <ul class="headerArea">
                        <li class="title">{{title}}</li>
                        <span class="date"></span>
                    </ul>
                    <div class="recruitViewContent" v-html="content"></div>
                    <!--본문-->
                </div>
                <div class="btnBottomArea">
                    <nuxt-link to="/recruit" class="btnText yellow"><span>목록</span></nuxt-link>
                </div>
                <!-- 상세 : e -->
            </div>
        </form>
    </div>
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";

const router = useRouter()
const id = router.currentRoute.value.params.detailId // 체용공고 상세 ID

let title: string = ''
let content: string = ''
let recruit_start: string = ''
let recruit_end: string = ''

// 상세 내용 가져오기
const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_announce/${id}`)
console.log(data)
if(data.value){
    title = data.value.data.title
    content = data.value.data.content
    recruit_start = data.value.data.recruit_start
    recruit_end = data.value.data.recruit_end
}

</script>

<style scoped>

</style>