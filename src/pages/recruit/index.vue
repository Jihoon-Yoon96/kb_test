<template>
    <div class="container">
        <form name="formRecruitLists" id="formRecruitLists" method="post">
            <input name="firstIndex" id="firstIndex" type="hidden"   value="0">
            <input name="pageIndex"  id="pageIndex"  type="hidden"   value="1">
            <input type="hidden" name="postNo" id="postNo">
            <div class="inner" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">채용</h2>
                <!-- 2212 배너 추가 -->
                <div class="recruitBanner">
                    <div class="hbox jc">
                        <!-- 이미지 갯수별로 꽉 차게 나오게 됩니다. div class="flex" 를 같이 반복 해주세요 // 웹 1개 이상 모두 출력, 모바일 1번 이미지만 출력 / 높이값 300px - 중간, 중간 꽉 채우기 기준 -->
                        <div class="flex">
                            <img src="@/public/img/img-recruit-1.png">
                        </div>
                        <div class="flex">
                            <img src="@/public/img/img-recruit-2.png">
                        </div>
                        <div class="flex">
                            <img src="@/public/img/img-recruit-3.png">
                        </div>
                        <div class="flex">
                            <img src="@/public/img/img-recruit-4.png">
                        </div>
                    </div>
                </div>
                <!-- //2212 배너 추가 -->
                <div class="recruitList">
                    <div class="btnTopArea">
                        <nuxt-link to="/recruit/apply"  class="btnText recruit"><span>입사지원</span></nuxt-link>
                    </div>
                    <ul class="headerArea">
                        <li class="title">채용공고명</li>
                        <li class="date">채용일정</li>
                    </ul>
                    <ul class="bodyArea">
                        <li>
                            <a href="javascript:selectRecruitDetail('18')">
                                <span class="title">KB헬스케어는 이런 분을 찾습니다.</span>
                                <span class="date">2022-01-01 ~ 2022-12-31</span>
                            </a>
                        </li>
                    </ul>
                </div>
                <!--paging-->
<!--                <div class="paging">-->
<!--                    &lt;!&ndash; 변수 매핑 &ndash;&gt;-->
<!--                    &lt;!&ndash; 이전 버튼 &ndash;&gt;-->
<!--                    <a href="#" class="pagingPrev off">이전페이지</a>-->
<!--                    <ul>-->
<!--                        <div class="number">-->
<!--                            <li class="on"><li class="on"><a href="#" >1</a>&#160;-->
<!--                        </li>-->
<!--                        </div>-->
<!--                    </ul>-->
<!--                    &lt;!&ndash; 다음 버튼&ndash;&gt;-->
<!--                    <a href="#" class="pagingNext off">다음페이지</a>-->
<!--                </div>-->
                <!--paging end-->
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: "index"
}
</script>

<style scoped>

</style>