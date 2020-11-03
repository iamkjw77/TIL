## HTML
<details open>
<summary>11일차</summary>
<div markdown="11">

#### [RWD, Responsive Web Design]
- 디바이스의 종류에 따라 웹 페이지의 크기가 자동으로 재조정 되는 것을 말한다. 오직 하나의 HTML소스 만으로 특정장치에 최적화된 환경을 사용자에게 제공(One Source Multi Use)
- 반응형 웹은 고사양(고 해상도) 웹이 저사양(저 해상도) 모바일 기기에서도 불편함이 없이 구현되는데 초점이 맞춰져있다.
- 기기 특성에 따라 레이아웃이 변경할 뿐만 아니라 콘텐츠도 변경할 수 있음을 의미한다. 
- 일반적으로 % 단위를 사용하여 각 디자인의 폭에 유동적으로 반응하여 콘텐츠의 크기가 유동적으로 변경된다. 
- ex) target/context = result, 960 레이어에 900 콘텐츠를 사용할 경우 900/960 = 0.9375(콘텐츠는 93.75% 차지)
- 보통 CSS 전처리기 LESS, SASS를 사용하여 구현

#### [AWD, Adaptive Web Design, 적응형 디자인]
- 사용자가 브라우저의 가로크기를 변경해서 개발자가 지정한 해상도에 도달하면 레이아웃이 재배치되는 형태
- px 단위를 사용하며 몇 개의 해상도를 지정하여 CSS 코딩 시 브라우저가 그 사이즈에 도달하면 해당되는 레이아웃을 보여줌

#### [반응형(RWD) vs. 적응형(AWD)]
- `RWD` : 콘텐츠의 정렬만 변경되면서 모바일에 도착, 브라우저의 크기가 변할 때, 콘텐츠가 변하는 장면을 끝까지 버퍼링 없이 시청 가능하다면 반응형
- `AWD` : 레이아웃이 바뀌면서 모바일에 도착한다면 적응형, 브라우저의 크기가 변동하며 콘텐츠가 변할 때, 중간 중간 끊김이 생기는 버퍼링을 목격한다면 적응형

#### [mobile first]
- 모바일 퍼스트는 웹 디자인을 할 때, PC보다 모바일 기기를 먼저 생각해서 디자인하고 프로그래밍 하는 기법
- 모바일 퍼스트의 핵심은 모바일의 제약을 집중의 기회로 본다는 것에 있다.
- 모바일의 제약은 크게 3가지로 나눌 수 있다.
	1. 모바일 기기의 스크린 크기
	2. 네트워크 속도 및 품질
	3. 사용하는 모드
- 위 3가지 제약을 통해 일반 웹은 모바일에 있어서 불필요한 요소(기능/형식/꾸미기/이동)들을 가지고 있다고 판단한다. 불필요한 요소를 최소한 시킨 모바일 웹은 사이트가 진짜로 제공해야 할 내용과 기능이 무엇인지 나타낸다.

#### [미디어 쿼리, Media Query]
- 단말기의 종류에 따라 각각 다른 스타일시트를 적용하게 하는 기능
- 미디어쿼리에서 사용할 수 있는 미디어 타입 : `all`(모든 미디어 타입), `print`(인쇄 용도), `screen`(컴퓨터 스크린을 위한용도) 등 

#### [미디어 쿼리 적용법]
1. `<link>`
```css
<link href="cssfile.css" media="screen and (min-width: 512px) and (max-width: 1024px)" rel="stylesheet">
```

2. `<style>`
```css
<style type="text/css" media="screen and (min-width: 512px) and (max-width:1024px)">  
</style> 
```

3. `<style> - @import`
```css
<style>  
    @import url(cssfile.css) screen and (min-width: 152px) and (max-width: 1024px);
</style> 
```

4. CSS 파일
```css
@media screen and (min-width:512px) and (max-width:1024px)
```

#### [이미지의 반응형]
1. 이미지에 바로 속성을 주는 경우
```css
img{
	max-width: 100%;
	/* 이미지의 최대 너비는 원본이상으로 커질 수 없음, width가 고정이 아님 */
	height: auto;
}
```

2. Class를 주는 경우, 해당 이미지에 조립하여 사용할 수 있음
```css
.responsive{
	width: 100%;
	height: auto;
}
```

#### [min-device-pixel-ratio]
- 화면 내의 1px를 표현할 때의 실제 단말기의 픽셀 비율에 대응한다.
- 아이폰4의 경우, 실제 해상도는 640*960이지만, 웹 브라우저 해상도는 320*480에 대응한다. 따라서 아이폰4의 사파리의 경우엔 1px에 실제로는 단말기의 2px이 대응하고 있으므로 이 값은 2이다.
- 안드로이드 폰의 경우 실제 해상도 480*800 단말기에서 웹브라우저 해상도는 320*533으로 표현되는데, 이때의 비율은 1.5이다.
[출처](https://nuli.navercorp.com/community/article/573473)

#### [tab-highlight-color]
- 탭, 링크, 포커스가 맞춰졌을 때, 나타나는 색상을 결정한다.
- 아이폰에서는 사각형 박스형태로 표시되고, 안드로이드에서는 주황색 테두리가 표시된다.

```css
/* 포커스가 안보이게 설정 */
body{-webkit-tap-highlight-color: rgba(0,0,0 0);}

/* 아이폰 에서는 */
body{-webkit-tap-highlight-color: transparent;}
```
[출처](https://dolly77.tistory.com/14)

#### [svg 코드 사용 시, 웹 접근성]
- `jpg`, `png`와 같은 이미지가 단순한 장식용으로 사용된 경우에는 대체텍스트를 부여할 필요없이 `alt=“ ”`로 대체할 수 있다. 이렇게하면 스크린리더는 해당 이미지를 음성출력하지 않는다.
- 이미지 주위에 그 이미지에 대한 설명을 텍스트로 충분히 제공하고 있다고 판단되는 경우에는 대체텍스트를 중복해서 사용할 필요가 없으며 이때에도 `alt=“ ”`를 공백으로 둘 수 있다.

- `svg` : 백터(vector) 이미지를 표현하기 위한 포맷으로 W3C에서 만든 백터 이미지 표준이다. 
- svg 이미지에 대체 텍스트를 주는 경우, svg가 이미지 소스이면 `role=“img”` 속성을 추가해 스크린리더에게 `svg` 콘텐츠 역시 이미지임을 알려줘야 한다.
- HTML 내부에 `<svg>`태그를 삽입하여 이미지를 생성하는 경우, 위의 방법으로 대체 텍스트를 추가할 수 없으므로 `<svg>` 가장 상위 태그에 `title`, `desc` 태그로 설명을 덧붙인다. `title`에는 기본적인 설명을, `desc`에는 부연설명이 있을 경우 추가한다. 추가적으로 `title`에 `aria-labelledby`를 desc에 `aria-descibedby` 속성을 추가할 수 있다.

```html
<svg version="1" id="cat" viewBox="0 0 720 800" aria-labelledby="catTitle” aria-describedby=”catDesc" role="img">
<title id="catTitle">친근한 고양이</title>
<desc id="catDesc">회색고양이가 주인에게 안겨 있는 모습</desc>
… 
</svg>
``` 
[출처](https://nuli.navercorp.com/community/article/1132853?email=true)

#### [성능을 위한 이미지 최적화]
- 대개 이미지는 다운로드 되는 바이트의 대부분을 차지하며, 또한 페이지에서 시각적 공간의 상단 부분을 차지한다. 결과적으로, 이미지를 최적화하면 바이트를 최대한 절약할 수 있고, 웹 사이트에 맞게 성능을 개선할 수 있다. 또한 브라우저가 다운로드해야하는 바이트가 줄어들고, 사용자의 대역폭에 여유가 생기고, 브라우저가 모든 자산을 더 빨리 다운로드하고 표시할 수 있다.  
- 이미지 형식을 함부로 선택하지 말자. 어떤 형식이 가능한지 이해하고 가장 적합한 형식을 사용하자.
- 파일 크기를 줄여주는 이미지 최적화 및 압축 도구를 워크플로에 포함해라
- 자주 사용하는 이미지를 `image sprite`에 배치하면 `http 요청 수`를 줄일 수 있다.
- 초기 페이지 로드 시간을 개선하고 초기 페이지 크기를 줄이려면, 이미지가 뷰로 스크롤된 후에만 이미지를 로드하도록 해라

##### [이미지 형식의 선택]
- 백터 이미지 또는 래스터 이미지(비트맵)를 고려할 수 있다. 래스터의 경우 `GIF`, `PNG`, `JPG` 등이 있다.
- `래스터 이미지(비트맵)` : 개별 점 또는 픽셀들이 모인 그리드로 표현된다. 이미지의 크기가 커질수록 파일의 크기도 커진다. 원래크기보다 더 크게 확대되는 경우에는 누락된 픽셀을 어떻게 채울지 브라우저가 추측해야하기 때문에 이미지가 흐려진다.
- `백터 이미지` : 곡선, 선, 셰이프 및 채우기 색상으로 정의된다. 백터 이미지는 Adobe Illustrator 또는 Inkscape와 같은 프로그램으로 만들어져 `SVG`와 같은 백터 형식으로 저장된다. 백터 이미지는 단순 원시 유형을 기반으로 작성되므로, 파일 크기 변경이나 화질 손실 없이도 이미지의 배율을 조정할 수 있다.

- 사진 이미지에는 `JPG`를 사용하자
- 로고 및 라인아트와 같은 벡터 아트 및 단색 그래픽에는 `SVG`를 사용하자. 백터 아트를 사용할 수 없는 경우 `WebP` 또는 `PNG`를 사용하자
- 더 많은 색상을 허용하고 더 나은 압축율을 제공하므로, `GIF` 대신 `PNG`를 사용하자
- `WebP` : 구글에서 만든 이미지 포맷, Web을 위해서 만들어진 이미지 포맷. 기존의 이미지 포맷이 JPEG, GIF, PNG으로 삼분되어 있었다면 `WebP`는 이 3가지 포맷을 전부 대체 가능하다. PNG 포맷처럼 알파채널을 지원해 배경이 투명한 이미지도 가능하다.(IE 지원X)

##### [파일 크기 줄이기]
- 저장 후 이미지를 ‘사후 처리’하여 파일크기를 줄일 수 있다. 이미지를 압축을 위한 다양한 도구들을 이용하여 이미지 최적화를 시도하자.
- `JPG` 및 `PNG` 파일에 추가적인 무손실 압축을 수행하는 여러 가지 도구가 있으며, 이들 도구는 화질에 영향을 미치지 않는다.

##### [이미지 스프라이트 사용]
- CSS Sprite란 여러 이미지를 단일 ‘sprite 시트’ 이미지에 결합하는 기법이다. 그런 다음, 정확한 부분을 표시하는 오프셋과 함께 요소(sprite 시트)의 배경 이미지를 지정하여 개별 이미지들을 사용할 수 있다.

##### [지연 로딩 고려]
- 지연 로딩은 필요할 때마다 페이지를 로딩하거나 기본 콘텐츠의 로딩과 렌더링이 완료될 때 페이지를 로딩하는 방식으로, 화면에 표시되지 않은 하단부에 많은 이미지가 포함된 긴 페이지에서 로딩 속도를 상당히 개선할 수 있다. 지연 로딩을 사용하면 성능이 향상될 뿐만 아니라 무한 스크롤 환경을 만들 수도 있다.
- 보이는 대로 콘텐츠가 로드되기 때문에 검색 엔진에 해당 콘텐츠가 나타나지 않을 수도 있으므로, 무한 스크롤 페이지를 만들 때 주의해야 한다. 또한 새 콘텐츠가 항상 로드되기 때문에, 하단에 나올 것으로 예상되는 정보를 찾는 사용자가 하단을 볼 수 없다.

#### [아트 디렉션, art direction]
- 화면이 넓은 기기는 큰 이미지가 잘 작동한다. 하지만, 좁은 화면 기기로 사이트를 보기 시작하면 문제가 생긴다. 모바일 기기에서 이미지가 화면 높이를 너무 많이 차지하기 시작하기 때문이다.
- 개선책은 좁은 화면에서 사이트를 볼 때 이미지의 중요한 상세를 보여주는 자른 이미지를 보여주는 것이다. 또 다르게 자른 이미지를 테블릿처럼 중간정도 너비 화면의 기기에서 보여 줄 수 있을 것이다. 이를 보통 `아트 디렉션 문제(art direction problem)`라고 한다.
- `아트 디렉션(art direction)` : ‘연출 방향’, 반응형 이미지에서는 이미지의 의도가 제대로 전달되도록 기기에 따라 사진의 핵심을 확대해서 보여주거나 하는 방식 

##### [아트 디렉션 문제의 해결책, `<picture>`]
- 아트 디렉션이 필요한 경우가 아니라면 `media` 속성을 사용하지 말자

```html
<picture>
  <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg">
  <source media="(min-width: 800px)" srcset="elva-800w.jpg">
  <img src="elva-800w.jpg" alt="딸 엘바를 안고 서 있는 크리스">
</picture>
```
- `<picture>` 요소는 `<source>` 요소들을 감싼다. `<source>` 요소는 브라우저가 고를 수 있는 여러 소스들을 제공한다. `<source>` 요소들 뒤에는 가장 중요한 `<img>`요소가 뒤따른다.
- 만약, 뷰포트의 너비가 799px 이하라면, 첫 번째 `<source>` 요소의 이미지가 표시된다.
- 만약, 뷰포트의 너비다 800px 이상이면, 두 번째 `<source>` 요소의 이미지가 표시된다.
- `<picture>` 요소를 지원하지 않는 브라우저나 위 두 개의 조건문을 만족하지 않는 경우 `<img>` 요소가 제공된다. 

#### [polyfill, 폴리필]
- 개발자가 특정기능이 지원되지 않는 브라우저를 위해 사용할 수 있는 코드 조각이나 플러그인 (이전 브라우저에서 최신기능을 제공하는데 필요한 코드)
- HTML5 및 CSS3와 오래된 브라우저 사이의 간격을 메꾸는 역할
- 일반적으로 웹의 자바스크립트(Javascript) 이다.
- 더 나은 가능성과 더 나은 성능을 위해 사용

#### [해상도 전환, resolution switching]
- 작은 모바일 화면에서는 페이지에 그렇게 큰 이미지를 포함할 필요가 없다. 이것을 `해상도 전환 문제(resolution switching problem)`라고 부른다. 
- 작은 화면에 큰 이미지를 표시 할 필요가 없다. 그렇게 하는 것은 대역폭(:단위 시간당 전송할 수 있는 데이터 전송량)을 낭비하는 것이다. 특히, 모바일 사용자는 기기에 맞는 작은 이미지 대신 데스크톱에 사용되는 큰 이미지를 다운로드 하느라 대역폭을 낭비하고 싶어 하지않는다. 
- 이상적인 방법은, 다양한 해상도를 준비해두고, 웹 사이트 데이터를 받는 기기에 따라 적당한 사이즈를 제공하는 것이다.

##### [해상도 전환 문제의 해결책, img srcset과 sizes 속성, IE지원 X]
- 기기에 따라 단지 크기만 다른, 동일한 이미지 콘텐츠를 보여주고 싶은 경우`
- `img srcset`은 자주 사용하지 않고, JS를 사용해 해상도 크기별로 동적으로 주기도 한다. 
```html
<img srcset="elva-fairy-320w.jpg 320w,
             elva-fairy-480w.jpg 480w,
             elva-fairy-800w.jpg 800w"
     sizes="(max-width: 320px) 280px,
            (max-width: 480px) 440px,
            800px"
     src="elva-fairy-800w.jpg" alt="요정 옷을 입은 엘바">
```
- `srcset` : 브라우저에게 제시할 이미지들과 그 크기를 정의한다. 각 쉼표 앞에는 이렇게 적는다.
	1. 이미지 파일명(elva-fairy-480w.jpg)
	2. 공백
	3. 이미지 고유 픽셀 너비(480w) - `px`이 아니라 `w`디스크립터 또는 `x`디스크립터 	사용한다.  

- `sizes` : 미디어조건과 그 조건에 해당하는 이미지의 ‘최적화 출력 크기’를 지정한다. 이 경우, 각 쉼표 전에 이렇게 쓴다.
	1. 미디어 조건문(`max-width: 480px`) 440px - 미디어 조건문은 가능한 최적상태	를 기술한다. 이 조건문의 경우, `뷰포트 너비가 480px이하 일 때`를 의미한다.
	2. 공백
	3. 미디어 조건문이 참인 경우 이미지의 너비(440px) 

```html
<img
  srcset="images/heropy_small.png 400w,
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"
  sizes="(min-width: 1000px) 700px"
  src="images/heropy.png"
  alt="HEROPY" />
```
- 뷰포트의 너비가 400px이하일 때, `heropy_small.png(400px)`가 사용된다.
- 뷰포트 너비가 401~700px 일 때 `heropy_medium.png(700px)`가 사용된다.
- 뷰포트 너비가 701~999px 일 때 `heropy_large.png(1000px)`가 사용된다.
- 뷰포트 너비가 1000px 이상일 때 `heropy_medium.png(700px)`가 사용된다.
- `sizes= (min-width: 1000px) 700px`에서 `(min-width: 1000px)`은 `뷰포트의 너비(가로)가 1000px 이상일 때`를 의미하며, 이어나오는 `700px`은 그 조건일 때 이미지를 `700px로 최적화 출력하겠다.`를 의미한다.

```html
<img
  srcset="images/heropy_small.png 400w,
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"
  sizes="500px"
  src="images/heropy.png"
  alt="HEROPY" />
```
- 뷰포트의 너비와 상관없이 `heropy_medium.png`만 사용
- `heropy_medium.png`는 `500px`의 크기를 가진다.(원래는 700px 크기의 이미지)

#### [img의 src와 sizes, 브라우저의 동작]
1. 기기의 너비를 확인한다.
2. `sizes` 목록에서 가장 먼저 참이 되는 미디어 조건문을 확인한다.
3. 해당 미디어 쿼리가 제공하는 슬롯의 크기를 확인한다.
4. 해당 슬롯 크기에 가장 근접하게 맞는 `srcset`에 연결된 이미지를 불러온다.

#### [W descriptor, X descriptor]
- `W` descriptor : `w` 디스크립터(width descriptor)는 이미지의 원본 크기(가로너비)를 의미
ex) 400*300(px) 크기 이미지의 w값은 400w이다.

- `X` descriptor : `x` 디스크립터(Device pixel ratio descriptor)는 이미지의 비율의도를 의미한다. 

[출처](https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/)
[출처](https://developer.mozilla.org/ko/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)
[출처](https://developers.google.com/web/fundamentals/design-and-ux/responsive/images?hl=ko#%EB%86%92%EC%9D%80_dpi_%EA%B8%B0%EA%B8%B0%EC%97%90%EC%84%9C_srcset%EB%A1%9C_img_%EA%B0%9C%EC%84%A0)

#### [RWD breakpoint]
- `중단점(breakpoint)` : 미디어쿼리를 통해 가변 레이아웃의 형태가 다르게 바뀌는 뷰포트 크기
- 중단점 찾기, `웹을 위한 타이포그래픽 스타일 기준`
	- 텍스트에서 한 줄에 담긴 글자가 45자 ~75자 일 때, 가독성이 가장 좋다.
	- 레이아웃을 키우다가 한 칼럼의 텍스트가 이 기준을 벗어나는지 확인하자.
- 주요 중단점(major) : 칼럼들이 추가되거나 하나 이상의 요소에 대한 변화가 일어나는 부분
- 하위 중단점(major) : 디자인 일부에서만 변화가 일어나는 부분 (font-size가 변해서 글자가 벗어나는 정도)

#### [`<meta name=“viewport” content=“width=device-width, initial-scale=1.0”>`]
- 애플이 아이폰, 아이패드 등 자사의 모바일 브라우저의 뷰포트(viewport) 크기 조절을 위해 만들어졌는데, iOS 장치가 널리 사용됨에 따라 사실상 표준처럼 사용되고 있고, 다른 브라우저들도 이 태그를 채택하게 되었다.
- 브라우저 너비를 장치 너비에 맞추어 표시한다.
- 초기 화면 배율(initial-scale) 설정, 1.0은 100%와 같음

#### [favicon, 파비콘]
- `파비콘(favicon)` : 웹 페이지의 주소 맨 왼쪽에 나오는 아이콘, `favortite + icon = favicon`으로 즐겨찾는 아이콘이라는 뜻이다.
- 파일확장자 : .png도 가능하지만, IE, Chrome, Firefox 등의 웹브라우저 전부를 만족시키기 위해선 `.ico`가 좋다. (`.png`는 IE지원X)

#### [link rel=“preload” as=“style”] 
- `preload` : 브라우저에게 현재 페이지에서 필요한 리소스를 빠르게 가져오게 한다.
- 현재 페이지에서 사용될 것이 확실한 리소스들을 `preload` 해야 한다.
- `as` 속성 사용 : `as` 속성을 사용하여 리소스 유형을 브라우저에게 알려줘야 한다. 올바른 유형이 설정되어 있지 않다면 브라우저는 해당 리소스를 사용하지 않도록 제어해야 한다. 
- `<link rel=“preload” as=“...”>`를 이용하여 리소스를 가져왔지만 현재 페이지에서 3초 내로 사용되지 않는 리소스는 경고문구가 출력된다. 필요하지 않는 것을 가져오지 않도록 주의하자.
- `preload`를 사용하기 좋은 리소스 : `폰트`, `Critical Rendering Path(CRP)의 CSS와 JS`
- `Critical Rendering Path` : 초기 렌더링 전에 반드시 로드되어야 할 리소스(6단계로 구성)
	- DOM 트리 구축
	- CSSOM 트리 구축
	- JS 실행
	- 렌더 트리 구축
	- 레이아웃 생성
	- 페인팅

```html
/* font */
<link rel="preload" as="font" crossorigin="crossorigin" type="font/woff2" href="myfont.woff2">

/* Critical Rendering Path(CRP) */
<link rel="preload" as="script" href="super-important.js">
<link rel="preload" as="style" href="critical.css">
```

#### [::selection]
- 가상 요소 선택자 중 하나로, 선택된 영역의 스타일을 변경하게 도와준다.
- 마우스 드래그 시, 스타일을 변경할 수 있다.
```css
::selection { 적용할 CSS 속성; }

/* 모질라 계열에 적용할 경우 */
::-moz-selection { 적용할 CSS 속성; }
```
- `::seletion` 선택자의 사용 가능한 속성들은 제한되어 있다. 
	1. 텍스트 색상 – color 속성
	2. 백그라운드 – background 속성
	3. 커서의 종류 – cursor 속성
	4. 외곽선 – outline 속성

#### [backdrop-filter]
- 요소 뒤 영역에 흐림이나 색상 시프트 등 그래픽 효과를 적용할 수 있는 속성
- 요소 ‘뒤’에 적용하기 때문에, 효과를 확인하려면 요소나 요소의 배경을 적어도 반투명하게는 설정해야한다.
- 속성값
	- `none` : 뒤에 아무런 필터도 적용하지 않는다.
	- `<filter-function-list>` : 뒤에 적용할 `<filter-function>` 또는 SVG필터의 공백 구분목록
```css
backdrop-filter: blur(5px);
```

</div> 
</details>

---

<details open>
<summary>12일차</summary>
<div markdown="12">

#### [visibility: hidden vs. display: none]
- `visibility: hidden` : 보이지만 않고 해당 공간은 존재, width와 height값을 주었다면 그만큼의 공간은 존재
- `display: none` : 아예 사라짐, 보이지도 않고, 해당 공간도 존재하지 않음

#### [`<video>`와 `<source>`, `<track>`]
- `<video>` : 무비 클립(movie clip)이나 비디오 스트림과 같은 비디오를 정의할 때 사용
- `<video>` 요소 내의 위치하는 텍스트는 사용자의 브라우저가 `<video>` 요소를 지원하지 않을 경우 화면에 표시된다.
- `<video>` 요소는 현재 다음 3가지 포맷의 파일을 지원한다.
	1. `MP4` (MIME 타입: video/mp4)
	2. `WebM` (MIME 타입: video/webm)
	3. `Ogg` (MIME 타입: video/pgg)
- `<video>`의 `poster` 속성: 속성값으로 URL을 줘서 비디오를 다운로드하는 동안이나 사용자가 재생버튼을 누를 때까지 표시할 이미지를 명시한다.

- `<source>` : `<audio>` 또는 `<video>` 요소, `<picture>` 요소에서 사용할 수 있는 다중 미디어 자원을 정의할 때 사용한다.
- 미디어 타입이나 코덱의 지원여부, 미디어쿼리에 따라 브라우저가 선택할 수 있는 대체 비디오/오디오/이미지 파일을 명시할 수 있도록 해준다.

- `<track>` : `<audio>` 또는 `<video>` 요소 같은 미디어 요소를 위한 텍스트 트랙(text track)을 정의할 때 사용한다. 이 요소는 자막 파일이나 캡션 파일, 또는 미디어가 재생되는 동안 화면에 보일 텍스트를 포함한 파일 등을 명시하는데 사용한다. 
- 자막은 필수로 제공해야하는 속성이다. 요약한 자막도 허용되지 않는다.

```html
<video style="width:576px; height:360px" controls>
    <source src="sample_video_mp4.mp4" type="video/mp4">
    <source src="sample_video_ogg.ogg" type="video/ogg">
    <track src="sub_kr.vtt" kind="subtitles" srclang="ko" label="Korean">
    <track src="sub_en.vtt" kind="subtitles" srclang="en" label="English">
</video>
```

#### [`<iframe>`]
- 중첩 브라우징 맥락을 나타내는 요소로 현재 문서 안에 다른 HTML 페이지를 삽입
- html 웹 문서 안에 또 다른 웹 문서를 넣을 수도 있고, 뮤비 등 동영상도 넣을 수 있다.
- `inline frame`, 인라인요소

#### [chrome의 autoplay 정책]
- muted(무음의) autoplay는 언제나 허용한다.
- 사운드가 있는 `autoplay`는 유저가 도메인과 click, tap 등을 이용한 상호작용을 하였을 때 허용한다.

#### [반응형 비디오 만들기]
- 먼저, 반응형으로 작업하려는 비디오의 비율을 알아야 한다.
- 모든 값은 반응형이므로 `width: 100%`를 기준으로 생각하여 `height`값을 넣는다.
ex) 16:9인 경우, 9/16 = 0.5625(56.25%)
4:3인 경우, 3/4 = 0.75(75%)

```html
<div class="video_wrap"> 
  <iframe src="https://www.youtube.com/embed/cEN00wMFB2A" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
</div>
```

```css
.video_wrap{ 
  position:relative; 
  width:100%; 
  height:0;
  padding-bottom:56.25%; 
} 
.video_wrap iframe{ 
  position:absolute; 
  width:100%; 
  height:100%;
}
```

- 16:9를 만들 때, 우리가 원하는 것 : 가로의 56.25%를 height에 적용 
- `height: 56.25%`가 아닌 `padding-bottom: 56.25%`를 준 이유 : height: 56.25%를 사용할 경우 height의 참조기준인 부모태그의 height값의 56.25%값이 적용된다.  
- `padding, margin`에서 %를 사용할 경우 여백의 크기로 컨테이닝 블록 너비의 백분율을 사용한다. 즉, 부모 가로 너비의 56.25%값이 적용된다.

- 그래서 `padding-bottom` 값을 주면 iframe이 밀려난다. 그것을 해결하기 위해 `position: relative, position: absolute`를 줘서 위치를 조정해준다.

- `padding-top`을 주는 경우
```css
.video_wrap{ 
  position:relative; 
  width:100%; 
  height:0; 
  padding-top:56.25%; 
} 
.video_wrap iframe{ 
  position:absolute; 
  left:0; 
  top:0; 
  width:100%; 
  height:100% 
}
/*padding-top을 주는 경우, iframe이 아래쪽으로 밀리기 때문에 offset을 줘서 맞춰주어야 한다.*/
```
[출처](https://okayoon.tistory.com/entry/css%EB%A7%8C%EC%9C%BC%EB%A1%9C-%EB%B0%98%EC%9D%91%ED%98%95-%EB%B9%84%EB%94%94%EC%98%A4-%EB%A7%8C%EB%93%A4%EA%B8%B0)

</div> 
</details>

---

<details open>
<summary>좋은 습관들</summary>
<div>

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