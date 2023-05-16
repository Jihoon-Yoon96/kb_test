<template>
    <div class="container">
        <form name="formNoticeList" id="formNoticeList" method="post">
            <input name="firstIndex"  id="firstIndex"   type="hidden"   value="0">
            <input name="pageIndex"   id="pageIndex"    type="hidden"   value="1">
            <input name="pageUnit"    id="pageUnit"     type="hidden"   value="10">
            <input name="ntcNo"       id="ntcNo"        type="hidden" >
            <input name="searchNtcFg" id="searchNtcFg"  type="hidden" >
            <div class="inners" id="contents">
                <!-- 상세 : s -->
                <h2 class="subTopTitle">소식</h2>
                <div class="tabArea">
                    <div class="tabList round">
                        <ul>
                            <li name="ntcFgLi"><a href="#" name="ntcFgTab" class="tab" cmCd="" id="ntcFgAll"><span>전체</span></a></li>

                            <li name="ntcFgLi"><a href="#" name="ntcFgTab" class="tab" cmCd="300117" id="300117"><span>공지사항</span></a></li>

                            <li name="ntcFgLi"><a href="#" name="ntcFgTab" class="tab" cmCd="300118" id="300118"><span>언론보도</span></a></li>

                            <li name="ntcFgLi"><a href="#" name="ntcFgTab" class="tab" cmCd="300119" id="300119"><span>이벤트</span></a></li>

                        </ul>
                    </div>
                    <div class="tabContArea">
                        <div class="tabCont on">



                            <h4 class="blind">전체 내용</h4>
                            <div class="thumbnail_ist">
                                <ul>

                                    <li id="">
                                        <a href="javascript:selectDetail('35')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="" width="180px">

                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">[일정변경] KB헬스케어_디지털 헬스케어 B2C,B2B 통합 플랫폼 구축 사업 공고</div>
                                                <div id="date" class="date">
                                                    2023-03-27 14:47
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('28')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/cover_image.jpg" alt="" >
                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">[영상] KB헬스케어, 건강관리 플랫폼 ‘오케어’로 디지털 헬스케어 선도</div>
                                                <div id="date" class="date">
                                                    2022-10-27 18:33
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('34')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="" width="180px">

                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">(재 공고) 정보보호관리체계 수립 컨설팅 용역사업</div>
                                                <div id="date" class="date">
                                                    2023-03-16 18:36
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('27')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/survery.jpg" alt="" >
                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">KB헬스케어 출범 1주년 사용성 조사... “건강관리 습관 형성 위해 이용”</div>
                                                <div id="date" class="date">
                                                    2022-10-27 18:27
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('32')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="" width="180px">

                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">정보보호관리체계 수립 컨설팅 사업 공고</div>
                                                <div id="date" class="date">
                                                    2023-02-27 09:51
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('26')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/Certification_221006.jpg" alt="" >
                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">비의료 건강관리서비스 12개 시범 인증… 케어코디 활성화 추진</div>
                                                <div id="date" class="date">
                                                    2022-10-06 00:00
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('31')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="" width="180px">

                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">문서 암호화 솔루션 도입 사업 공고</div>
                                                <div id="date" class="date">
                                                    2023-02-24 12:58
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('25')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/salted_220923.jpg" alt="" >
                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">KB헬스케어, 솔티드와 바른 자세 코칭 서비스 위한 MOU 체결</div>
                                                <div id="date" class="date">
                                                    2022-09-23 00:00
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('30')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="" width="180px">

                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">(재공고)2023년 KB헬스케어 종합 광고 대행 서비스 제공자 선정 공고</div>
                                                <div id="date" class="date">
                                                    2023-02-17 14:17
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('24')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/cover2_0922.png" alt="" >
                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">[보험헬스케어 활로는] ④KB손해보험 오케어, 원스톱 맞춤관리 차별화</div>
                                                <div id="date" class="date">
                                                    2022-09-22 00:00
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('29')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="" width="180px">

                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">시스템 접근제어 솔루션 도입 사업</div>
                                                <div id="date" class="date">
                                                    2022-11-02 18:00
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                    <li id="">
                                        <a href="javascript:selectDetail('23')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/cover_2.jpg" alt="" >
                                            </div>

                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">“즐기는 건강관리… 삶의 가치가 달라져요”</div>
                                                <div id="date" class="date">
                                                    2022-08-27 00:00
                                                </div>

                                            </div>
                                        </a>
                                    </li>

                                </ul>
                            </div>





                            <!--paging-->
                            <div class="paging">
                                <!-- 변수 매핑 -->



                                <!-- 이전 버튼 -->

                                <a href="#" class="pagingPrev off">이전페이지</a>


                                <ul>
                                    <div class="number">
                                      <li class="on">
                                          <a href="#" >1</a>&#160;
                                          <li>
                                          <a href="#" onclick="fnPageChange(2); return false;">2</a>&#160;
                                          </li>
                                        </li>
                                    </div>
                                </ul>
                                <!-- 다음 버튼-->


                                <a href="#" onclick="fnPageChange(2)" class="pagingNext">다음페이지</a>

                            </div>


                        </div>

                        <div class="tabCont">
                            <h4 class="blind">공지 내용</h4>
                            <div class="thumbnail_ist">
                                <ul>


                                    <li>
                                        <a href="javascript:selectDetail('35')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="">

                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">[일정변경] KB헬스케어_디지털 헬스케어 B2C,B2B 통합 플랫폼 구축 사업 공고</div>
                                                <div class="date">2023-03-27 14:47</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('34')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="">

                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">(재 공고) 정보보호관리체계 수립 컨설팅 용역사업</div>
                                                <div class="date">2023-03-16 18:36</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('32')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="">

                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">정보보호관리체계 수립 컨설팅 사업 공고</div>
                                                <div class="date">2023-02-27 09:51</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('31')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="">

                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">문서 암호화 솔루션 도입 사업 공고</div>
                                                <div class="date">2023-02-24 12:58</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('30')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="">

                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">(재공고)2023년 KB헬스케어 종합 광고 대행 서비스 제공자 선정 공고</div>
                                                <div class="date">2023-02-17 14:17</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('29')" class="item">
                                            <div class="img">
                                                <img src="../asset/images/noImg.png" alt="">

                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">

                                                    <div class="flag red">공지사항</div>


                                                </div>
                                                <div class="title">시스템 접근제어 솔루션 도입 사업</div>
                                                <div class="date">2022-11-02 18:00</div>
                                            </div>
                                        </a>
                                    </li>




                                </ul>
                            </div>
                        </div>

                        <div class="tabCont">
                            <h4 class="blind">공지 내용</h4>
                            <div class="thumbnail_ist">
                                <ul>




                                    <li>
                                        <a href="javascript:selectDetail('28')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/cover_image.jpg" alt="">
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">[영상] KB헬스케어, 건강관리 플랫폼 ‘오케어’로 디지털 헬스케어 선도</div>
                                                <div class="date">2022-10-27 18:33</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('27')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/survery.jpg" alt="">
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">KB헬스케어 출범 1주년 사용성 조사... “건강관리 습관 형성 위해 이용”</div>
                                                <div class="date">2022-10-27 18:27</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('26')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/Certification_221006.jpg" alt="">
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">비의료 건강관리서비스 12개 시범 인증… 케어코디 활성화 추진</div>
                                                <div class="date">2022-10-06 00:00</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('25')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/salted_220923.jpg" alt="">
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">KB헬스케어, 솔티드와 바른 자세 코칭 서비스 위한 MOU 체결</div>
                                                <div class="date">2022-09-23 00:00</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('24')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/cover2_0922.png" alt="">
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">[보험헬스케어 활로는] ④KB손해보험 오케어, 원스톱 맞춤관리 차별화</div>
                                                <div class="date">2022-09-22 00:00</div>
                                            </div>
                                        </a>
                                    </li>





                                    <li>
                                        <a href="javascript:selectDetail('23')" class="item">
                                            <div class="img">

                                                <img src="https://kbidpkrchomepagest001.blob.core.windows.net/image/cover_2.jpg" alt="">
                                            </div>
                                            <div class="textArea">
                                                <div class="flagArea">


                                                    <div class="flag blue">언론보도</div>

                                                </div>
                                                <div class="title">“즐기는 건강관리… 삶의 가치가 달라져요”</div>
                                                <div class="date">2022-08-27 00:00</div>
                                            </div>
                                        </a>
                                    </li>


                                </ul>
                            </div>
                        </div>

                        <div class="tabCont">
                            <h4 class="blind">공지 내용</h4>
                            <div class="thumbnail_ist">
                                <ul>

























                                </ul>
                            </div>
                        </div>

                    </div>
                </div>
                <!-- 상세 : e -->
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