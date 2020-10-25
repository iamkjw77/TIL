## HTML
<details open>
<summary>1일차</summary>
<div markdown="1>

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