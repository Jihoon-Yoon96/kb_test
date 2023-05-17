<template>
    <form name="RecruitWrite" id="RecruitWrite" method="post">
        <div class="container">
            <input type="hidden" name="isNewFile" value="">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">자주묻는질문 수정</h2>

                <div class="recruitWrite">
                    <div class="formWrap">
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="kind">질문 유형</label>
                            </li>
                            <li class="con">
                                <div class="selectBox">
                                    <select class="select" id="kind" name="kind" title="지원분야 선택" required="" v-model="type">
                                        <option :value=type>{{type === 'user' ? '회원' : (type === 'app' ? '앱' : '서비스가입')}}</option>
                                    </select>
                                    <span class="errMsg">지원분야를 선택해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="title">질문 제목</label>
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
                                <span>질문 답변</span>
                            </li>
                            <li class="con full">
                                <div class="textArea">
                                    <textarea title="추가 전달내용" placeholder="질문 답변 내용을 입력해주세요." name="applicationCnts" id="applicationCnts" v-model="content"></textarea>
                                    <span class="errMsg">질문 답변 내용을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>


                <div class="btnBottomArea tac">
                    <p class="btnText recruit" @click="updateFAQ()"><span>질문 수정 하기</span></p>
                </div>



            </div>
        </div>
    </form>
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";

const router = useRouter()
const id: string = router.currentRoute.value?.query?.id
const type: string = router.currentRoute.value?.query?.type


// let type: string = ref('user')
let title: string = ref('')
let content: string = ref('')

// 질문 가져오기
const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_${type}/${id}`)
console.log(data)
if(data.value){
    title.value = data.value.data.title
    content.value = data.value.data.content
}

// 질문 수정
async function updateFAQ(){
    const url: string = `http://125.131.88.58:8055/items/kb_${type}/${id}`
    const method: string = 'PATCH'
    const body: object = {
        "title": title.value,
        "content": content.value
    }
    debugger

    const {data, pending, error, refresh} = await useFetch(
        url,{
            method: method,
            body: JSON.stringify(body)
        }
    )
    console.log(data)
    if(data.value){
        alert('질문 수정 완료!')
        // router.push(router.options.history.state.back)
        router.push('/faq')
    }
    else{
        alert('질문 수정 실패')
        console.log(error)
    }
}

</script>

<style scoped>

</style>