###### 문제기록

1. ga.js vs gtag.js
  - ga.js는 이미 legacy(옛날)문서로 GA기능을 모두 소화하는데 한계가 있음
  - gtag.js로 바뀌어야 하나 많은 웹사이트들이 GA.js(구버전)을 지원하고 있음
  - 최대한 많은 GA기능을 구현하기 위해 gtag.js로 갈꺼임

2.  장바구니 버튼을 php함수가 먹고 있음
 - 조회화면해보자

2. [이벤트 쏘기](https://developers.google.com/analytics/devguides/collection/gtagjs/sending-data)

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
