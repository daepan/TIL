# CSR은 왜 SEO에 불리할까?
리액트에 대한 SPA에 학습하다 SEO 관점에서 불리하다라는 단점이 있다는 내용을 보고 이에 대한 내용을 학습하였다.

> 먼저 SEO(Search Engine Optimization)란?
> 검색엔진 최적화는 웹페이지 검색엔진이 자료를 수집하고 순위를 매기는 방식에 맞게 웹 페이지를 구성하여 검색 결과의 상위에 나올 수 있도록 하는 작업을 의미한다



> CSR이란
> JavaScript를 사용하여 브라우저에서 콘텐츠를 렌더링하는 것

## CSR의 작동 방식

CSR 방식에서는 이 번들링이 완료된 js 파일을 모두 로드하기 전에는 첫 페이지를 로드할 수가 없다. 엄연히 말해서 첫 페이지는 이미 로드가 되었지만, 로드된 페이지는 빈 HTML 파일이다. 

그렇기에 HTML만 있는 빈문서만 날라온 이후 JS로 페이지를 그려내기 때문에 크롤러가 이를 판단하지 못하기 때문에 SEO에 불리하다라는 말을 하는 것이다.

## 진실은..
위의 내용만 가지고는 CSR이 SEO에 불리하다라는 것은 반만 정답이라고 할 수 있다.
이런 내용이 나오게 된 이유는 많은 크롤러가 javaScript를 지원하지 않기 때문이다.
하지만 Googlebot크롤러는 ES5+ JS를 지원하기에 CSR은 SEO에 취약하지 않다.
실질적으로 따지면 CSR이 SEO에 불리한 것은 맞지만 SEO가 불가능하다라는 표현은 잘못된 표현이다.


## 그렇디면 어떻게 해야할까?

*이 두 가지 렌더링 방법을 적절하게 사용하여 첫 번째 페이지 로딩에서는 서버 사이드 렌더링을 사용하고,*
*그 후에 모든 페이지 로드에는 클라이언트 사이드 렌더링을 활용하는 방법을 많이 사용한다.*
React에서는 Next.js, GatsbyJS, Vue에서는 Nuxt.js 등의 라이브러리가 SPA에서 SEO을 할 수 있도록 도와준다. 많이 사용하는 Next.js의 경우 살펴보면 전통적엔 SSR이 아닌 SPA에서 SEO에 유리하기 위한 SSR를 도입하고 그 이외에도 개발자들이 직접 노드에서 환경설정을 해주지 않고도 익숙한 툴(바벨, 웹팩 등)을 가지고 설정을 할 수 있게 지원해 주기에 많은 React 개발자들이 선호한다.
또는 CSR에서 메타 태그를 정의해주는 라이브러리를 사용하는 것도 방법이다. 대표적인 라이브러리로 *react-helmet*이 있다. 이 라이브러리는 동적으로 SEO에 필요한 메타태그들을 쉽게 변경할 수 있도록 도와준다. JSX 또는 TSX 내부에서 메타태그를 관리할 수 있다.