## GIT
<details open>
<summary>GIT 설치 및 명령어</summary>
<div markdown="1">

- `GIT` : 버전관리 1등
- `GitHub` : 클라우드 저장소

#### Git 설치
https://gitforwindows.org/ 
- 공식 사이트보다 위의 사이트가 팀플 시 유용한 기능이 더 많음

#### Git 환경설정
`$ git config --list` : 정보먼저 확인
`$ git config --global user.name "jiwon"` : username 설정
`$ git config --global user.email "iamkjw77@naver.com"` : 이메일 설정
`$ git config --global core.editer "vim"` : 에디터 vim으로 설정
`$ git config --global core.pager "cat"`
`$ git config --list` : 잘 반영됐는지 정보 확인

#### 버전관리
- 원하는 시점마다 깃발을 꽂고(버전을 만들고) 이들 간에 자유롭게 돌아다닐 수 있다. 
- 내가 만든 버전 뿐 아니라 동료가 만든 버전으로 이동할 수 있고, 동료와 내 버전을 비교해서 최신으로 코드를 업데이트 할 수 있다.

#### GIT을 사용하는 2가지 방법
- `CLI(Command Line Interface)` : 명령어를 사용하여 사용
- `GUI(Graphical User Interface)` : 소스트리 같은 가시적인 인터페이스를 사용

#### GitHub에 코드를 올리는 과정(간단히)
- 내 컴퓨터 프로젝트 폴더에 ‘여기에 Git을 쓸거다!’ 라고 명령 → `git init`
- 내가 변경한 파일 중 올리길 원하는 것만 선택 → `git add`
- 선택한 파일들을 한 덩어리로 만들고 설명 적어주기 `git commit –m “첫 페이지 제작”`
(여기서 덩어리는 commit, 하나의 버전임)
- 내 컴퓨터 프로젝트 폴더에 GitHub 저장소 주소 알려주기 `git remote add 저장소 주소`
- 내 컴퓨터에 만들어진 덩어리 GitHub에 올리기 `git push`

#### GitHub에 코드를 올리는 과정(자세히)
1. 원하는 폴더에서 Git 초기화를 하면 그때부터 가능 → `git init(깃 저장소 만들기)`
※ Git 저장소 지우기 : `rm -rf .git`
2. Git 초기화를 하면 `.git`이라는 숨겨진 폴더가 만들어진다. (이것이 로컬저장소)
3. 로컬저장소에서 내가 만든 버전 정보, 원격 저장소 주소 등이 저장된다.
4. 원격 저장소에서 내 컴퓨터로 코드를 받아오면 로컬 저장소가 자동으로 생긴다.
5. 한 폴더에 하나의 로컬 저장소만 유지해야 한다.

#### 리눅스 명령어
- `$` : shell에서 작성한 것, 쉘 명령어
- `~` : 로그인 유저의 최상단이라는 뜻
- `$ pwd(print working directory)` : 현재 나의 위치
- `$ ls(list segment)` : 해당 디렉터리 내에 있는 디렉터리, 파일을 출력
ex1) `ls –a(all)` : 숨김 파일까지 모두 표시, 파일이름 앞에 .이 있으면 숨김 파일
ex2) `ls –l(list)` : 파일의 정보가 리스트로 나타남
ex3) `ls –al` : 모든 파일 & 파일의 정보가 리스트로 나타남 
tip) 파일이름이나 폴더이름을 몇 글자만 쓰고 tab을 누르면 자동완성이 됨

- `$ cd(change directory)` : 디렉터리 변경
ex) `cd ..` : 상위폴더로 올라가기

- `$ mk(make directory)` 디렉터리이름 : 디렉터리 생성
- `$ touch 파일이름` : 파일생성
(파일 생성이 안 되는 파일: pptx, hwp등 app을 사용해서 생성해야하는 파일, app이 미리 준비되어있으면 생성됨)

- `$ mv 파일이름 옮길장소` : 파일 옮기기 
ex) `mv style.css static`, `mv ../index.js .`(상위에 있는 index.js를 현재위치로 이동)
`.` : 현재폴더, `..` : 상위폴더

- `$ mv 파일이름 수정된 파일이름` : 파일이름 바꾸기
ex) `mv index.js server.js`

- `$ mv 파일이름 바꿀 파일이름` : 파일 포맷 바꾸기
ex) `mv index.html index.md`

- `$ cp 파일이름 복사할 장소` : 파일 복사
ex) `cp index.js ..` : 상위폴더로 index.js 복사

- `$ cat 파일이름`
: 파일 내용 출력

- `$ rm 파일이름` : 파일삭제
ex) `rm server.*` : server로 된 모든 파일들 삭제
ex) `rm *.db` : 모든 db파일 삭제

- `$ rm –r(recursive) 폴더이름/` 
: 디렉터리 지우기(모든 하위명령어를 지우고 자신도 지워라)
ex) `rm –rf subway/` 

- `$ rm –rf(remove recursive force)` : 사용자가 지정한 위치 내의 모든 파일과 폴더를 강제로 삭제(※사용주의)

- `$ chmod [옵션] (8진수) (파일명)` : 파일 권한 설정
(user)(group)(other) r: read w: write x: execute -: no permission
8진수 0: 000 1: 001 2: 010 3: 011 4: 100 5: 101 6: 110 7: 111

ex1) `chmod 777 readme.md` : 모든 사람에게 권한주기
ex2) `chmod 755 readme.md` : user는 모든권한 허용, 나머지는 읽고 실행만 가능 

- `ctrl + c` : 명령중단
- `vi readme.txt` : vim으로 readme.txt를 열어라
(vim으로 쓰는 연습하기!!)
- `code readme.txt` : VS코드로 readme.txt를 열어라

##### vim 모드(VS코드, 크롬에 확장기능이 있음)
- `normal모드 → insert모드` : i(하단에 끼워넣기 모드로 바뀜)
- `insert모드 → normal모드` : esc
- `o` : insert모드에서 아랫줄로 이동
- `O` : insert모드에서 윗줄로 이동
- `h j k l` : normal모드에서 화살표역할
- `:wq` : 저장 후 나가기
- `:q!` : 저장 안하고 나가기(커밋 취소)
- `:q` : 그냥 나가기
- `:set nu` : 줄번호 보기
- `vim README.md` : README.md 수정

#### Git 명령어
- `git status` : git 파일들 상태 확인, git 저장소인지 확인하는 방법
- `git log --oneline` : 로그를 한 줄로 보여줘
- `git commit –am "커밋메세지"` : 한 번 이상 연속으로 commit한 경우 사용하면 add를 안하고 바로 commit됨

#### Git에서의 커밋이란?
- 변경 사항의 모음(x) 하나의 최종 모음(o)
- 다만 기존 커밋과 비교해서 변경된 파일이 아니면 ‘변경되지 않았다’고만 저장해서 용량이 무겁지 않다.

#### commit 간단한 제목 작성법
- `docs`: 문서작업
ex) `docs: Create README.md`(제목 첫 글자는 대문자)
- `feat`: 기능개발
- `fix`: 버그수정
- `refactor`: 같은 기능을 더 간결하게(리팩터링)
- `test`: 테스트코드
- `ci`: 기능나열
- `conf`: 프로젝트가 돌기위한 환경 구성들
(제목은 되도록 영어로 작성!!)

##### commit 간단한 내용 작성법(mark down형식)
[commit message tip](https://www.conventionalcommits.org/en/v1.0.0-beta.2/)

```
<h1></h1>
# First Repo

## Abstract

This repo is the first repo in my life.

## Installation


\```html 
//사용할 언어이름, ``` 여기 안은 html <pre>와 같이 나타남
<pre></pre>
<p>no install required.</p>
\```

## Features

- feature 1
- feature 2
- feature 3

~~canceled feature.~~ //취소선

--- //구분선

## How to Contribute
1. Send me a mail shortly.
2. Make issue on issue tab.
3. Fork and Create Pull Request.
4. Wait for my `Merge`.

## Screenshot
<img src="https://github.com/download.jpg" alt="download img">
![download img](https://github.com/download.jpg)

## Reference
- github: [github](https://github.com/)
- pydoc: [pydoc](https://docs.python.org/)
- [node](https://www.nodejs.org/)
```

#### Git 의미있게 사용하기
- 커밋은 ‘의미 있는 변동사항’을 묶어서 만든다.
ex) 버튼 변동사항을 한 묶음으로 커밋 등 의미있게 커밋하자!
- 커밋 메시지를 시간 들여 작성하기
- 커밋은 기차처럼 쌓인다.

#### 로그를 축약해서 보는 방법(깃 저장소 안에서만 가능)
$ `git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"` 입력 후, `git lg(alias log)` : 로그를 축약해서 볼 수 있음

#### GitHub 페이지 사용법
- `+`버튼 항목 의미
1) `New repository` : 새로운 저장소 만들기
2) `Impory repository` :　저장소 가져오기
3) `New gist` : 새로운 코드 조각 올리기
4) `New organization` : 팀프로젝트 조직 만들기

##### New repository 클릭 시
- 마지막 `Add .gitignore` : 무시하고 올리고 싶은 파일 선택

#### 다른 사람이 만든 저장소 받아오기 
- 원격 저장소를 내 컴퓨터에 받아오기 : `클론(Clone)`
- 내 컴퓨터에 받아올 폴더 공간을 만들고 GitHub에서 받아올 저장소 받아오기
→ `git clone https://github.com/아이디/이름.git .`
- `clone` 해서 파일을 받아오면, `.git(로컬저장소)` 파일이 자동으로 생기면서 `init, remote add`과정이 생략됨(자동으로 원격저장소와 연동됨), 그래서 `push`을 하면 자동으로 원격저장소에 들어감
- `Download ZIP`은 위의 `.git(로컬저장소)`가 생기지 않고, 그냥 파일만 다운로드됨

#### git stash 
- 아직 마무리하지 않은 작업을 스택에 잠시 저장할 수 있도록 하는 명령어
- 이를 통해 아직 완료하지 않은 일을 commit하지 않고 나중에 다시 꺼내와 마무리 할 수 있다.

- `git stash` : 새로운 stash를 스택에 만들어 하던 작업을 임시로 저장한다.
- `git stash list` : 여러 번 stash를 했다면 위의 명령어를 통해 저장한 stash 목록을 확인할 수 있다.
- `git stash apply` : 위의 명령어를 통해 했던 작업을 다시 가져온다. (가장 최근의)
- `git stash apply [stash 이름]` : 해당 shash의 작업을 가져온다.
- `git stash apply —index` : 위 2개의 명령어로는 Staged 상태였던 파일을 자동으로 다시 Staged 상태로 만들어 주지 않는다. --index 옵션을 주어야 Staged 상태까지 복원한다. 이를 통해 원래 작업하던 파일의 상태로 돌아올 수 있다.
- `git stash drop` : 가장 최근의 stash를 제거한다. 
- `git stash drop [stash 이름]` : 해당 stash를 제거한다.
- `git stash pop` : 적용과 동시에 스택에서 stash를 제거
- `git stash show –p | git apply –R` : 가장 최근의 stash를 사용하여 패치를 만들고 그것을 거꾸로 적용한다.(실수로 잘못 stash 적용한 것을 되돌리고 싶으면 위의 명령어를 이용)
- `git stash show –p [stash 이름] | git apply –R` : 해당 stash를 사용하여 패치를 만들고 그것을 거꾸로 적용한다.(실수로 잘못 stash 적용한 것을 되돌리고 싶으면 위의 명령어를 이용)

#### 소스트리(SourceTree) 설치 – GUI 환경 구축
1. 버튼 클릭으로 Git 명령을 실행할 수 있는 도구, 소스트리 설치
Git 개념을 그래프로 가시적으로 볼 수 있어 편리하다.
2. 설치한 소스트리에 내 컴퓨터에서 이미 만든 로컬 저장소 추가하기 (Add – 탐색 – 로컬저장소 선택 후 확인)
3. 변경된 파일이 있으면 커밋을 눌러주고, +버튼을 눌러서 스테이지에 올리기
4. 커밋 메시지는 하단에 작성 후, 커밋
5. history를 누르면, master와 origin/master가 생기는데 master는 내 컴퓨터에만 있는 것, origin이 붙은 것은 GitHub에도 있는 것 → 따라서, master를 누르고 push 눌러서 master 선택 후 push
※ 변경된 파일을 받아올 때는 pull 누르고 시작! 

[참고](https://github.com/ulgoon)
[참고2](https://wayhome25.github.io/)

<div>
<details>

---
<details open>
<summary>GIT team으로 작업하기</summary>
<div markdown="2">

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
<details>

---