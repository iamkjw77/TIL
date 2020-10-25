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

