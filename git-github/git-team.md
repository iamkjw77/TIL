<details open>
<summary>GIT team으로 작업하기</summary>
<div markdown="1">

#### 브랜치(Branch)

- 각각의 구현작업마다 독립된 브랜치를 만들어 구현작업을 진행한다.
- 구현 작업이 성공적으로 마무리되면 그 작업 브랜치를 master 브랜치에 병합한다.
- 구현 성공하고 테스트를 통과한 브랜치만 마스터 브랜치에 병합한다.
- 어떤 새로운 기능의 구현을 시작할 때, 마스터 브랜치의 코드를 새 브랜치로 복사해서 작업을 시작하면 된다.
- 지금 구현하던 작업을 잠시 중단하고, 새 작업을 시작해야 한다면, 지금 작업하던 브랜치를 잠시 그대로 놔두고, 새 브랜치를 만들어 구현 작업을 시작하면 된다.
- 잠시 중단했던 브랜치로 돌아와서 작업을 계속하면 된다.

##### master branch

- `git repository`에서 `master` 브랜치가 디폴트 브랜치이다.
- `master` 브랜치는 `git repository`를 만들 때 자동으로 생성된다.

##### 현재 작업 브랜치

- 소스코드를 수정하고 커밋을 하면, 이 커밋은 현재 작업 브랜치의 소속된다.
- `git repository`에는 HEAD 이름의 참조가 있는데, 이 참조는 현재 작업 브랜치를 가리킨다.

- `git branch`
  : 현재 브랜치들을 출력

- `git branch –h`
  : -h는 help 옵션으로 어떤 명령어를 사용할 수 있는지 도와줌

- `git branch 브랜치이름`
  : 해당 브랜치 생성
  ex) `git branch header`

- `git checkout 브랜치이름`
  : 해당 브랜치로 이동해라(공간의 이동)
  : HEAD가 cat으로 옮겨감

- `git checkout 커밋아이디`
  : 해당 commit으로 이동(시간의 이동, 이동했다면 새브랜치를 만들어야함)
  : 커밋아이디는 `git log`시, `commit message 앞 6자리`

- (header 브랜치 안)
  `cat index.html`
  : master에서 commit하기 전의 상태를 불러옴
- `vi index.html`
- `git add index.html`
- `git commit`
- `cat index.html`
  : 내용 작성 후, add commit, 내용확인
  `git checkout master` // master로 돌아감
  `cat index.html` // 내용확인
  `git merge header` // header 작업을 끝내고, 병합

#### 머지(merge)

- `feat` 브랜치에서 작업이 끝남 → 이제 `master`에 합치면 됨
  (기능 개발이 끝나면, 그 커밋들을 이제 마스터에 합치면 됨)

- 방법

1. 먼저 base가 될 master 브랜치로 이동(HEAD가 이동)
2. compare 브랜치인 oct를 나와 합치고 싶다라고 명령
   : `git merge oct`

#### 컨플릭트(conflict)

- 합치다가 충돌이 난 경우
- 머지할 때 두 버전이 같은 곳을 수정했다면 이를 수동으로 고쳐줘야 한다.

- 충돌 실습)
- `git branch footer`
- `master`에서 `vi index.html` 작성 후, `add, commit`
- footer 브렌치로 checkout후, master에서 수정한 부분 수정 후, add commit
- 다시 master로 checkout후, (`git checkout master`) 병합(`git merge footer`)
- conflict (에러가 아님)
- 충돌난 부분 고쳐주기, `vi index.html`
- 수정 후, 저장 나가기(수정 내용은 2개 중 1개를 고르거나 새로 만들어서 저장)
- 수정 내용 머지하기(`git add index.html`, `git commit` 수정된 내용 상세히 작성)

※ 작업이 끝난 브랜치들은 꼭 지워주기
`git branch –D footer` (footer브랜치 지우기)

※ branch push

- push하지 않는 이상, 원격저장소에서 branch를 볼 수 없음
- `git push –u origin` 브랜치이름 // 원격저장소에 해당 브랜치가 올라감, -u(upstram)은 처음에만 쓰면됨
- `git push –u master` // 참고가 필요한 브랜치만 원격저장소에 올리고, 나머지는 merge하자

#### 저장소 통째로 복제하기 : 포크(fork)

※ 포크가 아닌 콜라보레이터를 주는 경우(위험)

- 해당 저장소에서 콜라보레이터는 모든 것을 할 수 있음
- 해당 저장소의 주인인 것처럼, push 할 수 있음
- 따라서 포크&머지를 추천

#### 풀 리퀘스트

- 이 커밋이랑 저 커밋을 합치는 걸 허락해줘

1. 머지하고 싶은 두 브랜치를 선택하고
2. 어떤 변경을 했는지 제목과 내용에 쓰면 됨
3. 단일 저장소에서 보낼 수도 있고, 이렇게 포크란 저장소에서도 보낼 수 있음.

- 풀 리퀘스트로 머지 요청 보내기

1. 코드를 함께 작성하는 팀원이 있다면, 최대한 직접 머지하는건 피하고 모든 머지를 풀 리퀘스트를 통해서 한다.
2. 동료가 내 풀 리퀘스트(PR)을 보고 코드를 리뷰할 수 있다.
3. 동료의 PR에 수정이 필요하면 댓글을 달아 change request를 보낼 수 있다.
4. 오픈소스에 PR을 보낼때는 ‘기여 안내문서(contribution guideline)’을 반드시 참고해야 한다.

##### TIP : 브랜치 관리하기

1. 보통 `feat/기능이름`으로 한 사람이 개발하는 기능 브랜치를 만든다.(혹은 fix/버그이름, hotfix/급한버그)
2. 작업이 끝나면 dev(혹은 master) 브랜치로 PR을 보낸다.
3. dev 브랜치에서 큼지막한 작업이 모두 머지되면 `release`(혹은 latest)브랜치로 머지시키고, 이를 실서버에 배포한다.
4. 직접 커밋은 feat(혹은 fix, hofix)브랜치에만 합니다.
5. dev나 master, release 브랜치에는 직접 커밋하지 말고 머지만 한다.

#### branching model

1. `git flow`
   `git flow release ~` : 사람들에게 공개적으로 배포할 때
   `(hotfix) - master - (release) - develop – feature`
   : 뒤에서부터 해석, hotfix는 빠르게 고칠 때(공개했는데 위험한 버그가 났을 때)
   : 거의 develop-feature 사용

2. `git flow` 사용하기
   : 원본 소스코드와 분리해서 작업하기 위해 사용, 만약 잘못되면 해당 브렌치만 날리면 됨

- `git flow` : flow를 쓸 수 있는 상태인지 점검
- `git flow init` : flow 설치
  <br />

![git flow 시작](../images/git_flow.PNG)

- `git flow feature start 기능이름` : 지금부터 기능개발 시작
  ex) `git flow feature start style-init` // 지금부터 `style-init` 기능개발시작, 자동으로 `feature/style-init`으로 이동

- 실습1) style-init 안
- static/css/style.css 파일 만들어서 index.html link로 연결하기
- `git add index.html`
- `git add static/css/style.css`
- `git commit`
- `git flow feature finish style-init` : develop과 style-init이 병합되고, style-init 브랜치는 자동으로 삭제됨

- 실습2)
  `git flow feature start create-sauron`
  `git touch sauron.html`
  `git add sauron.html`
  `git commit`

※ 만약 해당 브랜치를 지우고 싶은 경우)
`git checkout develop → git branch –D feature/create-sauron`

- 실습3)
  `git flow feature start create-aside`
  `vi index.html` 수정후
  `git add, commit`
  `git flow feature finish create-aside`
  `git flow release start v0.0.1(공개할 이름)`
  `git flow release finish v0.0.1`

1. 마스터 커밋메세지
2. 버전 태그메세지 (커밋 메시지가 아닌 태깅, 0.0.1버전에 무슨 버그가 수정되었다.)
3. develop에 달아줄 커밋메세지

#### 팀실습

1. 팀장

- 새로운 원격저장소 만든다.
- `git clone 자신의 원격저장소 주소`
- `git flow init`
- `git branch`
- `touch index.html`
- `git status`
- `git add index.html`
- `git commit`
- `git push –u origin develop`(clone하면, master의 –u는 쓸 필요X)

2. 팀원

- 팀장의 저장소에 방문해 `fork`
- `git clone 자신의 원격저장소`
- `git branch`
- `git flow init`
- `git flow feature start 브랜치이름`
- 팀장의 원격저장소에서 `issue` 생성(issue 선, 풀 리퀘스트 후로 작업)
- 수정 후, `git add`
- commit 메시지 작성 시 issue 넘버도 같이 작성(`solved: #1`)
- 풀 리퀘스트와 이슈는 넘버링되기 때문에, 같은 넘버로 연결해줘야 함
- `git flow feature finish 해당 브랜치이름`
- `git push origin delvelop`
- 나의 원격저장소에 가면 풀 리퀘스트가 생김
- 풀 리퀘스트 생성 후, 맨 위에 화살표 꼭! 확인하기(`팀원 develop → 팀장 develop`)
- 팀장이 수정사항 있으면, 코멘트 후 팀원은 다시 수정 후 add, commit, push
- branch가 open된 상태는 merge 전 상태
- 팀원이 팀장의 수정사항을 위해 수정할 때, 아직 open된 상태이기 때문에 바로 수정할 수 있음
- 팀장은 comment 메시지 작성 후, merge를 하면 닫아짐 (꼭 닫아줘야함!)

※ 팀원은 팀장의 파일을 당겨오고 작업하자(feature start 전에 작업하자!!)

- `git remote –v`
- `git remote add pmorigin 팀장주소`
- `git pull pmorigin develop`

※ 팀장은 자신의 것을 pull

- `git pull origin develop`

- 팀원이 작업하는 곳은 fork한 곳(자신의 원격저장소)
- 팀장의 것을 당겨오는 것은 pmorigin(팀장의 원격저장소)

※ 팀장의 원격저장소를 pull하지 않을 경우

- 빨간색 X 상자가 나옴
- `git pull pmorigin develop`
- 해결 후, `git add index.html`
- `git commit`
- `git push origin develop`

[참고](https://www.youtube.com/watch?v=jM7qRHXFin4&feature=youtu.be)

#### GIT 더 알아보기

- `rebase` : 묵은 커밋을 새 커밋처럼 조작하고 싶어요.(장점 : 충돌이 안나는 상태로 만들 수 있음)
- `amend` : 깜빡하고 수정 못 한 파일이 있어요, 방금 만든 커밋에 살짝 추가할래요.
- `cherry-pick` : 저 커밋 하나만 떼서 지금 브랜치에 붙이고 싶어요.
- `reset` : 옛날 커밋으로 시간을 돌리고 싶어요.
- `reverse` : 이 커밋으로 변경사항을 되돌리고 싶어요.
- `stash` : 변경 사항을 잠시 킵해두고 싶어요. 아직 커밋은 안 만들래요.

<div>

---
