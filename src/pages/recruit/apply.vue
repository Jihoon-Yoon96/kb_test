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
                                    <select class="select" id="kind" name="kind" title="지원분야 선택" required="">
                                        <option value="">선택하세요</option>

                                        <option value="UX/UI 기획">UX/UI 기획</option>

                                        <option value="모바일 앱 개발(IOS/Android)">모바일 앱 개발(IOS/Android)</option>

                                        <option value="백엔드 개발">백엔드 개발</option>

                                        <option value="프론트엔드 개발">프론트엔드 개발</option>

                                        <option value="데이터 엔지니어">데이터 엔지니어</option>

                                        <option value="클라우드 엔지니어">클라우드 엔지니어</option>

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
                                    <input type="text" id="userNm" name="userNm" >
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
                                    <input type="text"  id="hp" name="hp" placeholder="-없이 입력" maxlength="11">
                                    <span class="errMsg">휴대폰 번호를 입력해주세요.</span>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="email1">이메일</label>
                            </li>
                            <li class="con full">
                                <ul class="inputFlex">
                                    <li class="email1">
                                        <div class="input">
                                            <input type="text" id="email1" name="email1">
                                        </div>
                                    </li>
                                    <li class="blank">@</li>
                                    <li class="email2">
                                        <div class="input">
                                            <input type="text" id="email2" name="email2">
                                        </div>
                                    </li>
                                    <li class="email3">
                                        <div class="selectBox">
                                            <select class="select" id="emailSelect" name="emailSelect" title="이메일 선택" required="true">
                                                <option value="">선택하세요</option>
                                                <option value="gmail.com">gmail.com</option>
                                                <option value="hanmail.net">hanmail.net</option>
                                                <option value="hotmail.com">hotmail.com</option>
                                                <option value="lycos.co.kr">lycos.co.kr</option>
                                                <option value="nate.com">nate.com</option>
                                                <option value="naver.com">naver.com</option>
                                                <option value="paran.com">paran.com</option>
                                                <option value="직접입력">직접입력</option>
                                            </select>
                                        </div>
                                    </li>
                                </ul>
                                <span class="errMsg">이메일을 입력하세요</span>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <label class="required" for="file">지원서 첨부</label>
                            </li>
                            <li class="con">
                                <input type="file" name="postFileGrp" id="postFileGrp" onchange="uploadFile(this)" style="display:none"/>
                                <button type="button" id="btn-add" class="btnText black"><span>+ 파일첨부</span></button>
                                <div class="fileArea del">
                                    <div class="fileLink">
                                        <span><b></b></span>
                                        <input type="hidden" name="fileNm" id="fileNm">
                                        <button onclick="removeJobPostFile()" type="button" class="btnDel">삭제</button>
                                    </div>
                                </div>
                            </li>
                        </ul>
                        <ul class="formItem">
                            <li class="title">
                                <span>추가 전달내용</span>
                            </li>
                            <li class="con full">
                                <div class="textArea">
                                    <textarea title="추가 전달내용" placeholder="100자 이내로 작성해 주세요" name="applicationCnts" id="applicationCnts"></textarea>
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
                    <button class="btnText rightArr lyPopOpen" data-popup="#popup_agreement"><span>동의내용보기</span></button>
                </div>



                <div class="btnBottomArea tac">
                    <a href="javascript:save()" id="save" class="btnText recruit"><span>입사지원서 보내기</span></a>
                </div>



            </div>
        </div>
    </form>
</template>

<script>
export default {
    name: "apply"
}
</script>

<style scoped>

</style>