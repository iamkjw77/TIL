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