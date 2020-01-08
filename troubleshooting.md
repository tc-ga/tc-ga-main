###### 문제기록

1. ga.js vs gtag.js
  - ga.js는 이미 legacy(옛날)문서로 GA기능을 모두 소화하는데 한계가 있음
  - gtag.js로 바뀌어야 하나 많은 웹사이트들이 GA.js(구버전)을 지원하고 있음
  - 최대한 많은 GA기능을 구현하기 위해 gtag.js로 갈꺼임

2.  장바구니 버튼을 php함수가 먹고 있음
 - 조회화면해보자

3. 전자상거래 모바일화면 공통 html (header.html) 같은것을 못찾겠음
 - 걍 거래완료 화면에 gtag.js 박아버림

4. 상품별 구매합계가 단가로 들어가버림;;;   

5. 주문완료 수량 안맞음
  - String을 int로 바꿔보겠다
  - GA 버그

6. 네이버페이 추가 작업
- 모바일 - 상세보기, 장바구니 화면
- 웹 - ~~상세보기~~, 장바구니 화면  




```
// Get a reference to the form element, assuming
// it contains the ID attribute "signup-form".
var form = document.getElementById('signup-form');

// Add a listener for the "submit" event.
form.addEventListener('submit', function(event) {

  // Prevent the browser from submitting the form
  // and thus unloading the current page.
  event.preventDefault();

  // Send the event to Google Analytics and
  // resubmit the form once the hit is done.
  gtag('event', 'signup_form_complete', {
    'event_callback': function() {
      form.submit();
    }
  });
});
```
