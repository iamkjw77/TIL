## GIT
<details open>
<summary>GIT 설치 및 명령어</summary>
<div markdown="1">

- `GIT` : 버전관리 1등
- `GitHub` : 클라우드 저장소

#### Git 설치
[gitforwindows](https://gitforwindows.org/) 
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
1. 원하는 폴더에서 Git 초기화를 하면 그때부터 가능 
→ `git init(깃 저장소 만들기)`
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

---