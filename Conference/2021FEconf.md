A1. Do more with less : Toss팀 디자인팀 UX Engineer 이병철

더 많은 일을 더 적은 노력으로

이야기 할 내용
UI 개발의 일반적인 문제
    해결책은? 디자인 시스템
디자인 시스템 도입 후 생기는 일반적인 문제
    코드를 디자인에 일치시키는 어려움
    소통의 어려움
    엄격함과 유연함 사이의 어려움
디자인 시스템, 그 다음은?

도움이 되는 내용
디자인 시스템 도입 시 나아지는 개선점
디자인과 프론트엔드 개발 작업의 생산성을 높이고 싶을 때!

UI 개발의 일반적인 문제
하나의 앱 안에서 버튼이나 텍스트가 반복되지만 전혀 다른 UI로 구성되어 있다
버튼이라는 같은 의도의 UI 각기 다른 모양이며
화면마다 매번 새로 디자인되는 버튼이 된다

보통 팀의 규모가 커지게 된다면 버튼 UI 디자인에 대한 일관성을 맞추기 어려워진다

UI 개발의 일반적인 문제

디자인 일관성이 떨어지면 => 중복코드, 파편화 => 유지보수가 어려운 UI코드

이를 해결하기 위한 디자인시스템이다!

데이터의 사본이 존재할 가능성을 없애라
버튼의 의도: 클릭하면 눌리고 어떤 액션을 실행하는 UI

첫 번째 코드를 디자인에 일치시키는 어려움
가이드를 잘못 이해하고 구현 디자인 툴 기능의 한계

두 번째 소통의 어려움
디자이너와 개발자는 너무 다르고 서로 다른 언어를 사용하는게 편할 떄가 있다.
비주얼 중심의 디자이너 언어
기능 중심의 개발자 언어

세 번째 엄격함과 유연함 사이의 어려움


다시 돌아보는 디자인 시스템 가이드


디자인(스케치 컴포넌트)          개발(React 라이브러리)

디자인과 코드 사이에 의존 관께를 만들 수 있지 않을까?

일반적인 툴의 한계 
버튼의 스타일만 바뀌어도 디자인팀은 모든 스티커를 수정해야한다
디자인 툴 안에서의 작동되지 않는 기능도 있다.
(ex . 스케치나 파그마)

Framer React 기반의 프로토타이핑 도구
새로운 디자인 툴로의 이주
리액트 컴포넌트를 코드를 작성이 가능
Code Component 
디자인 요소를 React 컴포넌트로 구현
디자인 패널을 통해 props 설정
ajax 구현도 가능하다.

디자인 시스템의 옵션을 변경해서 여러 화면사이즈 변경에 대한 반응형 시안을 보여준다
여러기기에서의 프리뷰를 보아도 UI가 깨지지 않고 보이게 된다. 
클릭도 편안~

구현체는 따로 존재하지만 디자인 CodeComponent 디자인 시안으로 첫번째인 디자인과 코드를 일치시킴으로 해결이 가능하다

제플린을 통한 UI개발 
문제점 디자인 시스템의 컴포넌트 
토스에서의 디지인 시스템 컴포넌트를 확인해주고 레이어에서 레이어 이름을 보고 컴포넌트의 속성을 유추해야하는 단점이 존재했다.
Hand-off를 이용한 문제가 있음

자체 핸드오프 개발하기
기존 툴의 한계 뛰어넘기
커스텀 핸드오프 컴포넌트 구현
CodeComponent 기능 활용 
프레이머에서 children 화면 연결
기본적인 핸드오프 구현