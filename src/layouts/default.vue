<template>
  <div class="wrapper">
      <!--  nav  -->
      <header>
          <div class="inner">
              <a href="/" class="btn-home"><h1 class="h1-logo">O-CARE</h1></a>
              <!--            <button type="button" class="btn-menu only-mobile">메뉴</button>-->
              <nav class="nav-menu">
                  <!--                <div class="nav-bg only-mobile"></div>-->
                  <ul id="gnb">
                      <li name="Aboutmenu"><a href="/"><span>KB헬스케어</span></a></li>
                      <li name="Noticemenu"><a href="/notice"><span>소식</span></a></li>
                      <li name="RecruitMgmtmenu"><a href="/recruit"><span>채용</span></a></li>
                      <li name="FAQmenu"><a href="/faq"><span>자주묻는질문</span></a></li>
                      <!-- <li name="mainmenu" class="english"><a href="/bcc/MainEng.do"><span>English</span></a></li> -->
                  </ul>
              </nav>
          </div>
      </header>
      <!--  nav  -->
      <div class="content">
          <slot/>
      </div>
      <!--    footer    -->
      <footer>
          <div class="inner">
              <div class="logo">
                  <p>KB헬스케어</p>
              </div>

              <div>
                  <p>㈜케이비헬스케어</p>
                  <p>사업자등록번호:356-86-02394 ㅣ 대표:최낙천</p>
                  <p>통신판매업신고번호: 2021-서울강남-06776호</p>
                  <p>06212 서울특별시 강남구 테헤란로 334, 15층(교정공제회 역삼빌딩) | 1544-3677</p>
                  <p>Copyright © KB헬스케어. All rights reserved.</p>

                  <p class="footer-btn">
                      <a href="/bcc/Agreement.do">서비스이용약관</a>
                      <span class="m-block"><a href="/bcc/Person.do" class="fwb">개인정보처리방침</a></span>
                  </p>
              </div>
          </div>
      </footer>
      <!--    footer    -->
  </div>
</template>

<script>
export default {
    name: "default"
}
</script>

<style scoped>
/*header{*/
/*    width: 100%;*/
/*    height: 8.2rem;*/
/*    position: fixed;*/
/*    top: 0;*/
/*    left: 0;*/
/*    background: #fff;*/
/*    padding: 2.5rem 0 0 0 !important;*/
/*    border-bottom: 1px solid #b6b7a7;*/
/*    z-index: 20;*/
/*}*/

/*header .inner {*/
/*    min-width: 1280px;*/
/*    margin: auto;*/
/*    margin-top: auto;*/
/*    margin-right: auto;*/
/*    margin-bottom: auto;*/
/*    margin-left: auto;*/
/*    display: flex;*/
/*    align-items: center;*/
/*    justify-content: space-around;*/
/*}*/

/*header a.btn-home {*/
/*    position: relative;*/
/*    z-index: 1;*/
/*    display: inline-block;*/
/*    width: 10rem;*/
/*    height: 3rem;*/
/*    vertical-align: top;*/
/*}*/

/*header h1.h1-logo {*/
/*    height: 3.2rem;*/
/*    width: 10rem;*/
/*    height: 3rem;*/
/*    font-size: 0;*/
/*    text-indent: -999rem;*/
/*    background: url('@/public/img/top-logo.svg') no-repeat left center;*/
/*    background-size: auto 100%;*/
/*}*/

/*header .btn-menu {*/
/*    position: absolute;*/
/*    right: 1.2rem;*/
/*    top: -1.1rem;*/
/*    width: 4rem;*/
/*    height: 4rem;*/
/*    font-size: 0;*/
/*    text-indent: -999rem;*/
/*    background: url('@/public/img/btn-main-menu.svg') no-repeat center center;*/
/*    background-size: 4rem auto;*/
/*}*/

/*.content{*/
/*    position: static;*/
/*    top: 50px;*/
/*}*/

/*footer{padding: 4.2rem 3rem 5rem;background:#f1f1f1;}*/
/*footer .logo{display:none;}*/
/*footer p{color: #000;font-size:1.2rem;font-family: 'KBDisplay';font-weight: 500;line-height:1.58;letter-spacing:0.12px;}*/
/*footer .footer-btn{margin-top:2rem;}*/
/*footer .footer-btn a{display:inline-block;height:3.5rem;padding: 0 1.8rem;color: #14273d;font-size:1.2rem;line-height:3.3rem;font-weight:500 !important;border-radius:3rem;border: 1px solid #14273d;}*/
/*footer .footer-btn .m-block{margin-top:1.2rem ;}*/

</style>