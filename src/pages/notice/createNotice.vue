<template>
    <form name="RecruitWrite" id="RecruitWrite" method="post">
        <div class="container">
            <input type="hidden" name="isNewFile" value="">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">등록</h2>

                <div class="recruitWrite">
                    <div class="formWrap">
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="kind">소식 유형</label>
                            </li>
                            <li class="con">
                                <div class="selectBox">
                                    <select class="select" id="kind" name="kind" title="지원분야 선택" required="" v-model="type">
                                        <option v-for="(type, i) in typeValue" :key="i" :value=type.value>{{type.lable}}</option>
                                    </select>
                                    <span class="errMsg">지원분야를 선택해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="title"> 제목</label>
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
                                <span> 본문</span>
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
                    <p href="javascript:save()" id="save" class="btnText recruit" @click="createRecruit()"><span> 등록 하기</span></p>
                </div>



            </div>
        </div>
    </form>
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";

const router = useRouter()

let type: string = ref('notice')
let title: string = ref('')
let content: string = ref('')

let typeValue = ref([
    {lable:'공지사항', value:'notice'},
    {lable:'언론보도', value:'news'},
    {lable:'이벤트', value:'event'},
])
async function createRecruit(){
    const url: string = 'http://125.131.88.58:8055/items/kb_notice_list'
    const method: string = 'POST'
    const body: object = {
        type: type.value,
        title: title.value,
        content: content.value,
    }

    const {data, pending, error, refresh} = await useFetch(
        url,{
            method: method,
            body: JSON.stringify(body)
        }
    )
    console.log(data)
    if(data.value){
        alert('등록 완료!')
        // router.push(router.options.history.state.back)
        router.push('/notice')
    }
    else{
        alert('등록 실패')
        console.log(error)
    }
}

</script>

<style scoped>

</style>