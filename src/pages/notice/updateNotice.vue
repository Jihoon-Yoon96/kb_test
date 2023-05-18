<template>
    <form name="RecruitWrite" id="RecruitWrite" method="post">
        <div class="container">
            <input type="hidden" name="isNewFile" value="">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">수정</h2>

                <div class="recruitWrite">
                    <div class="formWrap">
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="title">제목</label>
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
                                <span>본문</span>
                            </li>
                            <li class="con full">
                                <div class="textArea">
                                    <textarea title="추가 전달내용" placeholder="본문 내용을 입력해주세요." name="applicationCnts" id="applicationCnts" v-model="content"></textarea>
                                    <span class="errMsg">본문 내용을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>

                <div class="btnBottomArea tac">
                    <p href="javascript:save()" id="save" class="btnText recruit" @click="updateNotice()"><span>채용공고 수정 하기</span></p>
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

// 상세내용 가져오기
const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_notice_list/${id}`)
console.log(data)
if(data.value){
    title = data.value.data.title
    content = data.value.data.content
}
else{
    console.log(error)
}

// 수정하기
async function updateNotice(){
    const url: string = `http://125.131.88.58:8055/items/kb_notice_list/${id}`
    const method: string = 'PATCH'
    const body: object = {
        "title": title,
        "content": content,
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
        router.push('/notice')
    }
    else{
        alert('채용공고 수정 실패')
        console.log(error)
    }
}

</script>

<style scoped>

</style>