## HTML
<details open>
<summary>6일차</summary>
<div markdown="6">

#### [user agent CSS]
- `agent(에이전트)` : 사용자를 대표하거나 대신해 사용자가 해야 할 작업을 자동으로 수행하는 소프트웨어
- `user agent CSS` : 브라우저에서 제공하는 기본 style
- ex) `<ul>`은 기본적인 margin, padding 값을 가지고 있다.


#### [block안에 inline을 배치할 경우, baseline]
[baseline](https://media.vlpt.us/images/ursr0706/post/3703c8be-9181-4f27-bf5a-07e5251c67df/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202020-07-22%20%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB%201.12.11.png)
- `baseline` : 이미지와 텍스트 등의 요소는 기본적으로 baseline을 기준으로 배치가 된다. 글자가 앉아있는 선이다. 한글과 다르게 영어 소문자에만 있는 g, j, p, q, y와 같이 끝이 밑으로 내려가는 부분(descender)은 baseline 밑으로 내려간다.


`Q. 이미지요소 하단에는 왜 작은 Gap이 생길까?`
A : img요소는 inline 레벨요소이기 때문이다. inline 레벨요소는 text와 동급이다. 이미지와 텍스트 모두 inline요소이기 때문에 vertical-align의 기본값 baseline을 기준으로 배치된다. 영어 소문자에는 한글과 다르게 g, j, p, q, y와 같이 글자의 끝이 기준선 밑으로 내려가는 글자(descender)가 있는데 그 부분을 표현하기위해 baseline은 밑에 약간의 공간을 두고 있다.


#### [이미지 하단의 Gap을 없애는 방법]
1. `display: block;`
- `img`가 더 이상 text와 같은 inline요소가 아니기 되면서 baseline 위에 놓이지 않게되어 Gap이 사라진다. 
- 문제점 : 이미지와 나란히 놓여있는 `text`가 있다면, `text`는 `img` 밑으로 배치된다.

2. `vertical-align` 속성값을 변경
- 기본값이 `baseline`으로 되어있는 `vertical-align` 속성의 값을 top, middle, bottom으로 변경하는 방법이다.
- 문제점 : 이미지와 나란히 놓여있는 `text`가 있다면, 기준선이 변경되어 `top, middle, bottom`으로 배치될 수 있다.

[image요소 하단의 알 수 없는 갭 현상](https://velog.io/@ursr0706/image%EC%9A%94%EC%86%8C-%ED%95%98%EB%8B%A8%EC%9D%98-%EC%95%8C-%EC%88%98-%EC%97%86%EB%8A%94-%EA%B0%AD-%ED%98%84%EC%83%81)
[inline-block요소의 baseline](https://velog.io/@ursr0706/vertical-align)

#### [서버로 들어가는 정보방식, key:value 쌍으로]
- `요청` : 클라이언트가 서버에게 웹 페이지를 보여 달라고 말하는 것
- `응답` : 서버가 클라이언트에게 요청받은 것을 대답하는 것
- `HTTP 패킷` : 클라이언트가 서버로 요청을 했을 때, 보내는 데이터를 HTTP 패킷이라고 표현한다. HTTP 프로토콜을 쓰므로, 앞에 HTTP가 붙고 인터넷을 통해 보내는 데이터를 패킷이라고 표현하므로, HTTP 패킷이라고 부른다.
- `HTTP 패킷`의 구조 : HTTP 패킷의 구조는 크게 header와 body로 나눠진다. header에는 7가지 HTTP 메서드 방식 중 무엇을 썼는지, 클라이언트 정보, 브라우저 정보, 접속할 URL등과 같은 정보를 담는다. body는 보통 비어있다. 하지만 특정 데이터를 담아서 서버에게 요청을 보낼 수 있다.
- `GET`, `POST` 메서드 : 웹 서비스 개발에 주로 사용하는 메서드이다. 두 방식 모두, 서버에 요청을 하는 메서드이다.

#### [GET 방식]
- 클라이언트의 데이터를 URL 뒤에 붙여서 보낸다. 예를 들어 아이디와 패스워드를 보낸다면 아래와 같은 예시처럼 보낸다.
- `www.example.com?id=mommoo&pass=1234`
- URL 뒤에 `?` 마크를 통해 URL의 끝을 알리면서, 데이터 표현의 시작점을 알린다.
- 데이터는 `key`와 `value` 쌍으로 넣어야한다. 위 예시에서 key는 id와 pass이고, value는 mommoo와 1234이다. 중간에 &마크는 구분자이다. 2개 이상의 key-value 쌍 데이터를 보낼 때는 &마크로 구분해준다. 
- URL 뒤에 붙이므로, HTTP 패킷 헤더에 포함되어 서버에 요청한다. 따라서 GET 방식에서 BODY에 특별한 내용을 넣을 것이 없으므로 BODY가 빈 상태로 보내진다. 그러므로 헤더의 내용 중 BODY 데이터를 설명하는 Content-Type이라는 헤더필드는 들어가지 않는다. URL 형태로 표현되므로, 특정 페이지를 다른 사람에게 접속하게 할 수 있다. 또한 간단한 데이터를 보내는 양의 한계가 있다.

#### [POST 방식]
- `POST` 방식은 `GET` 방식과 달리, 데이터 전송을 기반으로 한 요청 메서드이다. GET 방식은 URL에 데이터를 붙여서 보내는 반면, POST 방식을 URL에 붙여서 보내지 않고 BODY에다가 데이터를 넣어서 보낸다. 따라서 헤드필드 중 BODY에다가 데이터를 넣어서 보낸다. 헤드 필드 중 BODY의 데이터를 설명하는 Content-Type이라는 헤더 필드가 들어가고 어떤 데이터 타입인지 명시한다.

#### [GET 방식과 POST 방식에 대한 상식]
`Q. POST방식이 GET방식 보다 보안측면에서 더 좋다?`
A. POST든 GET든 보내는 데이터는 전부 클라이언트 측에서 볼 수 있다. 단지 GET방식은 URL에 데이터가 표시되어 별다른 노력 없이 볼 수 있어 서지, 두 방식 모두 보안을 생각한다면 암호화해야 한다.

`Q. GET방식이 POST방식보다 속도가 빠르다?`
A. 빠른건 맞다. 이유는 GET방식의 요청은 캐싱(한번 접근 후, 또 요청할 시 빠르게 접근하기 위해 데이터를 저장시켜 놓는다) 때문에 빠른 것이다. 

[출처](https://mommoo.tistory.com/60)

#### [fallback 디자인]
- `fallback` : (만일 사태에 대한) 대비책
```html
background: #ccc linear-gradient(#ccc, #eee);
/* #ccc는 fallback color, linear-gradient를 지원하지 않는 브라우저에서는 단색으로 나타나게 */
```

#### [CSS Flex 이슈]
- IE9 이하 버전 브라우저는 플렉스 명세를 지원하지 않는다.
- IE10 브라우저는 2012년의 플렉스 명세를 지원한다.
- IE10 브라우저를 지원하려면 2012년 플렉스 속성에 `–ms-` 제조사 접두어를 붙여야 한다.

- IE10 브라우저는 표준명세의 `flex-grow`, `flex-shrink`, `flex-basis` 속성을 지원하지 않고, 단축 속성인 `-ms:flex: 0 1 auto` 속성과 값을 지원한다. 
- 안드로이드 2.1 ~ 4.3 브라우저와 IE 브라우저가 공통으로 지원하지 않는 속성은 `flex-flow`, `justify-content: space-around`, `align-self`, `align-content` 이다.

#### [tab UI]
- 메가 네비게이션 : 글로벌 네비게이션 바(GNB)에 위치한 특정 메뉴에 마우스 롤오버 했을 시 나타나는 대형 메뉴를 말하며, 일반적인 드롭다운 메뉴보다 훨씬 많은 메뉴를 표시할 수 있으며 메가 메뉴 안에서도 상세 분류를 할 수 있습니다. 카테고리를 명확하게 분류하여 메뉴를 찾기 쉽도록 기획해야 하며, 주로 쇼핑몰 같은 대형 웹사이트에 적용된다.

```html
<ul role="tablist">
  <li role="none">
    <a href="#" role="tab" id="tab_01" aria-controls="tabpanel_01"></a>
  </li>
  <li role="presentation"><a href="#" role="tab"></a></li>
</ul>

<div role="tabpanel" id="tabpanel_01" aria-labelledby="tab_01" aria-selected="true"></div>
```
- 위와 같이 GNB(li)와 마우스 롤 오버시 나타나는 대형메뉴(div)가 독립적으로 떨어져 있다면, id와 aria-labelledby 속성을 사용하여 명시적으로 연결해주어야 한다.

- `role= “none”` : 역할 없음
- `role=“presentation”` : 꾸미는 역할만 하는 태그
- `aria-selected=“true”` : 지금 현재 tab으로 선택된 것


</div> 
</details>

---

## HTML
<details open>
<summary>7일차</summary>
<div markdown="7">

#### [time 태그]
- 시간의 특정 지점 또는 구간을 나타낸다. datatime 특성의 값을 지정해 보다 적절한 검색 결과나, 알림 같은 특정 기능을 구현할 때 사용할 수 있다.

```html
<time datetime="2020-10-28T14:19:07">2020.10.28.</time>
```
#### [text-overflow]
- 이 속성은 텍스트가 한 줄일 때만 가능한 속성이다. 따라서 `white-space: nowrap` (텍스트가 길어도 줄바꿈 되지 않음)와 `overflow: hidden or scroll or auto`(한 줄을 제외한 나머지는 숨겨라) 2가지 모두 충족할 경우에만 적용된다.

- 속성값
	- `clip` : 기본값, 텍스트를 자름
	- `ellipsis` : 잘린 텍스트 생략 부호(...)로 표시함
	- `string` : 잘린 텍스트를 지정한 문자열로 표시(지원하는 브라우저 없음) 

#### [컴파일 언어]
- 원시코드(프로그래머가 작성한 소스코드)를 모두 기계어로 변환한 후에 기계(JVM 같은 가상 머신)에 넣고 기계어 코드를 실행한다. 소스코드를 기계어로 번역하는 빌드 과정에서는 인터프리터 언어에 비해 시간이 소요된다. 하지만 런타임 상황에서는 이미 기계어로 모든 소스코드가 변환되어 있기 때문에 빠르게 실행할 수 있다. 대표적인 언어로 C, C++이 있다.

#### [인터프리터 언어]
- 원시코드(프로그래머가 작성한 소스코드)를 기계어로 변환하는 과정없이 한줄한줄 해석하여 바로 명령어를 실행하는 언어를 말한다. R, Python, Ruby, HTML과 같은 언어들이 대표적인 인터프리터 언어이다. 
- 인터프리터가 직접 한 줄씩 읽고 따로 기계어로 변환하지 않기 때문에 빌드 시간이 없다. Runtime 상황에서는 한 줄씩 실시간으로 읽어서 실행하기 때문에 컴파일 언어에 비해 속도가 느리다.
- 실행속도는 느리지만 코드 변경 시 과정없이 바로 실행 가능하다는 장점이 있다.

#### [빌드 과정]
- 빌드는 소스파일을 실행파일로 생성하는 과정이다. 즉, 고급언어 → 변환 → 저급언어(기계어) 과정을 거쳐서 실행파일로 생성한다.

#### [파싱]
- `parsing` : 구문 분석이라고도 하며 문장을 구성성분으로 분해하고, 그들 사이의 위계관계를 분석하여 문장의 구조를 결정하는 것
- 프로그램을 `compile` 하는 과정에서 특정 프로그래밍 언어가 제시하는 문법을 잘 지켜서 작성 하였는지 `compiler`가 검사하는 것
- `DOM(Document Object Model) 트리`를 만드는 과정으로 일반적으로 HTML, XML 파서를 각각 가지고 있음, HTML 파서는 말 그대로 HTML 문서를 해석하는데 사용되고, XML 파서는 XML 형식을 따르는 SVG, MathML 등을 처리하는데 사용 

#### [스크립트와 스타일 시트의 진행 순서]
- JS인 `<script>` 태그를 만나면 스크립트가 해석 및 실행되는 동안 문서의 파싱은 중단된다.
- 스크립트가 외부에 있는 경우 우선 네트워크로부터 자원을 가져와야 하는데 이 또한 실시간으로 처리되고 자원을 받을 때까지 파싱은 중단된다.
- 한편 스타일 시트는 이론적으로 DOM 트리를 변경하지 않기 때문에 문서 파싱을 기다리거나 중단하지 않는다.
- 만약. 스크립트 파일을 먼저 로드하게 되는 경우 즉, 스크립트 문서를 파싱하는 동안 스타일 정보를 요청하는 경우라면 문제가 된다
- 이 경우 스크립트 문서를 파싱하는 동안 브라우저는 다른 작업을 수행하지 않기 때문에 파싱되지 않은 상태가 되고, 이렇게 되었을 때 화면 레이아웃이 제대로 구성되지 않은 상태로 뷰를 제공하게 될 확률이 높기 때문에 사용자 경험(UX)을 떨어뜨리는 결과를 초래한다.

- 위 상황의 3가지 해결법
	1. 스크립트 소스를 `body` 태그 끝에 작성한다.
	2. `defer` 속성을 추가한다.
	3. `ready()` 함수를 사용한다.

#### [jQuery ready()]
- `ready()` 함수가 실행되는 시점은 브라우저가 DOM 트리를 생성한 직후이므로 유저 입장에서는(이미지나 외부 리소스의 로딩을 기다릴 필요 없이) 훨씬 빠르게 웹페이지의 기능을 사용할 수 있다.  

#### [defer]
- `<script>` 태그의 `defer` 속성은 페이지가 모두 로드된 후에 해당 외부 스크립트가 실행됨을 명시
- 이 속성은 `<script>` 요소가 외부 스크립트를 참조하는 경우에만 사용가능
- ex) `<script src="./js/jquery.min.js" defer></script>`
</div> 
</details>

---

## HTML
<details open>
<summary>8일차</summary>
<div markdown="8">

#### [figure, figcaption]
- `<figure>` 요소는 사진, 도표, 삽화, 오디오, 비디오, 코드 등을 담는 컨테이너 역할을 하는 태그이고, `<figcaption>` 요소는 이에 대한 설명하는 문구를 담는 태그이다.
- `<figcaption>` 요소는 선택적이며, `<figure>` 요소 안에 사용한다.(내용 앞뒤로 올수 있음)
- `<figcaption>` 요소는 `<figure>` 요소에서 한 번만 사용할 수 있으며 `<figure>` 안에는 여러 가지 자식요소 (img, code 등)을 포함할 수 있다.
- 책이나 잡지에서 이미지, 차트 등이 나올 때 이를 설명하는 문구와 함께 소개된다.

```html
<figure>
    <img src="/media/cc0-images/elephant-660-480.jpg"
         alt="Elephant at sunset">
    <figcaption>An elephant at sunset</figcaption>
</figure>
```
#### [XHTML 문법]
- `XHTML` : `EXtensible HTML`을 의미한다. `XHTML`은 `HTML`과 거의 비슷하지만, 문법의 적용이 조금 더 엄격한 특징을 가지고 있다. 
- ex) 모든 태그는 반드시 닫혀야 한다. / 인라인요소 안에 블록요소는 들어갈 수 없다.

#### [border-image]
- `border-image` : CSS 속성은 요소의 주위에 이미지를 그린다. 일반 테두리를 대체한다.
- `border-image: border-image-source border-image-slice border-image-width border-image-outset border-image-repeat `

```css
/* 이미지 | 슬라이스 */
border-image: linear-gradient(#f6b73c, #4d9f0c) 30;

/* 이미지 | 슬라이스 | 너비 */
border-image: linear-gradient(red, blue) 27 / 35px;

/* 이미지 | 슬라이스 | 너비 | 거리 | 반복 */
border-image: url("/images/border.png") 27 23 / 50px 30px / 1rem round space;
```

#### [웹 레이아웃 기술 발전사]
1. `레이아웃이 없던 초창기`
- 웹이 창궐한 초창기, 레이아웃을 위한 디자인 방법은 별도로 없었고 제한적인 텍스트 디자인만 가능했다.
- 단점 : 디자인 할 요소가 한 없이 부족

2. `테이블 레이아웃`
- 테두리(border)를 투명하게 설정한 테이블을 사용해 멀티 컬럼 디자인이 시작되면서 웹 레이아웃이 발전하게 되는 시기이다. 하지만 테이블을 사용하는 본래 목적을 망각하고 행/열 구조 안에 이미지를 채워 넣는 방법으로, 오늘 날 더 이상 사용되지 않는다.
- 단점 : 의미상실, 접근성 부재

3. `프레임 레이아웃`
- 테이블 레이아웃에 프레임 기술이 합쳐진 방법으로 여러 장의 HTML 문서를 결합해 하나의 문서를 만들어 사용했다. 이 방법이 한 때 사용된 이유는 페이지의 공통부분을 분리, 효율적으로 관리하는 데 있었다. 하지만 Ajax 비동기 통신 기술의 발전으로 오늘 날 더 이상 사용 되지 않는다.
- 단점 : 권장되지 않는 방법

4. `CSS 레이아웃`
- 웹 표준 시대가 태동 하면서 더 이상 구조 언어인 HTML에서 레이아웃을 하지 않고, 표현 언어인 CSS가 제공하는 본연의 레이아웃 기술인 `float`, `position` 을 사용해 웹 레이아웃을 만들어 내기 시작했다. 오래된 레이아웃 기술 임에도 여전히 많이 사용 되고 있는 방법이지만, 모바일 시대에 접어들면서 멀티스크린에 대응하는 디자인을 만들어 내기에는 적합하지 않다.
- 단점 : 브라우저 특성(버그)에 기반한 비논리적 기법이 난무

5. `Flex 레이아웃`
- 다양한 모바일 환경에 대응하기 위해 등장한 레이아웃 기술로 유연한 박스(Flexible Box)를 사용할 수 있는 방법을 제공한다. X축 또는 Y축 방향으로 요소를 배치, 정렬 할 수 있으며 각 요소의 순서를 변경할 수 있어 기존의 레이아웃 기술 대비 자유도가 높아졌다. 그리드 프레임 워크 Bootstrap에서 사용하는 기반기술이다.
- 단점 : X축 또는 Y축, 한쪽 방향으로만 설정가능한 자유도가 낮은 레이아웃 기법

6. `Grid 레이아웃`
- 그리드 시스템을 언어 차원에서 지원하면서 더 이상 기존의 그리드 프레임 워크를 사용할 필요가 없어졌다. 행/열 격자 구조에 요소를 자유롭게 배치할 수 있을 뿐더러 반응형 웹 레이아웃 대응도 가능해 더욱 각광 받는 레이아웃 기술이다.
- X축, Y축, 양쪽 방향 모두 설정 가능한 자유도가 높은 레이아웃 기법

[출처](https://uid.gitbook.io/css-grid/web-layout-history)

</div> 
</details>

---

<details open>
<summary>좋은 습관들</summary>
<div>

`HTML`


`CSS`
1. 각 요소마다 배경색을 줘서 구조를 파악하자

</div> 
</details>

---

<details open>
<summary>회고</summary>
<div>

<pre>

</pre>

</div> 
</details>

---