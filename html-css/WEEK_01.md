## HTML
<details open>
<summary>1일차</summary>
<div markdown="1">

#### [HTML 정의]
- `HTML(HyperText Markup Language)` : 웹 페이지를 위한 지배적인 마크업 언어
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
<br />
- WCAG(Web Content Accessibility Guidelines) : 웹 사이트/애플리케이션에서 충족해야 하는 기준을 정의하여 장애가 있는 사용자가 보다 쉽게 이용할 수 있도록 준수해야 하는 지침
<br />
- WAI-ARIA : WAI(Web Accessibility Initiative) - ARIA(Accessible Rich Internet Applications), 여기서 RIA란, 정적인 HTML과 단순한 자바스크립트 환경의 웹이 아닌 동적인 자바스크립트와 Ajax와 같은 기술을 사용한 환경에서 수준높은 UX(User eXperience)를 제공하는 웹 애플리케이션이다.
<br />
- RIA는 화려하고 편리한 웹 애플리케이션이지만 스크린리더와 같은 보조기술을 사용하는 장애인들이 접근하기에 취약하다. 때문에 WAI-ARIA는 RIA에서 스크린리더기 및 보조기기 등에서 접근성 및 상호 운용성을 향상시키기 위한 목적으로 탄생되었으며 웹 애플리케이션에 역할(Role), 속성(Property), 상태(State) 정보를 추가하여 이를 개선 할 수 있도록 제공하고 있다.
<br />
- role 속성 : 웹 접근성을 위해 나왔으며 위젯, 구조 및 동작에 대한 의미 정보를 올바르게 전달하기 위해 나옴, 가장 많이 사용하는 곳은 의미없이 묶는 태그인 `<div>`
- role 속성은 기존에 있던 태그를 변경하려는 목적으로 사용하면 안됨
<br />
- Skip Navigation : 건너뛰기 링크는 말 그대로 ‘링크’를 건너뛰기 위해 제공되는 메뉴를 의미합니다. 여기서 ‘링크’라는 것은 매 페이지마다 반복적으로 제공되는 링크를 말하며, 건너뛰기 링크는 이를 건너뛰어 바로 본문으로 포커스를 이동할 수 있게 해주는 역할, 사용자 특히 장애인이 반복적인 링크들로 인해 불편해 하지 않고, 원하는 영역 즉 ‘본문’으로 바로 이동할 수 있는 건너뛰기 링크를 반드시 제공해야만 한다.

#### [aria 속성]
- aria-current : 현재 맥락과 일치하는 항목을 의미
token의 값은 page, step, location, date, time, true, false(default)으로 정해져 있고 이 중 하나만 사용할 수 있습니다.
<br />
- aria-selected : 단일 속성 또는 다중 선택이 가능한 요소에 한하여 선택상태를 명시하는 용도로 사용, 키보드 초점을 받을 수 있는 요소에 적용해야한다.
<br />
- aria-haspopup : 연결되어 있는 팝업(메뉴, 대화상자) 정보를 제공한다. 팝업은 다른 내용 위에 표시하는 블록을 의미한다.
<br />
- aria-expanded : 제어 대상의 확장 또는 축소상태를 나타낸다. 어코디언, 메뉴, 콤보박스, 트리와 같이 하위 그룹(또는 독립적인) 내용을 토글(열기, 닫기)하는 경우에 사용하면 적절하다. 독립적인 내용을 제어할 때 aria-controls 속성을 이용하여 제어 대상을 명시해야함.
<br />
- aria-pressed : aria-presses 속성은 토글 버튼(button, role=“button”)이 눌린 상태를 표시한다. 흔하게 사용하는 속성은 아니다. 이속성을 사용하기 전에 aria-selected 속성을 먼저 검토하는 것이 좋다.
<br />
- aria-hidden : 접근성 API(보조기기 접근 가능성) 차단 상태를 결정한다. 화면에 표시하지만 잠시 사용을 제한하는 콘텐츠에 사용
<br />
- aria-invalid : 주로 input 요소에 선언하여 사용자가 입력한 값이 요구하는 형식과 일치하는지 여부를 나타낸다.
<br />
- aria-controls : 현재 요소가 제어하는 대상을 명시하는 속성
- aria-live : 실시간으로 내용을 갱신하는 영역을 의미
- aria-labelledby : aria-labelledby, aria-label, aria-describedby 속성은 모두 현재 요소에 설명을 제공하는 속성
<br />
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
<br />
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
    3. HSL 실린더형 좌표계 사용(`hsl()`, `hsla()`의 함수형 표기법)

    ##### [color 값 키워드]
    - `transparent` : 완전히 투명색으로 색을 입힌 항목의 뒤편이 보인다. 기술적으로 transparent는 rbga(0, 0, 0, 0)의 짧은 이름
    - `currentColor` : 요소의 color 속성값을 나타낸다. 이를 통해 다른 속성이 color 속성값을 따라가도록 설정할 수 있다. color 속성의 값으로 currentColor 키워드를 사용하면, 값을 상속받은 color 속성에서 대신 가져온다.

#### [box-sizing 속성]
- 요소의 너비와 높이를 계산하는 방법을 지정
- CSS 박스 모델 기본값에서, 요소의 테두리나 안쪽 여백이 있으면 너비와 높이가 더해져 화면에 그려진다. 따라서 크기를 설정할　때, 원하는 크기를 얻으려면 테두리나 안쪽 여백을 고려해야 한다.
- `content-box` : 기본값 (content 상자 기준)
- `border-box` : 테두리와 안쪽 여백의 크기도 요소의 크기로 고려한다. (border 기준)
width, height = border + padding + content

#### [justify-content 속성]
- flexbox의 주기능 중 하나는 (주축과 교차축으로 표현되는) flex container 공간 안에 flex항목들을 정렬하고 여유 공간을 항목 간에 분배하는 것
- justify-content 속성은 주축에 따라 flex 항목 행을 정렬하는 방식을 지정
- 속성값
    - `flex-start` : flex 항목 행 내의 항목들이 flex 컨테이너의 시작선에서부터 정렬(기본값)
    - `flex-end` : flex 항목 행의 마지막 항목이 flex container의 끝선에 정렬
    - `center` : flex 항목들이 flex 항목 행의 가운데 정렬
    - space-between : 주축 방향 여유 공간을 flex항목 사이 공간에 균등 배분
    - `space-around` : 시작선과 끝선, flex 항목 간 공간을 균등 배분에 고려하여, 시작선 및 끝선과 flex 항목 간의 공간 크기를 1로 배분한다면, flex 항목 사이의 공간은 2로 배분 
    - `space-evenly` : 여유 공간을 flex 항목 사이의 공간 및 시작선과 끝선과 flex 항목 간의 공간에 모두 균등하게 배분
 
[flex 게임](https://flexboxfroggy.com/#ko)

#### [position 속성]
- 문서 상에 요소를 배치하는 방법을 지정, top, right, bottom, left 속성이 요소를 배치할 최종위치를 결정
- 속성값
    1. `static` : 요소를 normal-flow(일반적인 흐름)에 따라 배치, top, right, bottom, left, z-index 속성이 아무런 영향을 주지않는 기본값

    2. `relative` :  요소를 normal-flow에 따라 배치하고, 자기 자신을 기준으로 top, right, bottom, left 값에 따라 offset을 적용
        - ※ offset : 동일 오브젝트 안에서 오브젝트 처음부터 주어진 요소나 지점까지의 변위차를 나타내는 정수형
        - ex) 문자열 S의 배열이 ‘abcdef’ 라면 에서 ‘c’문자는 문자열 S의 시작점에서 2의 오프셋을 지닌다고 할 수 있다. 

    3. `absolute` : 요소를 normal-flow(일반적인 흐름)에서 제거하고, 페이지 레이아웃에 공간도 남아있지 않는다. 대신 가장 가까운 위치 지정 요소에 대해 상대적으로 배치한다. 단 조사 중 위치 조정 요소가 없다면 초기 컨테이닝 블록을 기준으로 삼는다. 최종 위치는 top, right, bottom, left값이 지정한다.

    4. `fixed` : 요소를 normal-flow(일반적인 흐름)에서 제거하고, 페이지 레이아웃에 공간도 배정하지 않는다. 대신, 스크린의 뷰포트(viewport)를 기준으로 한 위치에 배치된다. 즉, 스크롤되어도 움직이지 않는 고정된 자리를 가지게 된다.

    5. `sticky` : 요소를 normal-flow(일반적인 흐름)에 따라 배치되고, top, right, bottom, left 속성들의 값을 기준으로 flow root 및 해당 element를 포함하는 containing block에 대한 상대적(relative) 위치에 배치된다. 그래서 sticky로 position을 지정했는데 top, right, bottom, left 속성이 주어지지 않으면 static으로 배치되는 위치와 같다.

    ##### [fixed와 sticky의 차이점]
    - `fixed`와 `sticky` 둘 다 스크롤을 하더라도 보이는 공통점을 가지고 있는데, 이 두 position의 차이점은 fixed는 문서의 흐름을 따르지 않고 뷰포트를 기준으로 배치가 되는 반면 sticky는 문서의 흐름(normal flow)을 따르면서 containing box를 기준으로 상대적인 위치에 배치된다. 따라서 fixed를 쓰면 요소들이 겹쳐 보일 수 있는 상황이 나올 수 있는 반면 sticky를 쓰면 그러한 상황을 예방할 수 있다. 

#### [float 속성]
- `float` : ‘띄우다’라는 뜻으로 원래 웹페이지에서 이미지를 어떻게 띄워서 텍스트와 함께 배치할 것인가에 대한 속성
- 속성값
    - `inherit` : 부모 요소에서 상속
    - `left` : 요소가 자신의 포함(containing) 블록의 좌측에 부동(float)해야 함을 나타내는 키워드
    - `right` : 요소가 자신의 포함 블록의 우측에 부동해야 함을 나타내는 키워드
    - `none` : 요소가 부동하지 않아야 함을 나타내는 키워드
    - `inline-start` : 요소가 자신의 포함 블록의 시작쪽에 부동해야함을 나타내는 키워드이다. ltr(left to right) 스크립트 상에서 왼쪽 그리고 rtl(right to left) 스크립트 상에서는 오른쪽
    - `inline-end` : 요소가 자신의 포함 블록의 끝쪽에 부동해야함을 나타내는 키워드이다. 즉, ltr(left to right) 상에서 오른쪽 그리고 rtl(right to left)상에서는 왼쪽

#### [float 해제]
1. 가상요소 `::after` 사용
- float 속성을 적용한 요소의 부모요소에 ::after를 사용, inline의 가상요소를 만듦.
```css
clearfix::after {
	content: “”;
	display: block;
	clear: both;
	/*clear: both는 display: block만 사용가능*/
}
```
- 장점 : `clearfix`가 사용되는 곳마다 클래스를 가져다 조립하면됨.

2. `overflow` 사용
- `float`를 가진 요소의 부모 요소에 `overflow: hidden` 또는 `overflow: auto`를 적용
- `overflow` 속성을 사용할 경우 부모요소에 BFC가 생성되어, `float` 요소의 높이가 container 높이에 영향을 준다. BFC는 그 안에 만들어진 모든 요소를 포함하기 때문이다. (`overflow` 속성을 주면 넘치는 영역을 관리해야하기 때문에 우선적으로 자신의 높이를 알아야함)

3. 부모요소에게 `height`를 주는 경우
- `float`를 가진 요소의 부모 요소에 `min-height` 속성을 주는 경우, 높이가 fix되어 있기 때문에 콘텐츠 삽입시 문제가 될 수 있다.


</div> 
</details>


---
<details open>
<summary>3일차</summary>
<div markdown="3">

#### [웹 접근성을 고려한 텍스트 숨김처리]
- 콘텐츠의 영역마다 제목을 지정함으로써 스크린리더 등 보조기기 사용자가 웹 페이지를 이용하면서 콘텐츠를 이해하는데 도움을 받을 수 있다. 이렇게 heading 태그를 이용하여 각 영역에 제목을 입력하면 시각장애인의 사이트 탐색이 용이하고, 사이트의 컨텐츠에 대한 이해를 높일 수 있기 때문에 텍스트를 넣어주는데 디자인상 필요없으므로 숨김처리를 해야한다.

- 텍스트를 숨기는 방법
  1. `display: none`
  - 이 값을 주게 되면, 영역에서 아예 사라지게 된다. 따라서 화면에서 안보일 뿐만 아니라 보조기기나 검색엔진이 접근하지 못하게 되어 스크린리더 사용자는 해당 요소의 텍스트를 들을 수 없다. 마찬가지로 `input type=“hidden”` 이나 `visibility: hidden` 속성 또한 화면에서 보이지 않게 처리되지만 웹 접근성을 전혀 고려하지 않은 방법이다.


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


  4. `text-indent : -9999px;` 이용해서 화면에서 밀어내기
  - 이 방법은 form 또는 link와 같은 요소에 사용할 경우, 포커싱 되었을 때, 스크린 밖에 위치해 있기 때문에 정확한 위치를 표시할 수 없어 혼란을 줄 수 있고, SEO(검색 엔진 최적화)에도 좋지 않은 영향을 미칠 수 있다.


  5. `position`을 이용해서 화면에서 밀어내기
  ```css
  .offscreen {
	  position: absolute;
	  top: -9999px;
	  overflow: hidden;
  }
  ```
  - 이 방법은 스크린리더가 차례대로 웹을 탐색하다가 .offscreen 클래스가 적용된 영역을 읽을 때 `top: -9999px;` 속성값이 적용되면서 화면 스크롤이 상단으로 이동한다. 스크린리더가 읽는 곳이 화면에 보이지 않게 되면서 이용자는 콘텐츠를 이해하기 어렵게 된다. 때문에 이방법도 웹 접근성이 떨어지는 방법이다.


6. `clip-path`를 이용해서 숨기기

  - `clip-path`는 지정된 클리핑 범위의 바깥 부분을 숨겨주는 속성이다.
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
  - tip. `.a11y-hidden` 클래스를 만들고, 접근성을 고려하여 요소를 숨겨야 할 경우 클래스를 가져다 사용하자

[참고](https://velog.io/@ursr0706/%EC%9B%B9-%EC%A0%91%EA%B7%BC%EC%84%B1%EC%9D%84-%EA%B3%A0%EB%A0%A4%ED%95%98%EC%97%AC-%ED%85%8D%EC%8A%A4%ED%8A%B8-%EC%88%A8%EA%B8%B0%EA%B8%B0)



#### [clip-path 속성]
- 클리핑 : 다른 파트에서 정의한 요소의 일부를 제거하는 것을 말한다.
- 요소의 클리핑 범위를 지정한다. 클리핑 범위 안의 부분은 보여지고, 바깥은 숨겨진다.
- SVG 대신 CSS 클립 패스를 활용할 수 있지만, IE, Edge는 현재 지원하지 않는다. (IE12부터 지원)

[그 외 다양한 클리핑 범위](https://bennettfeely.com/clippy/)

#### [clip 속성]
- 이미지나 도형 등을 클리핑할 때 사용, IE8도 지원
- 클리핑 효과를 주기 위해서는 속성을 부여하는 개체의 `position` 속성이 `absolute`여야 한다.
- `clip` 속성은 사각형을 통한 클리핑 지원, `clip-path`는 다양한 도형을 통한 클리핑을 지원
- `rect`가 받는 인자는 마스킹되는 영역을 정의하는 것으로, (top, right, bottom, left)로 정의
- CSS만을 활용해서 도넛 그래프 등을 만들 때 유용하다.

[참고](https://blog.hyungsub.com/entry/CSS-clip-%EC%86%8D%EC%84%B1)

#### [CSS 상속]
- CSS의 3대 개념 : `상속`, `종속 Cascading`, `명시도(우선순위)`
<br />
- `상속(Inheritance)` : 상위(부모, 조상)요소에 적용된 속성을 하위(자식, 자손)요소가 물려받는 것을 의미한다. 
- 모든 속성이 상속되는 것이 아니고, 상속이 되는 것가 되지 않는 것이 있다.
<br />
- 상속이 되는 속성 : `visibility`, `opacity`, `font`, `color`, `line-height`, `text-align`, `white-space` 등
- 상속이 되지 않는 속성 : `width`, `height`, `margin`, `padding`, `border`, `box-sizing`, `display`, `background`, `vertical-align`, `text-decoration`, `position`, `offset(top, right, bottom, left)`, `z-index`, `overflow`, `float` 등
<br />
- `color`는 상속되는 속성으로서 자식요소는 물론 자손요소까지 적용된다. 하지만, `button`처럼 요소에 따라 상속 받지 않는 경우도 존재한다. 이런 경우(상속되지 않는 경우) 상속받지 않는 요소 또는 상속되지 않는 속성에 `inherit` 키워드를 사용하여 명시적으로 상속 받을 수 있다.
<br />
#### [캐스케이딩, Cascading]
- 요소는 하나 이상의 CSS 선언에 영향을 받을 수 있다. 이때 충돌을 피하기 위해 CSS 적용 우선순위가 필요한데 이를 `캐스케이딩(Cascading Order)`이라고 한다.
- 캐스케이딩에는 3가지 규칙이 있다.

  ##### [중요도]
  - CSS가 어디 선언 되었는지에 따라서 우선순위가 달라진다.
  1. `head` 요소 내의 `style` 요소
  2. `head` 요소 내의 `style` 요소 내의 `@import`문
  3. `<link>`로 연결된 CSS파일
  4. `<link>`로 연결된 CSS파일 내의 `@import`문
  5. 브라우저 디폴트 스타일시트

  ##### [명시도]
  - 대상을 명확하게 특정할수록 명시도가 높아지고 우선순위가 높아진다.
  - `!important > 인라인 스타일 > 아이디 선택자 > 클래스/어트리뷰트/가상 선택자 > 태그 선택자 > 전체 선택자 > 상위 요소에 의해 상속된 속성`

  ##### [선언순서]
  - 선언된 순서에 따라 우선순위가 적용된다. 즉, 나중에 선언된 스타일이 우선 적용된다.

#### [tabindex]
- tab키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정
- 대화형(Interactive Content)는 기본적으로 코드 순서대로 탭 순서가 지정
- 비대화형 콘텐츠에 `tabindex=“0”`을 지정하여 대화형 콘텐츠와 같이 탭순서를 사용
- `tabindex=“-1”`을 통해 포커스는 가능하지만, 탭순서에서 제외 가능
- `tabindex=“1”` 이상의 양수 값은 논리적 흐름을 방해하기 때문에 비추천

  ##### [대화형 콘텐츠]
  - 사용자와의 상호작용을 위해 특별하게 설계된 요소를 포함
  - a, button, datalist, embed, iframe, keygen, label, select, textarea 등
  - `<audio>` controls 속성을 가진 경우
  - `<img>` usemap 속성을 가진 경우
  - `<input>` type 속성이 hidden이 아닌 경우
  - `<menu>` type 속성이 toolbar에 속한 경우
  - `<object>` usemap 속성을 가진 경우
  - `<video>` controls 속성을 가진 경우


#### [button 속성]
- 선택 가능한 버튼을 지정
- `display : inline-block`
- `box-sizing: border-box`, 브라우저별로 크기는 같지만 `padding`, `border`가 다름(padding의 재정의가 필요)
- 속성값
  - `autofocus` 속성 : 페이지가 로드될 때 자동으로 포커스(문서 내 고유해야함)
  - `disabled` 속성 : 버튼을 비활성화
  - `form` 속성 : `<form>`의 id 속성값(해당 `<form>`의 후손이 아닐 경우만)
  - `name` 속성 : 폼 데이터와 함께 전송되는 버튼의 이름
  - `type` 속성 : 버튼의 타입, `button`, `reset`, `submit`(기본값은 submit)


#### [box-shadow 속성]
- 요소의 테두리를 감싼 그림자 효과를 추가한다.
- `box-shadow: offset-x offset-y blur-radius spread-radius color`;
- 콘텐트 상자크기에 영향을 주지 않는다.


#### [text-shadow 속성]
- text에 그림자를 추가한다.
- `text-shadow: offset-x offset-y blur-radius color`


#### [background: linear-gradient() 함수]
- 두 개 이상의 색이 직선을 따라 점진적으로 변화하는 이미지를 생성
- 속성값
  1. `<side-or-corner>` 
  - 그라디언트 축의 시작점, 지정할 경우 to 이후 최대 두 개의 방향을 나타내는 키워드를 사용할 수 있다. 하나는 수평방향(left or right)이고, 다른 하나는 수직방향(top or bottom)이다. 방향 키워드의 순서는 상관하지 않으며, 기본값은 to bottom이다.
  - to top, to bottom, to left, toright 값은 0deg, 180deg, 270deg, 90deg와 같다.

  2. `<angle>`
  - 그라디언트 축의 방향, 0deg는 to top과 같다. 0이상의 값을 지정하면 축이 시계방향으로 돌아간다.

  3. `<linear-color-stop>`
  - 색상 정지점의 `<color>`값과 하나 혹은 두 개 선택적인 정지점 위치(각각 그라디언트 축 위의 % 또는 length)

  4. `<color-hint>`
  - 두 인접한 색상 정지점 사이에서 그라디언트가 진행하는 방식을 지정하는 힌트이다. 길이는 두 정지점 간의 길이에서 어느 지점에 그 중간색이 도달해야 하는지 지정한다. 생략할 경우 가운데 중간색에 도달

- 예제
```css
/* 45도 기울어진 파랑 시작 빨강 종료 그라디언트 */
linear-gradient(45deg, blue, red);

/* 우하단에서 좌상단으로, 파랑 시작 빨강 종료 그라디언트 */
linear-gradient(to left top, blue, red);
```

#### [background: radial-gradient() 함수]
- 원형 그라데이션 효과를 만들 수 있다. 
- CSS3에서 추가된 것으로 IE10이상 사용 가능
- 사용법 
- `radial-gradient( shape size at position, color1, color2, ,,, , color3)`
- 속성값
  - `shape` : 원모양 인지 타원모양인지 선택
  - `size` : 크기를 정함
  - `position` : 중심의 위치를 정함
  - `color` : 색지정

```css
background: radial-gradient(ellipse at right top, red, yellow)
/* 오른쪽 상단에서 시작하는 그라디언트*/
```

[참고, 화면에서 만든 그라디언트를 코드로 생성, CSS Gradient Generator](https://www.colorzilla.com/gradient-editor/)

#### [CSS currentColor]
- CSS3에서 도입된 개념으로 `currentColor` 키워드가 설정되면, color값이 상속됨
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

- `focus-visible`의 추가로, 간단하게 디자인과 접근성을 살릴 수 있게 되었다. 이 클래스는 `:focus`와 달리 키보드로 해당 요소를 선택해야만 적용된다.

```css
:focus-visible {
	outline: 3px solid #aaa;
}

:focus:not(:focus-visible) {
	outline: 0;
	/* :focus-visible이 아닌 :focus만 outline: 0 적용*/
}
```

- 아직 `:focus-visible`을 지원하는 브라우저가 많지 않기 때문에 WICG의 focus visible을 이용하면 지원범위를 넓힐 수 있다. 라이브러리만 추가하면 CSS는 상술한 내용과 크게 다르지 않다.
```css
	.js-focus-visible :focus:not(.focus-visible) {
    		outline: none;
	}
```
[참고, WICG의 focus visible](https://github.com/WICG/focus-visible)
[출처](https://marshall-ku.com/web/tips/focus-visible%EB%A1%9C-%EC%A0%91%EA%B7%BC%EC%84%B1-%EB%86%92%EC%9D%B4%EA%B8%B0)



#### [:focus-within]
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

- Dropdown 메뉴 안에 있는 요소에 outline을 아무리 추가해도 마우스를 올리지 않으면 메뉴가 표시조차 되지 않으니, 키보드론 절대로 선택할 수 없는 요소가 탄생해버린다. 심지어 `display: none`이 아니라 `opacity: 0`등으로 숨겨두었다면 키보드로 선택은 되지만 보이지 않는 요소가 탄생한다.

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
  - `normal`
    - 연속 공백을 하나로 합침. 개행 문자도 다른 공백 문자와 동일하게 처리한다. 한 줄이 너무 길어서 넘칠 경우 자동으로 줄을 바꾼다.
  - `nowrap`
  - 연속 공백을 하나로 합침. 줄 바꿈은 `<br>` 요소에서만 일어난다.
  - `pre`
    - 연속 공백 유지. 줄 바꿈은 개행 문자와 `<br>` 요소에서만 일어난다.
  - `pre-wrap`
  - 연속 공백 유지. 줄 바꿈은 개행 문자와 `<br>` 요소에서 일어나며, 한 줄이 너무 길어서 넘칠 경우 자동으로 줄을 바꾼다.
  - `pre-line`
  - 연속 공백을 하나로 합침. 줄바꿈은 개행 문자와 `<br>` 요소에서 일어나며, 한 줄이 너무 길어서 넘칠 경우 자동으로 줄을 바꾼다.
  - `break-spaces`
  - 다음 차이점을 제외하면 `pre-wrap`과 동일
      - 연속 공백이 줄의 끝에 위치하더라도 공간을 차지한다.
      - 연속 공백의 중간과 끝에서도 자동으로 줄을 바꿀 수 있다.
      - 유지한 연속 공백은 `pre-wrap`과 달리 요소 바깥으로 넘치지 않으며, 공간도 차지하므로 박스의 본질 크기(min-content, max-content)에 영향을 준다.

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
<details open>
<summary>4일차</summary>
<div markdown="4">

#### [가상요소 선택자]
- 선택자에 추가하는 키워드로, 선택한 요소의 일부분에만 스타일을 입힐 수 있다.
- 요소박스 내에 가상요소는 한 번 밖에 사용할 수 없음(::before::before, ::after::after는 사용할 수 없음)
- 기본값은 `display: inline `
- `::after`, `::before`, `::marker`, `::backdrop`, `::part()`, `::placeholder`, `::selection` 등

```css
p::first-line {
	color: blue;
	text-transform: uppercase;
	/* 문단 첫 줄의 글씨체가 바뀜 */
}
```

- 규칙에 따라 단일 콜론(:)대신 이중 콜론(::)을 사용하여 가상요소와 가상클래스를 구별해야 한다. 하지만, 과거 W3C 명세에선 이런 구별법을 두지 않았으므로 대부분의 브라우저는 기존 가상 요소에 대해 두 구문 모두 지원한다.


#### [자주쓰는 특수문자]
- 특수문자가 포함된 경우 브라우저는 웹소스의 일부로 인식하여 결과가 다르게 나오는 경우가 있다.
- `<>`안에 코드 형식을 쓰고, 그대로 보여주고 싶어도 태그로 인식하여 화면에 표시가 안 되는 경우가 있다.

|특수문자|문자표현|
|------|------|
|<|`&lt;`|
|>|`&gt;`|
|&|`&amp;`|
|*|`&quot;`|
|#|`&num;`|
|;|`&semi;`|
|^|`&Hat;`|
|'|`&apos;`|
|space|`&nbsp;`|

#### [margin collapse, 마진 병합, 마진 상쇄]
- 여러 블록의 상하 바깥 여백(margin)은 경우에 따라 제일 큰 여백의 크기를 가진 단일 여백으로 결합(상쇄)된다. 
- 마진 상쇄는 인접한 두 박스가 온전한 block-level 요소일 경우에만 적용
- 마진 값이 0이더라도 상쇄 규칙은 적용
- 좌우 마진은 겹치더라도 상쇄되지 않는다.

#### [margin 상쇄가 일어나는 3가지 상황]
1. 인접 형제 박스 간 상하 마진이 겹칠 때
  - 겹쳐진 두 마진 값을 비교해, 더 큰 마진 값으로 랜더링한다. 만약 두 값이 동일하다면 둘 중 하나의 값으로(중복값)으로 랜더링된다.
[인접 형제간 상하마진](https://media.vlpt.us/post-images/raram2/97e16a40-121f-11ea-aaba-65695302c179/01-margin-collapsing-sibling-case.png)

2. 빈 요소의 상하 마진이 겹칠 때 
- “빈 요소”란 높이(height)가 0인 상태인 블록 요소를 말한다.
- `height/ min-hight / padding / border` 등 상하로 늘어나는 속성값을 명시적으로 주지 않았거나
- 내부에 `inline` 콘텐츠가 존재하지 않는 요소
- 이 경우 위와 아래를 가르는 경계가 없으므로, 자신의 상하 마진 값을 비교해 큰 값으로 상쇄된다. 만약 두 값이 동일할 경우, 중복값으로 상쇄된다. 특히 빈 요소와 인접 박스들 간에 margin 겹침이 일어나는 구조에서는 다음과 같이 상쇄가 여러번 발생한다.
[빈 요소의 상하마진](https://media.vlpt.us/post-images/raram2/ffac75c0-121f-11ea-aaba-65695302c179/02-margin-collapsing-emptybox-case.png)

3. 부모 박스와 첫 번째(마지막) 자식 박스의 상단(하단) 마진이 겹칠 때
- 브라우저는 부모박스와 첫 번째(마지막) 자식 박스 간의 경계를 그 사이에 있는 `border/padding/inline` 콘텐츠의 유무로 판단한다. 2번의 빈박스 마진 상쇄 현상과는 조금 다르게, 이미 명시적으로 `height / min-height` 값을 줬더라도 이번 경우에선 신경쓰지 않는다.
[부모 박스와 첫 번째 자식박스의 상단마진 박스](https://media.vlpt.us/post-images/raram2/3bc26dc0-1221-11ea-aaba-65695302c179/03-margin-collapsing-firstchild-case1.png)
[부모 박스와 마지막 자식 박스의 하단마진](https://media.vlpt.us/post-images/raram2/59ea9cf0-1221-11ea-aaba-65695302c179/06-margin-collapsing-lastchild-case.png)

- `그래서` 부모 박스 상단(하단)에 `padding` 또는 `border` 값을 주어 벽을 만들어주는 것이 안전하다. 
[안전한 방법](https://media.vlpt.us/post-images/raram2/62855f30-1221-11ea-aaba-65695302c179/07-margin-collapsing-recomm-case.png)

[참고](https://velog.io/@raram2/CSS-%EB%A7%88%EC%A7%84-%EC%83%81%EC%87%84Margin-collapsing-%EC%9B%90%EB%A6%AC-%EC%99%84%EB%B2%BD-%EC%9D%B4%ED%95%B4)

#### [margin 상쇄 규칙 예외]
- 박스가 `position: absolute` 된 상태
- 박스가 `float: left/right` 된 상태(단, clear 되지 않은 상태)
- 박스가 `display: flex` 일 때, 내부 flexbox item
- 박스가 `display: grid` 일 때, 내부 grid item

#### [animation 속성]
- 다수의 스타일을 전환하는 애니메이션을 적용
- `transition`보다 할 수 있는 것이 더 많다.
- `transition`은 시작하기 위해 이벤트가 필요하지만, `animation`은 시작, 정지, 반복까지 제어 가능
- 하나 또는 복수의 `@keyframs`로 이뤄짐
- `animation-name`, `animation-duration`, `animation-timing-function`, `animation-delay`, `animation-iteration-count`, `animation-direction`, `animation-fill-mode`, `animation-play-state`의 단축속성

```css
/* @keyframes duration | timing-function | delay | iteration-count | direction | fill-mode | play-state | name */
animation: 3s ease-in 1s 2 reverse both paused slidein;
```

#### [animation-fill-mode]
- CSS 애니메이션이 실행 전과 후에 대상에 스타일 적용하는 방법
- 속성값
	- `none` : 애니메이션이 실행되지 않을 때, 대상에 스타일을 적용X(기본값)
	- `forwards` : 대상은 실행된 애니메이션의 마지막 keyframe에 의해 설정된 값을 유지
	- `backwards` : 애니메이션 대상에 적용되는 즉시 첫 번째 관련 keyframs에 정의된 값을 적용
	- `both` : 애니메이션은 앞뒤 양쪽 모두의 규칙을 따르도록 애니메이션 속성이 양방향으로 확장

#### [animation-play-mode]
- 애니메이션의 진행상태를 설정
- 속성값
	- `running`(기본값) : 애니메이션을 움직이게 한다.
	- `paused` : 애니메이션의 움직임을 정지시킨다.
	- `inherit` : 애니메이션의 움직임을 상속받는다.

#### [transition 속성]
- 요소의 두 가지 상태 사이에 변화를 줄 수 있다.
- `transition-property`, `transition-duration`, `transition-timing-function`과 `transition-delay`의 단축속성
- `transition-property(transition-name)`, `transition-duration`은 필수속성
- 자동으로 발동되지 않음(가상클래스를 사용해 정의된 `:hover` or `:active` or 자바스크립트 같은 이벤트 트리거에 의해 동작)

```css
/* transition name | duration | timing function | delay */
transition: margin-left 4s ease-in-out 1s;
```

#### [transform 속성]
- 요소에 회전(rotate), 확대 축소(scale), 비틀기(skew), 이동효과(translate)를 부여할 수 있다.
- `transition`과 `animation`을 조합하여 사용하면 편리하다.
- `transform: 함수1 함수2 함수3`;

#### [animation 이동]
1. `transform: translate(0, 0) → transform: translate(400px, 75px)`
	- `translate`를 사용할 경우 가로 스크롤이 생길 수 있음
	- 해결법 : 요소에 `width`값을 준다.

2. `margin`을 줘서 이동하는 것처럼 보이게 하는 경우
	- `margin` 병합이 생길 수 있음, 이를 위한 조치가 필요

3. `padding`을 줘서 이동하는 것처럼 보이게 하는 경우
	- 요소에 배경이 없는 경우만 가능하다.

4. `position: relative`를 이용한 경우
	- 전체크기를 유지하면서 이동하기 때문에 가로스크롤이 생김	
	- 해결법 : 요소에 width값을 준다.

5. `position: absolute`를 쓰고, 부모에 `position: relative`를 주는 경우
	- `width`값을 주지 않아도 스크롤이 안생기고 잘 움직임


#### [CSS　성능]
- 위의 `animation` 이동측면에서, 성능을 생각하면 `translate()`를 사용, `translate`는 이동의 개념이기 때문에 `position`보다 성능이 좋음
- reflow : 생성된 DOM 노드의 레이아웃(너비, 높이 등) 변경 시 영향 받는 모든 노드(자식, 부모)의 수치를 다시 계산하여 렌더트리를 재생성하는 작업
- repaint : reflow 과정이 끝난 후, 재생성된 랜더트리를 다시 그리는 작업으로 수치와 상관없는 `background-color, visibility, outline` 등의 스타일 변경 시에는 reflow 과정이 생략된 repaint 작업만 수행한다.
- 레이아웃에 영향을 주는 스타일 height, margin등은 화면에 요소를 다시 그리기 때문에 reflow, repaint가 일어나 성능이 저하됨 

[CSS 성능 개선방법](https://wit.nts-corp.com/2017/06/05/4571)
[CSS 성능개선 사례](https://www.slideshare.net/wsconf/css-animation-wsconfseoul2017-vol2?qid=94336ada-5255-458e-8409-b37fe73ff911&v=&b=&from_search=3)

#### [투명도, opacity]
- `opacity : 0` // 요소의 내용을 포함해 모든 곳에 영향을 주지만, 상속되지는 않는다.(상자 전체가 투명해짐)
-`color : transparent` // 글자 색상만 투명해짐

#### [form 태그]
- 폼에 입력된 데이터를 한 번에 서버로 전송
- `<form>`이 다른 `<form>`을 자식요소로 포함할 수 없음
- `display: block`
- 속성
	- `action(필수)` : 폼을 전송할 서버 쪽 스크립트 파일을 지정
	- `name(필수)` : 폼을 식별하기 위한 이름 지정(DB쪽 name과 동일)
	- `method` : 폼을 서버에 전송할 HTTP 메소드를 정한다. (GET 또는 POST)
	- `target` : 서버로 전송 후 응답받을 방식을 지정(기본값: _self)
	- `autocomplete` : 사용자가 이전에 입력한 값으로 자동완성기능을 사용할 것인지 여부(기본값: on)
	- `novalidate` : 서버로 전송 시 양식 데이터의 유효성을 검사하지 않도록 지정
	  - ex) 이메일 형식이 맞지 않으면, 페이지가 넘어가지 않음(novalidate를 쓰면 검사X)

#### [fieldset 태그]
- `<fieldset>`태그는 `<form>`요소에서 연관된 요소들을 하나의 그룹으로 묶을 때 사용
- `<fieldset>`요소는 하나의 그룹으로 묶은 요소들 주변으로 박스모양의 선을 그려줌
- `<legend>`요소를 사용하면 `<fieldset>`요소의 캡션(caption)을 정의할 수 있음
- `<form>`과 `<fieldset>` 요소를 독립적으로 만든 후, `<form>`의 id 속성과 `<fieldset>`의 form 속성을 연결해 form 요소를 명시할 수 있음 
- XHTML에서는 `form>fieldset>legend` 구조가 필수이지만, HTML 4.01에서는 필수가 아님
- HTML5에서는 `form>fieldset>legend` 구조를 써도 되고, 쓰지 않아도 됨(둘 다 가능하지만 구조를 사용하자)
**`<form>`, `<fieldset>`은 디자인시 버그가 많으므로 주로, `<div>` 묶어서 디자인**


#### [input type 및 속성]
- 사용자에게 입력받을 데이터 양식(대화형 컨트롤)
- input type의 종류
	1. `button`
	2. `checked`
	3. `color (IE지원 불가)`
	4. `email`
	5. `file`
	6. `hidden`
	7. `image`
	8. `number`
	9. `password`
	10. `radio`
	11. `range`
	12. `reset`
	13. `search`
	14. `submit`
	15. `tel`
	16. `text`
	17. `url`

#### [input 태그 required]
- 폼 데이터(form data)가 서버로 제출되기 전 반드시 채워져 있어야 하는 입력 필드를 명시
- input 내용이 공란이면, 서버에 가기 전 `submit` 되지 않음 
- 불리언(boolean) 속성
- 불리언 속성은 해당 속성을 명시하지 않으면 자동으로 false 값을 가지게 되며, 명시하면 자동으로 true 값을 가짐

#### [label과 input의 연결]
- `label` : 사용자 인터페이스 항목의 설명을 나타냄
- `input` 요소는 1:1로 대응되는 `label`을 꼭 줘야 한다.
- `label`과 `input`은 연결하면, 스크린리더기에서 `input(폼 입력)`에서 `label`을 읽어서 사용자가 입력해야 하는 텍스트가 무엇인지 더 쉽게 이해할 수 있다.
- 연결하는 방법
	1. `label`의 `for` 속성과 `input`의 `id` 속성을 연결(명시적)
	2. `input` 요소 안에 `title` 속성을 주는 경우(명시적이긴 하지만 1번 방법을 쓰자)
	3. `label` 안에 `input`을 중첩(이 경우 암묵적이므로, `for` 및 `id` 속성이 필요 없음)
	
#### [text-indent]
- 블록(block) 요소에서 들여쓰기와 내어 쓰기
- 값이 양수이면 들여쓰기, 값이 음수이면 내어쓰기(기본값은 0)
- `inline` 요소는 사용 불가, `inline`은 `padding` 좌·우를 이용할 수 있음

</div> 
</details>

---
<details open>
<summary>5일차</summary>
<div markdown="5">

#### [CSS 함수]
- CSS에서 함수는 어떠한 요소의 속성값을 제어하는 역할을 한다.
- `attr()`, `calc()`, `hsl()`, `hsla()`, `linear-gradient()`, `radial-gradient()`. `rgb()`, `rgba()`. `polygon()`, `rotate()`, `scale()`, `skew()`, `translate()`, `inset()` 등이 있다.

#### [CSS의 진화, CSS-SASS-BEM-Module-styled 컴포넌트]
- `CSS` : 프로젝트 규모나 복잡도가 커질수록, 혹은 팀원들의 수가 많아질수록 기존 스타일이 영향을 받는 문제와 `!important`를 사용해서 UI요소가 특정한 방식으로 보이는 것을 강제하는 문제는 큰 문제들이 되었다.


- `SASS`의 구원 : SASS는 CSS를 네스팅(nesting), 변수, 믹스인, 확장, 로직 등을 장착한 전처리 엔진 형태의 프로그래밍언어로 변형시켰다. 이를 통해 CSS 파일들을 잘 구조화할 수 있게 되었고, 최소한 CSS 파일을 몇 개의 작은 파일로 분리할 수 있는 방법이 생겼다. 

- SASS는 본질적으로 SCSS 코드를 읽어서 전처리한 다음 컴파일해서 전역 CSS 번들파일을 만들어준다.

- SASS는 전처리기 내부에서 어떤 작업을 하는지 알지 못한 채 스타일이 겹치는 문제를 해결하기 위해 단순히 계층 구조를 만들어 내는 것어 의지하게 되었고, 그 결과 컴파일이된 CSS는 어마어마하게 커지게 되었다.(BEM이 등장하기 전)


- `BEM`과 컴포넌트 기반 사고 : BEM의 등장은 우리가 재사용성과 컴포넌트에 대해 생각할 수 있게 해주는 신선한 공기였다. BEM은 새로운 수준의 의미를 부여할 수 있게 해주고, 단순 블록(Block), 요소(Element), 변경자(Modifier) 컨벤션을 사용함으로써 클래스명이 유일함(unique)을 보장하여 스타일이 겹치는 위험성을 줄일 수 있게 해주었다.

- `BEM`의 문제점
	1. 클래스명 선택자가 장황해졌다.
	2. 긴 클래스명 때문에 마크업이 불필요하게 커졌다.
	3. 재사용하려고 할 때마다 모든 UI컴포넌트를 명시적으로 확장해야만 했다.
	4. 마크업이 불필요한 의미를 갖게 되었다.


- SASS와 BEM도 고치지 못했던 몇 가지 문제들은 언어 로직상에 진정한 캡슐화(encapsulation)의 개념이 없다는 것이고, 이로 인해 개발자들이 유일한 클래스명을 선택하는 것에 의존할 수밖에 없었다. 이런 과정은 컨벤션보다는 도구에 의해 해결되었다.


- `CSS Module` : 이것이 바로 CSS Module이 했던 일이다. 로컬단위로 정의된 모든 스타일에 동적으로 클래스명을 만들어내어 추가된 CSS 속성들에 의해 스타일이 겹치지 않도록 해주었다. CSS모듈은 React 생태계에서 빠르게 인기를 얻었으며, 이제 많은 React 프로젝트에 이를 사용하고 있는 것을 흔히 볼 수 있다. CSS Module 또한 나름의 장점과 단점이 있지만 전반적으로 사용하기에 좋은 패러다임이라는 것이 증명되었다.


- 하지만, CSS Module 자체로는 CSS의 핵심 문제들을 해결하지 못했는데, 이는 단지 스타일 정의를 로컬화 할 수 있는 방법을 보여주었을 뿐이었다. 그 방법이란 바로 BEM을 자동화함으로써 더 이상 클래스명을 결정하기 위해 고민할 필요가 없게 하는 것이었다.


- CSS 모듈 역시 쉽게 확장이나 재사용이 가능하고, 최소한의 노력으로 제어가 가능한 더 예측 가능한 아키텍쳐의 필요성을 완화시켜주지는 못했다.
- 로컬 모듈은 BEM 표기법을 자동화해주는 방법이 되었고, 유일한 클래스명을 생성해내어 심지어 같은 이름을 사용했더라도 서로가 겹치지 않게 보장해주었다.


- `Styled 컴포넌트`로 CSS와 JS를 완전히 섞기 : styled 컴포넌트는 순수한 시각적 기본요소로서 실제의 HTML 태그와 맵핑될 수 있으며, 자식 컴포넌트들을 Styled 컴포넌트로 감싸주는 역할을 한다. 
- Styled 컴포넌트 : 기능적(Functional) 혹은 상태를 가진(StateFul) 컴포넌트들로부터 UI를 완전히 분리해 재사용 할 수 있는 아주 단순한 패턴을 제공한다. 브라우저의 HTML이나 React Native에서 사용될 수 있는 네이티브 태그들에 접근할 수 있는 API를 만들어 내는 것이다.


- 누구나 재사용할 수 있는 핵심 URI : CSS 모듈과 styled 컴포넌트 모두 혼자만으로는 완벽한 해결책이 될 수 없다는 것은 금새 분명해졌다. 제대로 작동하고 확장 가능하게 만들기 위해서는 어떠한 패턴 같은 것이 필요했다. 그러한 패턴은, 컴포넌트를 로직으로부터 완전히 분리하여 스타일링 외에는 아무런 목적도 갖지 않는 핵심 컴포넌트들을 정의하는 방식으로 만들어졌다.
- 이 컴포넌트들은 마음대로 끼워넣을 수 있는 기본 UI API를 정의하고, 모든 UI가 전체 어플리케이션 내에서 영속적임을 보장할 수 있게 해준다.
- 이 방식을 통해 구현 절차로부터 디자인 절차를 완벽하게 분리해 낼 수 있으며, 원한다면 2가지 절차를 동시에 진행할 수 있게 해준다. 한명의 개발자는 기능구현에 집중하고, 다른 한명은 UI를 다듬는 데에 집중함으로써 완전히 관심사를 분리를 달성할 수 있다. 

[출처](https://dongwoo.blog/2017/02/07/%EB%B2%88%EC%97%AD-css%EC%9D%98-%EC%A7%84%ED%99%94-css-%EB%B6%80%ED%84%B0-sass-bem-css-%EB%AA%A8%EB%93%88-%EC%8A%A4%ED%83%80%EC%9D%BC%EB%93%9C-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%EA%B9%8C/)

#### [border 단축속성]
- 각 테두리마다 선의 굵기(width), 선의 형태(style), 선의 색상(color)를 지정할 수 있다.
- `border: border-width border-style border-color;`

#### [label의 완화, title]
- `WCAG` (W3C에서 발표한 웹 콘텐츠 접근성 지침, Level A) : 
- 콘텐츠에 사용자 입력이 필요한 경우 `label` 또는 지침 제공
- `label` 요소가 사용되지 않을 때, 폼 컨트롤을 식별하기 위해 `title` 속성 사용하기
- 시각적인 디자인이 label을 수용할 수 없을 때나(ex, label로 식별되는 텍스트가 스크린에 없는 경우) `label`을 표시하는 것이 혼란스러울 수 있는 곳에는 `title` 속성을 대신 사용할 수 있다.

```html
<input type=“text” id=“user_num2” title=“주민등록번호 뒷자리” />
<input type=“text” id=“phone2” title=“전화번호 뒷자리” />
```

- 상황에 맞는 도움말을 사용할 수 있습니다.

```html
<label for=“address”>주소 : </label>
<input type=“address” type=“text” title=“주소 예시: 경기도 성남시 대왕판교로” />
```

- `KWCAG` (한국형 웹 콘텐츠 접근성 지침, Level A) :
입력서식에는 다음과 같은 레이블을 제공해야한다.
- `<input>, <textarea>, <select>` 요소에는 1:1 대응하는 `<label>`요소 또는 `title` 속성을 제공하지 않은 경우 : `<label>`의 id가 동일하게 제공함으로써 입력서식의 목적을 사용자에게 명확히 제공하여 준다.

```html
<ul>
	<li><label for=“userId”>아이디</label><input type=“text” id=“userId” /></li>
	<li><label for=“userPw”>비밀번호</label><input type=“password” id=“userPwd” /></li>
</ul>
```

#### [html 전역속성]
- `accesskey` : 요소에 접근할 수 있는 단축키를 지정
- `class` : 스타일시트에 정의되어있는 클래스이름을 지정
- `contenteditable` : HTML5에서 새롭게 등장한 속성으로 페이지 안에서 사용자들이 컨텐츠를 수정할 수 있게 한다.
- `contextmenu` : 사용자가 요소의 context menu를 정의할 수 있도록 한다. 사용자가 트리거 했을 때 (윈도우의 경우 마우스 우클릭을 했을 경우) 나타난다. 
- `data-*` : data- 라고 앞에 붙여 이름을 만듦으로써 사용자 지정 속성을 정의할 수 있다. 사용자 지정 속성은 화면상에 보이지 않는 텍스트나 추가정보를 요소에 담아 놓읗때 활용할 수 있다.
- `dir` : 요소의 텍스트 방향을 명시한다.(ltr or rtl)
- `draggable & dropzone` : HTML5 지원 사항중 하나로, 문서 안의 요소를 드래그&드랍 할 수 있는지 나타낸다.
- `hidden` : 브라우저에서 요소를 숨겨준다. 단순히 뷰만 숨기는 것이 아닌, 브라우저에서 hidden 속성의 엘리먼트는 랜더링하지 않는다.
- `id` : 엘리먼트의 유일한 식별자를 부여하기 위해 쓴다.
- `lang` : 요소의 컨텐츠 언어를 명시하기 위해 사용한다.
- `spellcheck` : 브라우저가 요소 컨텐츠의 철자를 체크해야 할지 명시하기 위해 사용
- `style` : CSS 스타일을 정의할 때 사용한다.
- `tabindex` : HTML 페이지 안에서 `Tab`키 포커스를 이동할 때의 순서를 정한다.

#### [text-align]
- 블록요소나 표의 칸 상자의 가로 정렬을 설정한다.
- `block`박스에 적용하는 속성, 부모블록 안에 `inline`요소가 정렬됨
 
#### [vertical-align]
- inline 또는 table-cell box에서의 수직정렬을 지정한다.
- 같은 `inline` 요소끼리 세로 정렬하는 속성
- 기본값은 `baseline`으로, 부모 요소의 기준선(baseline)에 맞춤

[baseline](https://i.imgur.com/xPzFwwp.png)
- `baseline`이란? 위 그림처럼 꼬리부분을 뺀 기준선
- 기준선이 없는 요소는 `margin` 끝을 기준선으로 사용함 

#### [a태그의 target속성]
- `_self` : 연결 문서를 클릭한 창에서 엶(기본값)
- `_blank` : 연결 문서를 새 창에서 엶
- `_parent` : 부모(상위레벨) 창에서 엶(부모가 없으면 _self처럼 표시됨)
- `_top` : 가장 상위 창에서 엶

#### [a태그와 button태그]
- `<a>` : anchor, 다른 자원을 연결하는 의미, href 값으로 아무 의미 없는 ‘#’을 사용하여 onclick과 같은 방식을 쓰는 것은 `<a>`의 본래의 의미와 다르게 사용했다는 것을 반증한다. 

- `<button>` : 다른 자원의 참조하는 의미 없는 버튼이나 텍스트가 키보드 포커스를 받아야 하는 경우, 이벤트가 실행되었을 때, 기능을 수행하는 경우에 사용
- ex) 회원가입 창이 모달창으로 열린다면, 그것은 의미상 button이 적합
- `<a>`안에 `<button>`은 쓸 수 없다.(interactive한 요소 안에 interactive한 요소는 들어갈 수 없음)

#### [background-position]
- 배경이미지의 위치를 지정
- 속성값
	- `left top`, `left center`, `left bottom` 등(2가지 중 한가지만 쓸 경우 나머지는 자동으로 `center`)
	- `x% y%` (`30% 40%`를 지정하면, 상자의 `30% 40%` 위치와 배경의 `30% 40%` 위치를 매칭시켜서 배치 
	- `px`, `cm`, `in`, `pt`, `em` 등


#### [section과 article]
- `<section>` : 서로 관계 있는 문서를 분리하는 역할을 한다. 주로 문서를 다른 주제로 구분짓기 위해 사용된다.

- `<article>` : 내용이 각기 독립적이고, 홀로 설 수 있는 내용을 담는다. 주로 블로그 글, 포럼글, 뉴스 기사 등을 article로 묶을 수 있다.

- 내용이 독립적이고 스스로 설 수 없는 내용이라면 `<article>` 사용
- 내용이 서로 관계가 있다면 `<section>`
- 의미적으로 관계가 없다면 `<div>` 사용, `<div>`는 오직 내용을 묶는 역할
- 여러 개의 `<section>`을 `<article>`로 묶을 수 있고, 마찬가지로 여러 개의 `<article>`을 `<section>`으로 묶을 수 있다.  

#### [aside]
- 주요한 주제가 아닌 것, 부차적인 내용을 담는 태그
- ex) 블로그에서 볼 수 있는 사이드바 혹은 날씨, 주식 정보 등 

#### [dl,dt,dd 그리고 dl 안에 div]
- `<dl>` : Description List의 줄임말로, 개념과 정의로 이루어진 목록이다. 개념은 `<dt>`요소로 정의는 `<dd>`요소로 작성하며, 주로 용어사전 구현이나 메타데이터(키,값 쌍 목록)를 표시할 때 사용
- `<dt>` : 설명 혹은 정의 리스트에서 용어를 나타낸다.(display: inline)
- `<dd>` : 정의 목록 요소(`<dl>`)에서 앞선 용어(`<dt>`)에 대한 설명(display: block)
- `<dt>`와 `<dd>`는 1:1 형태가 아닌, 1:다, 다:1, 다:다 형태를 취할 수 있다.
- `<dl>`안에 `<div>`를 넣을 수 있지만, 같은 내용(dt, dd들)만 하용

```html
<dl>
	<div>
		<dt>foo</dt>
		<dd>bar</dd>
	</div>
<dl>
```
</div> 
</details>

---
<details open>
<summary>좋은 습관들</summary>
<div>

`HTML`
1. 마크업 후, 문법검사하는 습관을 들이자.
2. 나만의 문법기준, 컨벤션을 정하자
3. 다양한 meta 정보를 통해서 head 영역을 풍부하게 작성해보자
4. title 속성을 활용해 SEO를 활성화시키자

`CSS`
1. display: flex; flex-flow: row nowrap; 기본값이어도 항상 같이쓰자
2. 어렵지만 레퍼런스 읽는 습관을 가지자

</div> 
</details>

---

<details open>
<summary>회고</summary>
<div>

<pre>
정말 많은 HTML 개념을 배운 일주일이었다. 
HTML은 알면 알수록 더 많은 내용이 존재하는 것 같다.
WEB CAFE 실습을 하면서 배운 개념을 활용하는 것이 너무 어려운것 같다. 특히 float와 flex는 너무 어렵고 복잡하다.
노트에 구조를 그리고, 많은 경험을 하면서 부딪히는 노력이 필요할 것 같다. 
</pre>

</div> 
</details>