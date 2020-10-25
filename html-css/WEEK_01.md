## HTML
<details open>
<summary>1일차</summary>
<div markdown="1">

#### [HTML 정의]
- HTML(HyperText Markup Language) : 웹 페이지를 위한 지배적인 마크업 언어
- Markup : 태그 등을 이용하여 문서나 데이터의 구조를 명기하는 언어의 한 가지
- 웹 페이지의 구조적의미를 나타냄

#### [HTML 표준과 HTML5]
- 웹 표준 : 웹에서 표준적으로 사용되는 기술이나 규칙을 의미하며, 웹 사이트에 접속한 사용자는 어떠한 운영체제나 브라우저를 사용하더라도 동일하게 보이고 정상적으로 작동함을 의미
- HTML 4.01 → XHTML → HTML5

#### [HTML5]
- 단순히 웹 문서를 작성할 때 사용되는 마크업 언어(HTML)의 문법적 버전뿐만 아니라 새로운 DOM API 스펙을 포함
- 비디오 및 오디오와 같은 미디어 엘리먼트에 대한 API를 포함해 웹 앱 구현, 문서 편집 등과 같은 다양한 기능에 대한 API가 추가됨
- 이런 API들은 JavsScript를 통해 이용할 수 있다.

#### [HTML5]
- 단순히 웹 문서를 작성할 때 사용되는 마크업 언어(HTML)의 문법적 버전뿐만 아니라 새로운 DOM API 스펙을 포함
- 비디오 및 오디오와 같은 미디어 엘리먼트에 대한 API를 포함해 웹 앱 구현, 문서 편집 등과 같은 다양한 기능에 대한 API가 추가됨
- 이런 API들은 JavsScript를 통해 이용할 수 있다.

#### [HTML5 콘텐츠 모델]
- 좀 더 명확한 정보 구조 설계 및 구성을 위해 카테고리를 정의하여 각 요소별로 비슷한 성격을 가지고 있는 것끼리 그룹화
![CSS Content Model](https://seulbinim.github.io/WSA/images/markup/content-model.png)

#### [HTML5 아웃라인 알고리즘]
- 정보구조를 명확히 할 수 있도록 ‘아웃라인 알고리즘’ 이라는 개념이 도입됨
- 책의 목차와 비슷한 개념으로 웹 페이지의 정보구조를 판별할 수 있는 개념
- HTML5에서 추가된 많은 요소들은 대부분 아웃라인 알고리즘과 관련이 있음
    - ex) 헤딩 콘텐츠, 섹셔닝 콘텐츠, 섹셔닝 루트 요소

#### [HTML DOCTYPE, Document Type]
- HTML이 어떤 버전으로 작성되었는지 미리 선언해, 웹 브라우저가 내용을 올바로 표시할 수 있도록 해주는 것이 `<!DOCTYPE>`
- 버전 별로 지원하는 태그가 조금씩 다름

#### [HTML 언어설정]
```html
<html lang="ko-KR">
```
- KR : Republic of Korea 지역코드, ko 만 사용하면 한국어를 통칭

#### [웹 접근성, Web Accessibility]
- 장애인이나 고령자분들이 웹 사이트에서 제공하는 정보를 비장애인과 동등하게 접근하고 이용할 수 있도록 보장하는 것
- WCAG(Web Content Accessibility Guidelines) : 웹 사이트/애플리케이션에서 충족해야 하는 기준을 정의하여 장애가 있는 사용자가 보다 쉽게 이용할 수 있도록 준수해야 하는 지침
- WAI-ARIA : WAI(Web Accessibility Initiative) - ARIA(Accessible Rich Internet Applications), 여기서 RIA란, 정적인 HTML과 단순한 자바스크립트 환경의 웹이 아닌 동적인 자바스크립트와 Ajax와 같은 기술을 사용한 환경에서 수준높은 UX(User eXperience)를 제공하는 웹 애플리케이션이다.
- RIA는 화려하고 편리한 웹 애플리케이션이지만 스크린리더와 같은 보조기술을 사용하는 장애인들이 접근하기에 취약하다. 때문에 WAI-ARIA는 RIA에서 스크린리더기 및 보조기기 등에서 접근성 및 상호 운용성을 향상시키기 위한 목적으로 탄생되었으며 웹 애플리케이션에 역할(Role), 속성(Property), 상태(State) 정보를 추가하여 이를 개선 할 수 있도록 제공하고 있다. 
- role 속성 : 웹 접근성을 위해 나왔으며 위젯, 구조 및 동작에 대한 의미 정보를 올바르게 전달하기 위해 나옴
- Skip Navigation : 건너뛰기 링크는 말 그대로 ‘링크’를 건너뛰기 위해 제공되는 메뉴를 의미합니다. 여기서 ‘링크’라는 것은 매 페이지마다 반복적으로 제공되는 링크를 말하며, 건너뛰기 링크는 이를 건너뛰어 바로 본문으로 포커스를 이동할 수 있게 해주는 역할, 사용자 특히 장애인이 반복적인 링크들로 인해 불편해 하지 않고, 원하는 영역 즉 ‘본문’으로 바로 이동할 수 있는 건너뛰기 링크를 반드시 제공해야만 한다.

#### [aria 속성]
- aria-current : 현재 맥락과 일치하는 항목을 의미
token의 값은 page, step, location, date, time, true, false(default)으로 정해져 있고 이 중 하나만 사용할 수 있습니다.

- aria-selected : 단일 속성 또는 다중 선택이 가능한 요소에 한하여 선택상태를 명시하는 용도로 사용, 키보드 초점을 받을 수 있는 요소에 적용해야한다.

- aria-haspopup : 연결되어 있는 팝업(메뉴, 대화상자) 정보를 제공한다. 팝업은 다른 내용 위에 표시하는 블록을 의미한다.

- aria-expanded : 제어 대상의 확장 또는 축소상태를 나타낸다. 어코디언, 메뉴, 콤보박스, 트리와 같이 하위 그룹(또는 독립적인) 내용을 토글(열기, 닫기)하는 경우에 사용하면 적절하다. 독립적인 내용을 제어할 때 aria-controls 속성을 이용하여 제어 대상을 명시해야함.

- aria-pressed : aria-presses 속성은 토글 버튼(button, role=“button”)이 눌린 상태를 표시한다. 흔하게 사용하는 속성은 아니다. 이속성을 사용하기 전에 aria-selected 속성을 먼저 검토하는 것이 좋다.

- aria-hidden : 접근성 API(보조기기 접근 가능성) 차단 상태를 결정한다. 화면에 표시하지만 잠시 사용을 제한하는 콘텐츠에 사용

- aria-invalid : 주로 input 요소에 선언하여 사용자가 입력한 값이 요구하는 형식과 일치하는지 여부를 나타낸다.

- aria-controls : 현재 요소가 제어하는 대상을 명시하는 속성
- aria-live : 실시간으로 내용을 갱신하는 영역을 의미
- aria-labelledby : aria-labelledby, aria-label, aria-describedby 속성은 모두 현재 요소에 설명을 제공하는 속성

- aria-errormessage : 주로 input 요소에 선언하여 오류 메시지를 제공하는 요소를 값으로 참조
- aria-modal : 모달인지 여부를 보조기기에 전달

#### [HTML, CSS 설계]
1. 구조 분석 단계
    - 3단 : header(네비게이션 포함), contents, footer
    - 4단 : eader, navigation(네비게이션을 따로 분리) ,contents, footer

2. 논리적 순서생각
    - 사용자의 입장이 되어 흐름을 생각해보자 
    - ex) 로그인 창) 아이디 → 비밀번호 → 로그인 상태 유지 → 로그인

3. 시맨틱 마크업
    - 컴퓨터, 브라우저가 잘 이해할 수 있도록 약속하는 것
    - 의미에 맞게 HTML요소를 올바르게 사용하는 것

4. 네이밍(케이스 스타일)
    - 1.케밥-케이스
        - kebab-case, spinal-case, Train-Case, Lisp-case
        - 하이픈으로 단어를 연결하는 표기법
        - HTML 태그의 id, class 속성으로 흔히 사용됨.

    - 2.파스칼 표기법
        - PascalCase, BackgroundColor, TypeName, PowerPoint
        - 첫 단어를 대문자로 시작하는 표기법

    - 3.스네이크 케이스(뱀 표기법)
        - snake_case, background_color, type_name
        - 단어를 밑줄 문자로 구분하는 표기법

    - 4.헝가리언 표기법
        - strName, bBusy, szName
        - 접두어를 사용하는 표기법

#### [CSS 방법론]
1. BEM(Block Element Modifier)
    - 개발, 디버깅, 유지보수를 위하여 가능한 한 명확하게 네이밍하는 것이 목표
    - 소문자, 숫자만을 조합
    - 조합은 하이픈(-)으로 연결하여 작명
    - 모든 것이 클래스이고, 중첩된 것은 없다.

```html
<button class="button">
  Normal button
</button>
<button class="button button--state-success">
  Success button
</button>
<button class="button button--state-danger">
  Danger button
</button>
```
```css
.button {
  display: inline-block;
	border-radius: 3px;
	padding: 7px 12px;
	border: 1px solid #D5D5D5;
	background-image: linear-gradient(#EEE, #DDD);
	font: 700 13px/18px Helvetica, arial;
}
.button--state-success {
  color: #FFF;
	background: #569E3D linear-gradient(#79D858, #569E3D) repeat-x;
}
.button--state-danger {
  color: #900;
}
```
- [출처](https://junwoo45.github.io/2019-08-29-BEM/)

#### 2. OOCSS(Object Oriented CSS), 객체지향 CSS
- 구조와 모양으로 분리
- 반복적인 것은 별도로 분리
- 콘테이너와 콘텐츠의 분리(의존적인 스타일 사용x)
- 가능한 짧고 간결하게 작성
- 동작과 형태가 예상 가능하도록 명확히 작성
- 형태보다는 목적의 의미를 작성
- 구체적이지 않고 일반적으로 사용가능하도록 작성

```css
<a class="btn facebook">Facebook</a>
<a class="btn twitter">Twitter</a>
```

- 장점 
    - 코드의 재사용성이 높아 코드의 길이가 줄어든다. (css 파일크기가 줄어드므로 속도 향상)
    - 새로운 요소를 추가할 때 기존 모듈을 통해서 재사용이 가능하고 쉽게 확장가능하다.(유지보수)

- 단점 
    - 복잡해지는 HTML에서는 오히려 유지보수가 힘들다
    - 가독성이 떨어진다.
    - 미디어 객체와 함께 적용하기는 좋으나 프로젝트 전반적으로 적용하기에는 어렵다.

#### [크로스 브라우징]
- 지원할 수 없는 다른 웹 브라우저를 위한 장치를 구현하여 모든 웹 브라우저 사용자가 방문했을 때 정보로서의 소외감을 느끼지 않도록 하는 방법론적 가이드를 의미

#### [웹 폰트]
- 방문자의 로컬 컴퓨터에 폰트 설치 여부와 상관없이 온라인의 특정 서버에 위치한 폰트 파일을 다운로드하여 화면에 표시해주는 웹 전용 폰트
- 문제점 : 네트워크의 속도, 웹 폰트의 용량, 웹 폰트가 적용된 텍스트가 보이지 않는 문제
- 해결법 : 웹 폰트는 네트워크를 통해 다운로드하는 자원이기 때문에 파일의 크기가 크면 웹 폰트가 적용된 글자가 화면에 표시될 때까지 시간이 지연되는 문제가 발생한다. 이러한 문제는 폰트 파일의 용량을 최적화해 완화할 수 있다.

#### [웹 폰트 최적화 방법]
- WOFF, WOFF2 형식 사용　:　폰트 형식에서 WOFF(Web Open Font Format) 형식과 WOFF 2.0 형식(이하 WOFF2 형식)은 압축된 폰트 형식이다. 같은 계열에 속하는 WOFF 형식과 WOFF2 형식에서는 WOFF2 형식이 30~50% 더 압축된 형식이다.
- 서브셋 폰트 사용 : 서브셋 폰트(subset font)는 폰트 파일에서 불필요한 글자를 제거하고 사용할 글자만 남겨둔 폰트다.

[참고 및 출처](https://d2.naver.com/helloworld/4969726)

#### [자주쓰는 웹 폰트와 사용법]
- Noto Sans(아시아권 언어를 사용하기 적합) = Noto Sans = Spoqa han sans
- 글꼴군 : 폰트가 없을 경우 사용 ex) serif(바탕체), sans-serif(고딕체)
- font-family: 폰트 ,글꼴군;
- F12-네트워크 패널-status가 200이면 응답함, 404이면 파일 찾을 수 없음, 500이면 인터넷 서버장애

#### [CSS Box Model]
- 문서의 레이아웃을 계산할 때, 브라우저의 렌더링 엔진은 표준 CSS 기본 박스 모델에 따라 각각의 요소를 사각형 박스로 표현
- 하나의 박스는 네 부분(영역)으로 이루어진다. 각 영역을 콘텐츠 영역, 안쪽 여백(패딩) 영역, 테두리 영역, 그리고 바깥 여백(마진) 영역이라고 부른다.

![CSS Box Model](https://codinglead.github.io/images/box-model.png)

#### [브라우저별 접두사]
1. -ms : IE → -webkit으로 바뀜
2. -webkit :chrome
3. -moz : 파이어폭스
4. -o : 오페라 → -webkit으로 바뀜

#### [DOM]
- Document Object Model(문서 객체 모델)
- 문서 객체 모델 : 문서의 구조화된 표현을 제공하며, 프로그래밍언어가 DOM 구조에 접근할 수 있는 방법을 제공하여 그들이 문서구조, 스타일, 내용 등을 변경 할 수 있게 돕는다.
- DOM은 구조화된 nodes와 property와 method를 갖고 있는 object로 문서를 표현한다. 이들은 웹 페이지의 스크립트 또는 다른 언어들에서 사용될 수 있게 연결시켜주는 역할을 담당한다.


</div> 
</details>


---
<details open>
<summary>2일차</summary>
<div markdown="2">

#### [BFC, Block Formatting Context]
- 웹 페이지를 렌더링하는 시각적 CSS의 일부, 블록박스의 레이아웃이 발생하는 지점과 플로팅 요소의 상호작용 범위를 결정하는 범위
- 레이아웃 안에 작은 레이아웃
- 요소를 세로로 배치하는 영역

```html
<div class="container">
  <div class="float-left">
  </div>
</div>
```

```css
<style>
  .container {
    color: #833ab4;
    border: 5px dashed;
    margin: 20px;
    padding: 10px;
    border-radius: 5px;
  }
  .float-left {
    float: left;
    background-color: #833ab450;
    padding: 15px;
    height: 100px;
  }
</style>
```
- .float-left 영역이 container를 벗어난다. block 레벨 요소(container)가 float 된 자식 요소를 포함하지 않기 때문에 발생한 현상이다. 
- 이때, .container에 overflow: hidden(or auto)을 넣으면 container에 BFC가 생성되었다. 이제는 float요소의 높이가 container의 높이에 영향을 준다. BFC는 그 안에 만들어진 요소를 포함하기 때문이다.

    ##### [자신의 BFC가 생성되는 경우]
    - html root 태그 (body 태그는 만들어지지 않는다)
    - none을 제외한 float
    - position: fixed, absolute
    - display: inline-block, table, table-cell, table-caption
    - overflow: visible을 제외한 모든 값
    - display: flow-root (일부 브라우저만 동작함)
    - display: flex, inline-flex, grid, inline-grid

[출처](https://blueshw.github.io/2020/05/17/know-css-block-formatting-context/)


#### [IFC, Inline Formatting Context]
- 요소를 가로로 배치하는 영역

#### [color 속성]
- sRGB 색 공간의 색을 표현하며, 추가로 알파 채널 투명도 값도 가질 수 있어 자신이 가리키는 색상과 배경이 어떻게 합성되어야 하는지 지정할 수 있다.
- 사용법 : 
    1. 키워드 사용(blue, transparent 등)
    2. RGB 3차원 좌표계 사용(# + 16진수 표기법 또는 rgb(), rgba()의 함수형 표기법)
    3. HSL 실린더형 좌표계 사용(hsl(), hsla()의 함수형 표기법)

    ##### [color 값 키워드]
    - transparent : 완전히 투명색으로 색을 입힌 항목의 뒤편이 보인다. 기술적으로 transparent는 rbga(0, 0, 0, 0)의 짧은 이름
    - currentColor : 요소의 color 속성값을 나타낸다. 이를 통해 다른 속성이 color 속성값을 따라가도록 설정할 수 있다. color 속성의 값으로 currentColor 키워드를 사용하면, 값을 상속받은 color 속성에서 대신 가져온다.

#### [box-sizing 속성]
- 요소의 너비와 높이를 계산하는 방법을 지정
- CSS 박스 모델 기본값에서, 요소의 테두리나 안쪽 여백이 있으면 너비와 높이가 더해져 화면에 그려진다. 따라서 크기를 설정할　때, 원하는 크기를 얻으려면 테두리나 안쪽 여백을 고려해야 한다.
- content-box : 기본값 (content 상자 기준)
- border-box : 테두리와 안쪽 여백의 크기도 요소의 크기로 고려한다. (border 기준)
width, height = border + padding + content

#### [justify-content 속성]
- flexbox의 주기능 중 하나는 (주축과 교차축으로 표현되는) flex container 공간 안에 flex항목들을 정렬하고 여유 공간을 항목 간에 분배하는 것
- justify-content 속성은 주축에 따라 flex 항목 행을 정렬하는 방식을 지정
- 속성값
    - flex-start : flex 항목 행 내의 항목들이 flex 컨테이너의 시작선에서부터 정렬(기본값)
    - flex-end : flex 항목 행의 마지막 항목이 flex container의 끝선에 정렬
    - center : flex 항목들이 flex 항목 행의 가운데 정렬
    - space-between : 주축 방향 여유 공간을 flex항목 사이 공간에 균등 배분
    - space-around : 시작선과 끝선, flex 항목 간 공간을 균등 배분에 고려하여, 시작선 및 끝선과 flex 항목 간의 공간 크기를 1로 배분한다면, flex 항목 사이의 공간은 2로 배분 
    - space-evenly : 여유 공간을 flex 항목 사이의 공간 및 시작선과 끝선과 flex 항목 간의 공간에 모두 균등하게 배분
 
[flex 게임](https://flexboxfroggy.com/#ko)

#### [position 속성]
- 문서 상에 요소를 배치하는 방법을 지정, top, right, bottom, left 속성이 요소를 배치할 최종위치를 결정
- 속성값
    1. static : 요소를 normal-flow(일반적인 흐름)에 따라 배치, top, right, bottom, left, z-index 속성이 아무런 영향을 주지않는 기본값

    2. relative :  요소를 normal-flow에 따라 배치하고, 자기 자신을 기준으로 top, right, bottom, left 값에 따라 offset을 적용
        - ※ offset : 동일 오브젝트 안에서 오브젝트 처음부터 주어진 요소나 지점까지의 변위차를 나타내는 정수형
        - ex) 문자열 S의 배열이 ‘abcdef’ 라면 에서 ‘c’문자는 문자열 S의 시작점에서 2의 오프셋을 지닌다고 할 수 있다. 

    3. absolute : 요소를 normal-flow(일반적인 흐름)에서 제거하고, 페이지 레이아웃에 공간도 남아있지 않는다. 대신 가장 가까운 위치 지정 요소에 대해 상대적으로 배치한다. 단 조사 중 위치 조정 요소가 없다면 초기 컨테이닝 블록을 기준으로 삼는다. 최종 위치는 top, right, bottom, left값이 지정한다.

    4. fixed : 요소를 normal-flow(일반적인 흐름)에서 제거하고, 페이지 레이아웃에 공간도 배정하지 않는다. 대신, 스크린의 뷰포트(viewport)를 기준으로 한 위치에 배치된다. 즉, 스크롤되어도 움직이지 않는 고정된 자리를 가지게 된다.

    5. sticky : 요소를 normal-flow(일반적인 흐름)에 따라 배치되고, top, right, bottom, left 속성들의 값을 기준으로 flow root 및 해당 element를 포함하는 containing block에 대한 상대적(relative) 위치에 배치된다. 그래서 sticky로 position을 지정했는데 top, right, bottom, left 속성이 주어지지 않으면 static으로 배치되는 위치와 같다.

    ##### [fixed와 sticky의 차이점]
    - fixed와 sticky 둘 다 스크롤을 하더라도 보이는 공통점을 가지고 있는데, 이 두 position의 차이점은 fixed는 문서의 흐름을 따르지 않고 뷰포트를 기준으로 배치가 되는 반면 sticky는 문서의 흐름(normal flow)을 따르면서 containing box를 기준으로 상대적인 위치에 배치된다. 따라서 fixed를 쓰면 요소들이 겹쳐 보일 수 있는 상황이 나올 수 있는 반면 sticky를 쓰면 그러한 상황을 예방할 수 있다. 

#### [float 속성]
- float : ‘띄우다’라는 뜻으로 원래 웹페이지에서 이미지를 어떻게 띄워서 텍스트와 함께 배치할 것인가에 대한 속성
- 속성값
    - inherit : 부모 요소에서 상속
    - left : 요소가 자신의 포함(containing) 블록의 좌측에 부동(float)해야 함을 나타내는 키워드
    - right : 요소가 자신의 포함 블록의 우측에 부동해야 함을 나타내는 키워드
    - none : 요소가 부동하지 않아야 함을 나타내는 키워드
    - inline-start : 요소가 자신의 포함 블록의 시작쪽에 부동해야함을 나타내는 키워드이다. ltr(left to right) 스크립트 상에서 왼쪽 그리고 rtl(right to left) 스크립트 상에서는 오른쪽
    - inline-end : 요소가 자신의 포함 블록의 끝쪽에 부동해야함을 나타내는 키워드이다. 즉, ltr(left to right) 상에서 오른쪽 그리고 rtl(right to left)상에서는 왼쪽

#### [float 해제]
1. 가상요소 ::after 사용
- float 속성을 적용한 요소의 부모요소에 ::after를 사용, inline의 가상요소를 만듦.
```css
clearfix::after {
	content: “”;
	display: block;
	clear: both;
	/*clear: both는 display: block만 사용가능*/
}
```
- 장점 : clearfix가 사용되는 곳마다 클래스를 가져다 조립하면됨.

2. overflow 사용
- float를 가진 요소의 부모 요소에 overflow: hidden 또는 overflow: auto를 적용
- overflow 속성을 사용할 경우 부모요소에 BFC가 생성되어, float 요소의 높이가 container 높이에 영향을 준다. BFC는 그 안에 만들어진 모든 요소를 포함하기 때문이다. (overflow 속성을 주면 넘치는 영역을 관리해야하기 때문에 우선적으로 자신의 높이를 알아야함)

3. 부모요소에게 height를 주는 경우
- float를 가진 요소의 부모 요소에 min-height 속성을 주는 경우, 높이가 fix되어 있기 때문에 콘텐츠 삽입시 문제가 될 수 있다.


</div> 
</details>


---
<details open>
<summary>3일차</summary>
<div markdown="3">

#### [웹 접근성을 고려한 텍스트 숨김처리]
- 콘텐츠의 영역마다 제목을 지정함으로써 스크린리더 등 보조기기 사용자가 웹 페이지를 이용하면서 콘텐츠를 이해하는데 도움을 받을 수 있다. 이렇게 heading 태그를 이용하여 각 영역에 제목을 입력하면 시각장애인의 사이트 탐색이 용이하고, 사이트의 컨텐츠에 대한 이해를 높일 수 있기 때문에 텍스트를 넣어주는데 디자인상 필요없으므로 숨김처리를 해야한다.

- 텍스트를 숨기는 방법
  1. display: none
  - 이 값을 주게 되면, 영역에서 아예 사라지게 된다. 따라서 화면에서 안보일 뿐만 아니라 보조기기나 검색엔진이 접근하지 못하게 되어 스크린리더 사용자는 해당 요소의 텍스트를 들을 수 없다. 마찬가지로 input type=“hidden” 이나 visibility: hidden 속성 또한 화면에서 보이지 않게 처리되지만 웹 접근성을 전혀 고려하지 않은 방법이다.

  2. 요소의 크기를 0으로 하기
  ```css
  .offset{
    width: 0;
    height: 0;
    font-size: 0;
    line-height: 0;
  }
  ```
  - 요소의 크기를 0으로 만들면 화면에서 보이지 않지만, 일부 스크린리더의 경우 해당요소를 무시해서 읽지 않을 수 있기 때문에 접근성을 고려한다면 좋은 방법이 아니다.

  3. 불투명도(opacity)를 0으로 하기
  ```css
  .offset{
    opacity: 0;
  }
  ```
  - 이경우도 모바일이나 스크린리더에서 읽지 않으므로 좋지 않은 방법이다.

  4. text-indent : -9999px; 이용해서 화면에서 밀어내기
  - 이 방법은 form 또는 link와 같은 요소에 사용할 경우, 포커싱 되었을 때, 스크린 밖에 위치해 있기 때문에 정확한 위치를 표시할 수 없어 혼란을 줄 수 있고, SEO(검색 엔진 최적화)에도 좋지 않은 영향을 미칠 수 있다.

  5. position을 이용해서 화면에서 밀어내기
  ```css
  .offscreen {
	  position: absolute;
	  top: -9999px;
	  overflow: hidden;
  }
  ```
  - 이 방법은 스크린리더가 차례대로 웹을 탐색하다가 .offscreen 클래스가 적용된 영역을 읽을 때 top: -9999px; 속성값이 적용되면서 화면 스크롤이 상단으로 이동한다. 스크린리더가 읽는 곳이 화면에 보이지 않게 되면서 이용자는 콘텐츠를 이해하기 어렵게 된다. 때문에 이방법도 웹 접근성이 떨어지는 방법이다.

6. clip-path를 이용해서 숨기기

  - clip-path는 지정된 클리핑 범위의 바깥 부분을 숨겨주는 속성이다.
  ```css
  .a11y-hidden {
	  position: absolute;
  /* 레이아웃에 영향을 주지 않에 normal flow에서 해당 영역을 없앤다. */
	  width: 1px;
	  height: 1px;
  /* width, height 값을 최소한의 크기로 조절한다. */
	  margin: -1px;
  /* 화면상 아예 안나오게 한다. */
	  overflow: hidden;
  /* 1px이 넘는 텍스트는 보이지 않음 */
	  clip-path: polygon(0 0, 0 0, 0 0);
  /* 클리핑 범위를 모두 0으로 지정해서 요소를 숨긴다. */
  /* clip-path: inset(50%)를 해도 보이지 않는다. */
	  clip: rect(0,0,0,0);
	  clip: rect(0 0 0 0);
  /* clip-path 속성이 IE11이하에서는 지원하지 않기 때문에 하위호환성을 위해 사용*/ 
  /* IE 구형 브라우저에서는 ,를 인식하지 못할 수 있기 때문에 ,가 없는 값도 사용*/
  }
  ```
  - 이 방법은 화면에서 요소를 숨기고, 스크린 리더가 해당요소의 텍스트를 읽을 수 있으며 보조기기가 접근했을 때 화면 스크롤의 움직임을 막을 수 있다.
  - tip. .a11y-hidden 클래스를 만들고, 접근성을 고려하여 요소를 숨겨야 할 경우 클래스를 가져다 사용하자

[참고](https://velog.io/@ursr0706/%EC%9B%B9-%EC%A0%91%EA%B7%BC%EC%84%B1%EC%9D%84-%EA%B3%A0%EB%A0%A4%ED%95%98%EC%97%AC-%ED%85%8D%EC%8A%A4%ED%8A%B8-%EC%88%A8%EA%B8%B0%EA%B8%B0)



#### [clip-path 속성]
- 클리핑 : 다른 파트에서 정의한 요소의 일부를 제거하는 것을 말한다.
- 요소의 클리핑 범위를 지정한다. 클리핑 범위 안의 부분은 보여지고, 바깥은 숨겨진다.
- SVG 대신 CSS 클립 패스를 활용할 수 있지만, IE, Edge는 현재 지원하지 않는다. (IE12부터 지원)

[그 외 다양한 클리핑 범위](https://bennettfeely.com/clippy/)

#### [clip 속성]
- 이미지나 도형 등을 클리핑할 때 사용, IE8도 지원
- 클리핑 효과를 주기 위해서는 속성을 부여하는 개체의 position 속성이 absolute여야 한다.
- clip 속성은 사각형을 통한 클리핑 지원, clip-path는 다양한 도형을 통한 클리핑을 지원
- rect가 받는 인자는 마스킹되는 영역을 정의하는 것으로, (top, right, bottom, left)로 정의
- CSS만을 활용해서 도넛 그래프 등을 만들 때 유용하다.

[참고](https://blog.hyungsub.com/entry/CSS-clip-%EC%86%8D%EC%84%B1)

#### [CSS 상속]
- CSS의 3대 개념 : `상속`, `종속 Cascading`, `명시도(우선순위)`
- 상속(Inheritance) : 상위(부모, 조상)요소에 적용된 속성을 하위(자식, 자손)요소가 물려받는 것을 의미한다. 
- 모든 속성이 상속되는 것이 아니고, 상속이 되는 것가 되지 않는 것이 있다.
- 상속이 되는 속성 : `visibility`, `opacity`, `font`, `color`, `line-height`, `text-align`, `white-space` 등
- 상속이 되지 않는 속성 : width, height, margin, padding, border, box-sizing, display, background, vertical-align, text-decoration, position, offset(top, right, bottom, left), z-index, overflow, float 등
- color는 상속되는 속성으로서 자식요소는 물론 자손요소까지 적용된다. 하지만, button처럼 요소에 따라 상속 받지 않는 경우도 존재한다. 이런 경우(상속되지 않는 경우) 상속받지 않는 요소 또는 상속되지 않는 속성에 inherit 키워드를 사용하여 명시적으로 상속 받을 수 있다.

#### [캐스케이딩, Cascading]
- 요소는 하나 이상의 CSS 선언에 영향을 받을 수 있다. 이때 충돌을 피하기 위해 CSS 적용 우선순위가 필요한데 이를 캐스케이딩(Cascading Order)이라고 한다.
- 캐스케이딩에는 3가지 규칙이 있다.

  ##### [중요도]
  - CSS가 어디 선언 되었는지에 따라서 우선순위가 달라진다.
  1. head 요소 내의 style 요소
  2. head 요소 내의 style 요소 내의 @import문
  3. <link>로 연결된 CSS파일
  4. <link>로 연결된 CSS파일 내의 @import문
  5. 브라우저 디폴트 스타일시트

  ##### [명시도]
  - 대상을 명확하게 특정할수록 명시도가 높아지고 우선순위가 높아진다.
  - !important > 인라인 스타일 > 아이디 선택자 > 클래스/어트리뷰트/가상 선택자 > 태그 선택자 > 전체 선택자 > 상위 요소에 의해 상속된 속성

  ##### [선언순서]
  - 선언된 순서에 따라 우선순위가 적용된다. 즉, 나중에 선언된 스타일이 우선 적용된다.

#### [tabindex]
- tab키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정
- 대화형(Interactive Content)는 기본적으로 코드 순서대로 탭 순서가 지정
- 비대화형 콘텐츠에 tabindex=“0”을 지정하여 대화형 콘텐츠와 같이 탭순서를 사용
- tabindex=“-1”을 통해 포커스는 가능하지만, 탭순서에서 제외 가능
- tabindex=“1” 이상의 양수 값은 논리적 흐름을 방해하기 때문에 비추천

  ##### [대화형 콘텐츠]
  - 사용자와의 상호작용을 위해 특별하게 설계된 요소를 포함
  - a, button, datalist, embed, iframe, keygen, label, select, textarea 등
  - <audio> controls 속성을 가진 경우
  - <img> usemap 속성을 가진 경우
  - <input> type 속성이 hidden이 아닌 경우
  - <menu> type 속성이 toolbar에 속한 경우
  - <object> usemap 속성을 가진 경우
  - <video> controls 속성을 가진 경우

#### [button 속성]
- 선택 가능한 버튼을 지정
- display : inline-block
- box-sizing: border-box, 브라우저별로 크기는 같지만 padding, border가 다름(padding의 재정의가 필요)
- 속성값
  - autofocus 속성 : 페이지가 로드될 때 자동으로 포커스(문서 내 고유해야함)
  - disabled 속성 : 버튼을 비활성화
  - form 속성 : <form>의 id 속성값(해당 <form>의 후손이 아닐 경우만)
  - name 속성 : 폼 데이터와 함께 전송되는 버튼의 이름
  - type 속성 : 버튼의 타입, button, reset, submit(기본값은 submit)

#### [box-shadow 속성]
- 요소의 테두리를 감싼 그림자 효과를 추가한다.
- box-shadow: offset-x offset-y blur-radius spread-radius color;
- 콘텐트 상자크기에 영향을 주지 않는다.

#### [text-shadow 속성]
- text에 그림자를 추가한다.
- text-shadow: offset-x offset-y blur-radius color

#### [background: linear-gradient() 함수]
- background: linear-gradient() 함수는 두 개 이상의 색이 직선을 따라 점진적으로 변화하는 이미지를 생성한다.
- 속성값
  1. <side-or-corner> 
  - 그라디언트 축의 시작점, 지정할 경우 to 이후 최대 두 개의 방향을 나타내는 키워드를 사용할 수 있다. 하나는 수평방향(left or right)이고, 다른 하나는 수직방향(top or bottom)이다. 방향 키워드의 순서는 상관하지 않으며, 기본값은 to bottom이다.
  - to top, to bottom, to left, toright 값은 0deg, 180deg, 270deg, 90deg와 같다.

  2. <angle>
  - 그라디언트 축의 방향, 0deg는 to top과 같다. 0이상의 값을 지정하면 축이 시계방향으로 돌아간다.

  3. <linear-color-stop>
  - 색상 정지점의 <color>값과 하나 혹은 두 개 선택적인 정지점 위치(각각 그라디언트 축 위의 % 또는 length)

  4. color-hint 
  - 두 인접한 색상 정지점 사이에서 그라디언트가 진행하는 방식을 지정하는 힌트이다. 길이는 두 정지점 간의 길이에서 어느 지점에 그 중간색이 도달해야 하는지 지정한다. 생략할 경우 가운데 중간색에 도달

- 예제
```css
/* 45도 기울어진 파랑 시작 빨강 종료 그라디언트 */
linear-gradient(45deg, blue, red);

/* 우하단에서 좌상단으로, 파랑 시작 빨강 종료 그라디언트 */
linear-gradient(to left top, blue, red);
```
[참고, 화면에서 만든 그라디언트를 코드로 생성, CSS Gradient Generator](https://www.colorzilla.com/gradient-editor/)

#### [CSS currentColor]
- CSS3에서 도입된 개념으로 currentColor 키워드가 설정되면, color값이 상속됨
```css
div {
	color: red;
	border: 5px solid currentColor;
	box-shadow: 0 0 5px solid currentColor;
}
```
#### [focus-visible]
- 접근성 높은 웹사이트를 만들기 위해 고려해야 하는 것 중 하나는 키보드‘만’ 이용해도 사이트를 정상적으로 이용할 수 있어야한다. 시각장애나 신체장애를 가진 사용자는 키보드(혹은 그와 비슷한 장치)를 이용해 웹사이트를 이용해야 하는 경우가 많기에, 키보드로 선택한 요소에 하이라이트를 줄 필요가 있다. 

```css
a, input, button {
	outline: 0;
}

:focus {
	outline: 0;
}
/* 위 CSS코드와 같이 특정 요소나 :focus의 outline을 지워버리는 방식은 키보드만으로 브라우저를 조작해야하는 사람을 완전히 배제해버리는 디자인이므로 지양하자. */
```
- focus-visible의 추가로, 간단하게 디자인과 접근성을 살릴 수 있게 되었다. 이 클래스는 :focus와 달리 키보드로 해당 요소를 선택해야만 적용된다.

```css
:focus-visible {
	outline: 3px solid #aaa;
}

:focus:not(:focus-visible) {
	outline: 0;
	/* :focus-visible이 아닌 :focus만 outline: 0 적용*/
}
```
- 아직 :focus-visible을 지원하는 브라우저가 많지 않기 때문에 WICG의 focus visibloe을 이용하면 지원범위를 넓힐 수 있다. 라이브러리만 추가하면 CSS는 상술한 내용과 크게 다르지 않다.
```css
	.js-focus-visible :focus:not(.focus-visible) {
    		outline: none;
	}
```
[참고, WICG의 focus visible](https://github.com/WICG/focus-visible)
[출처](https://marshall-ku.com/web/tips/focus-visible%EB%A1%9C-%EC%A0%91%EA%B7%BC%EC%84%B1-%EB%86%92%EC%9D%B4%EA%B8%B0)


[:focus-within]
- Dropdown 메뉴처럼 마우스를 올려야 표시되는 메뉴도 :focus-within을 이용해 접근성을 높일 수 있다.

```css
.dropdown{
	display: none;
}

.dropdown:hover{
	display: block;
}

.dropdown.hover{
	display: block;
}
```
- Dropdown 메뉴 안에 있는 요소에 outline을 아무리 추가해도 마우스를 올리지 않으면 메뉴가 표시조차 되지 않으니, 키보드론 절대로 선택할 수 없는 요소가 탄생해버린다. 심지어 display: none이 아니라 opacity: 0등으로 숨겨두었다면 키보드로 선택은 되지만 보이지 않는 요소가 탄생한다.

```css
.dropdown:focus,
.dropdown:focus-within {
    display: block;
/*해당 메뉴에 포커스가 가거나. 해당 메뉴의 자식에 포커스가 가면 메뉴를 표시하는 방법*/
}
```

#### [white-space 속성]
- 요소가 공백문자를 처리하는 법을 지정
- 속성값
|                | 개행문자 | 스페이스, 탭 | 자동 줄바꿈 | 줄 끝의 공백 |
| -------------- | -------- | ------------ | ----------- | ------------ |
| `normal`       | 병합     | 병합         | O           | 제거         |
| `nowrap`       | 병합     | 병합         | X           | 제거         |
| `pre`          | 유지     | 유지         | X           | 유지         |
| `pre-wrap`     | 유지     | 유지         | O           | 넘침         |
| `pre-line`     | 유지     | 병합         | O           | 제거         |
| `break-spaces` | 유지     | 유지         | O           | 줄 바꿈      |


#### [icon 삽입 방법]
1. 가상요소를 이용한 삽입
```css
.sub-menu a::before {
    content: '\f192';
    /* ‘\’가 있으면 기본적으로 스크린 리더기에서 읽히지 않음 */
    font-family: 'fontello';
    display: inline-block;
    /* width값을 가지기 위하여 display: inline-block */
    /* text-decoration: inherit; */
    width: 1em;
    margin-right: .2em;
}
```

2. `<span>` 이용한 삽입
```html
<span class="icon-right-open" aria-hidden="true"></span>
<!-- aria-hidden="true"을 줘서 스크린 리더기에서도 읽히지 않게 -->
```

</div> 
</details>

---
