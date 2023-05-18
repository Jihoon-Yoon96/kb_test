<template>
    <form name="RecruitWrite" id="RecruitWrite" method="post">
        <div class="container">
            <input type="hidden" name="isNewFile" value="">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">채용공고 수정</h2>

                <div class="recruitWrite">
                    <div class="formWrap">
                        <!--                        <ul class="formItem">-->
                        <!--                            <li class="title">-->
                        <!--                                <label class="required" for="kind">질문 유형</label>-->
                        <!--                            </li>-->
                        <!--                            <li class="con">-->
                        <!--                                <div class="selectBox">-->
                        <!--                                    <select class="select" id="kind" name="kind" title="지원분야 선택" required="" v-model="type">-->
                        <!--                                        <option value="user">회원</option>-->
                        <!--                                        <option value="app">앱</option>-->
                        <!--                                        <option value="service">서비스가입</option>-->
                        <!--                                    </select>-->
                        <!--                                    <span class="errMsg">지원분야를 선택해주세요.</span>-->
                        <!--                                </div>-->
                        <!--                            </li>-->
                        <!--                        </ul>-->
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="title">채용공고 제목</label>
                            </li>
                            <li class="con">
                                <div class="input">
                                    <input type="text" id="userNm" name="userNm" v-model="title">
                                    <span class="errMsg">제목을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <span>채용공고 본문</span>
                            </li>
                            <li class="con full">
                                <div class="textArea">
                                    <textarea title="추가 전달내용" placeholder="본문 내용을 입력해주세요." name="applicationCnts" id="applicationCnts" v-model="content"></textarea>
                                    <span class="errMsg">본문 내용을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="title">채용공고 시작일</label>
                            </li>
                            <li class="con">
                                <div class="input">
                                    <input type="text" id="userNm" name="userNm" placeholder="YYYY-MM-DD" v-model="recruit_start">
                                    <span class="errMsg">제목을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="title">채용공고 종료일</label>
                            </li>
                            <li class="con">
                                <div class="input">
                                    <input type="text" id="userNm" name="userNm" placeholder="YYYY-MM-DD" v-model="recruit_end">
                                    <span class="errMsg">제목을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>


                <div class="btnBottomArea tac">
                    <p href="javascript:save()" id="save" class="btnText recruit" @click="updateRecruit()"><span>채용공고 등록 하기</span></p>
                </div>



            </div>
        </div>
    </form>
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";

const router = useRouter()
const id: string = router.currentRoute.value?.query?.id

let title: string = ref('')
let content: string = ref('')
let recruit_start: string = ref('')
let recruit_end: string = ref('')

// 채용공고 상세내용 가져오기
const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_announce/${id}`)
console.log(data)
if(data.value){

    title = data.value.data.title
    content = data.value.data.content
    recruit_start = data.value.data.recruit_start
    recruit_end = data.value.data.recruit_end
}
else{
    console.log(error)
}

// 수정하기
async function updateRecruit(){
    const url: string = `http://125.131.88.58:8055/items/kb_announce/${id}`
    const method: string = 'PATCH'
    const body: object = {
        "title": title,
        "content": content,
        "recruit_start": recruit_start,
        "recruit_end": recruit_end
    }

    const {data, pending, error, refresh} = await useFetch(
        url,{
            method: method,
            body: JSON.stringify(body)
        }
    )
    console.log(data)
    if(data.value){
        alert('채용공고 수정 완료!')
        router.push('/recruit')
    }
    else{
        alert('채용공고 수정 실패')
        console.log(error)
    }
}

</script>

<style scoped>

</style>