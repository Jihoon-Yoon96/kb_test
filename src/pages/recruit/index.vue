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
                        <li v-for="(li, i) in list" :key="i">
                            <nuxt-link :to="{path:`/recruit/${li.id}`}">
                                <span class="title">{{li.title}}</span>
                                <span class="date">{{ li.recruit_start }} ~ {{ li.recruit_end }}</span>
                            </nuxt-link>
                        </li>
                    </ul>
                </div>

                <div class="btnBottomArea tac">
                    <nuxt-link to="recruit/create" class="btnText recruit"><span>채용공고 등록 하기</span></nuxt-link>
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

<script setup lang="ts">
const list = ref([])

// 체용공고 리스트 가져오기
const {data, pending, error, refresh} = await useFetch(`http://125.131.88.58:8055/items/kb_announce`)
console.log(data)
if(data.value){
    list.value = data.value.data
}
</script>

<style scoped>

</style>