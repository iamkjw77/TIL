패스트캠퍼스 - HTML 수업을 듣고 중요 내용을 정리합니다.

## box-sizing : 요소의 크기 계산 기준을 지정
- content-box : 콘텐트 영역을 기준으로 크기를 정함(기본값)
- border-box : 테두리를 기준으로 크기를 정함

## justify-content : 메인축 방향으로 아이템을 정렬
- flex-start : 아이템들을 시작점으로 정렬(기본값)
- flex-end : 아이템들을 끝점으로 정렬
- center : 아이템들을 가운데 정렬
- space-between : 아이템들 "사이"에 균등한 간격을 만듦
- space-around : 아이템들 "둘레"에 균일한 간격을 만듦
- space-evenly : 아이템들 "사이"와 "양 끝"에 균일한 간격을 만듦(IE, edge 지원X)

### space-evenly를 우회하는 방법
- justify-content: space-between을 주고, 좌우에 padding값을 줌

---

## float 해제
- 방법1) 해당요소의 높이값을 주는 방법(매우 비추천)
이 방법은 내부 콘텐츠의 높이가 변할 경우, 높이값이 fix되어 있기 때문에 높이가 유연하게 변하지 않는 큰단점이 있음

- 방법2) 부모 요소에 overflow: (hidden, auto)를 주는 방법
 이 방법을 사용하면 해당 태그의 자식 요소의 일부라도 부모요소 박스를 벗어나는 부분은 그려지지 않는다.

- 방법3) 부모요소에 clearfix 클래스를 추가하는 방법
 이 방법은 필요시 마다 조립하여 쓸 수 있기때문에 추천한다.

## aria-hidden = "true"
- 화면에만 보이고 스크린 리더기는 읽어줄 필요없는 목록에 사용 ex) 구분선

---

## BFC(Block Fomatting context, 블록 서식 맥락)
- 레이아웃 안에 작은 레이아웃
- 블록 박스의 레이아웃이 발생하는 지점과 플로팅 요소의 상호작용 범위를 결정하는 요소

### BFC는 다음과 같은 경우에 생성됨
- html root 태그 (body 태그는 만들어지지 않는다)
- none을 제외한 float
- position: fixed, absolute
- display: inline-block, table, table-cell, table-caption
- overflow: visible을 제외한 모든 값
- display: flow-root (일부 브라우저만 동작함)
- display: flex, inline-flex, grid, inline-grid



