#1 웹앱 삽질기
* 웹앱애서 LazyLoading을 할 때 생각해야 할 점
  * 이미지는 다음 페이지 직전 미리 로딩
  * 에니메이션은 모두 로딩되기 전까진 첫 이미지만 띄워놓고 모두 로딩되면 프라미스를 통해 움직이자
  
 #2 앵귤러
  우리가 아는 뷰와의 차이점
  1. 브라우저 하위버젼 상황 자동 모듈 import
  2. 자주 업데이트해서 개발자의 공부를 늘려줌
  3. LazyLoading CodeSpliting 쉬움
   
#3 바닥부터 시작하는 뷰 테스트 리팩토링
  1. 템플릿에 표현식 쓰지말자 테스트하기 힘들다
  2. ref정도는 기본이다
  3. shallowMount 이해하고쓰면 좋다
  4. 리팩토링 자바스크립트 읽어서 잘 공부중이다