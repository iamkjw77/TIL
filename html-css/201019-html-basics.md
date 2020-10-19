패스트캠퍼스 - HTML 수업을 듣고 중요 내용을 정리합니다.

## mark up

- 태그 등을 이용하여 문서나 데이터의 구조를 명기하는 언어의 한 가지
- marking이라고 생각, ex)　＜강사＞김데레사</강사>

## HTML 표준

- XHTML 1.0 : 표준
- HTML 4.01 : 표준
- HTML5 : 가장 최신 표준, mark up + API를 합친 개념

## HTML5 콘텐츠 모델(Contents Models) 

- 명확한 정보 구조 설계 및 구성을 위해 카테고리를 정의하여 각 요소별로 비슷한 성격을 가지고 있는 것끼리 그룹화한 것

---

## 아웃라인 알고리즘 

- 정보 구조를 명확히 할 수 있도록 등장한 개념
- 웹 페이지의 정보 구조를 판별할 수 있는 개념으로 책의 목차와 비슷

---

## 웹 접근성(Web Accessibility)

- 장애인이나 고령자분들이 웹 사이트에서 제공하는 정보를 비장애인과 동등하게 접근하고 이용할 수 있도록 보장하는 것

### WCAG(Web Content Accessibility Guidelines)

- 웹 사이트/애플리케이션에서 충족해야 하는 기준을 정의하여 장애가 있는 사용자가 보다 쉽게 이용할 수 있도록 준수해야 하는 지침

---

## role 속성

- 웹 접근성을 위해 나왔으며 위젯, 구조 및 동작에 대한 의미 정보를 올바르게 전달하기 위해 나옴. 즉, 좀 더 명확한 구조와 의미를 부여하는 역할

```html
<a role=“button”></a> 
<!--  마크업은 버튼이 아니지만 역할은 버튼이야! -->
```

---

## DOM(Document Object Model, 문서 객체 모델)
- 문서 객체 : <html>이나 <body>같은 html문서의 태그들을 JS가 이용할 수 있는 객체(Object)로 만들면 그것을 문서 객체라고 한다.

---

## CSS 방법론
1. OOCSS : ex)btn facebook, btn twitter, .btn{ 공통 버튼 스타일 정의 }

2. BEM(Block Element Modifier) :　
ex)header__search-form
(__는 상위요소에 포함된~ 이라고 생각, 재사용/확장성에 용이)

---

## 케이스 스타일
- 카멜식(Camel case) : 낙타의 모양에서 따온 방법, 첫 단어는 소문자로 시작하고, 두 번째 단어부터 대문자로 시작한다. 단어와 단어 사이는 붙인다.
ex) rocketLaunchDuration

- 케밥식(Kabab case) : 케밥이 코챙이에 꽂힌 모습에서 생긴 방법이다. 모든 단어가 소문자로 시작하고, 단어와 단어 사이는 “-”로 연결된다.
ex) rocket-launch-duration

- 파스칼식(Pascal case) : 첫 단어를 대문자로 시작한다.
ex) RocketLaunchDuration

- 스네이크식(Snake case) : 케밥식과 매우 유사하지만, 각 단어가 “-”가 아닌 “_”로 연결된다.
ex) rocket_launch_duration