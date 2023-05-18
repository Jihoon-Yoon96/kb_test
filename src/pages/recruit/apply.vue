<template>
    <form name="RecruitWrite" id="RecruitWrite" method="post">
        <div class="container">
            <input type="hidden" name="isNewFile" value="">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">입사지원</h2>

                <div class="recruitWrite">
                    <div class="formWrap">
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="kind">지원분야</label>
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
                                <label class="required" for="name">성명</label>
                            </li>
                            <li class="con">
                                <div class="input">
                                    <input type="text" id="userNm" name="userNm" v-model="title">
                                    <span class="errMsg">성명을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="hp">휴대폰 번호</label>
                            </li>
                            <li class="con">
                                <div class="input">
                                    <input type="text"  id="hp" name="hp" placeholder="-없이 입력" maxlength="11" v-model="phone">
                                    <span class="errMsg">휴대폰 번호를 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="hp">이메일</label>
                            </li>
                            <li class="con">
                                <div class="input">
                                    <input type="text"  id="email" name="email" placeholder="" maxlength="" v-model="email">
                                    <span class="errMsg">이메일을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <span>추가 전달내용</span>
                            </li>
                            <li class="con full">
                                <div class="textArea">
                                    <textarea title="추가 전달내용" placeholder="100자 이내로 작성해 주세요" name="applicationCnts" id="applicationCnts" v-model="etc"></textarea>
                                    <span class="errMsg">추가 전달내용을 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>

                <div class="agreeBox">
                    <div class="textArea">
                        <div class="title">개인정보 수집이용 동의(필수)</div>
                        <div class="con">
                            1. 개인정보의 수집 및 이용 목적<br>
                            입사 지원자 식별, 본인 확인, 입사 전형 진행(합격여부 확인) 및 문의 등의 원활한 처리
                        </div>
                        <div class="checkbox">
                            <input type="checkbox" id="agree">
                            <label for="agree">동의합니다.</label>
                        </div>
                    </div>
<!--                    <button class="btnText rightArr lyPopOpen" data-popup="#popup_agreement"><span>동의내용보기</span></button>-->
                </div>



                <div class="btnBottomArea tac">
                    <a  class="btnText recruit" @click="sendApply()"><span>입사지원서 보내기</span></a>
                </div>



            </div>
        </div>
    </form>
</template>

<script setup lang="ts">
import {useRouter} from "vue-router";
const router = useRouter()

let type: string = ref('')
let title: string = ref('')
let phone: string = ref('')
let email: string = ref('')
let etc: string = ref('')

let typeValue = ref([
    {lable:'UX/UI 기획', value:'UX/UI'},
    {lable:'모바일 앱 개발(IOS/Android)', value:'mobile dev'},
    {lable:'백엔드 개발', value:'backend dev'},
    {lable:'프론트엔드 개발', value:'frontend dev'},
    {lable:'데이터 엔지니어', value:'data engineer'},
    {lable:'클라우드 엔지니어', value:'cloud enginner'},
])

// 지원서 보내기
async function sendApply(){
    const {data, pending, error, refresh} = await useFetch(
        'http://125.131.88.58:8055/items/kb_apply', {
            method: 'POST',
            body: JSON.stringify({
                type: type.value,
                title: title.value,
                phone: phone.value,
                email: email.value,
                etc: etc.value
            })
        }
    )
    console.log(data)

    if(data.value){
        alert('채용 지원 성공!')
        router.push('/recruit')
    }
    else{
        alert('채용 지원 실패')
        console.log(error)
    }
}

</script>

<style scoped>

</style>