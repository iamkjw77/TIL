패스트캠퍼스-git 수업을 듣고 중요 내용을 정리합니다.

## 버전관리

- 원하는 시점마다 깃발을 꽂고(버전을 만들고) 이들 간에 자유롭게 돌아다닐 수 있다.
- 내가 만든 버전 뿐 아니라 동료가 만든 버전으로 이동할 수 있고, 동료와 내 버전을 비교해서 최신으로 코드를 업데이트 할 수 있다.

---

## 버전 만들고 올리기

1. 변경한 파일을 선택해서 <mark>add</mark>하기
```bash
$ git add readme.md
```

2. 선택한 파일들을 <mark>commit</mark>하고 설명 적어주기(vim으로 작성하는 습관을 들이자!)
```bash
$ git commit // 내용 작성 후, esc :wq
```

3. git 파일 상태 확인하기
```bash
$ git status 
```

4. 원격 저장소에 <mark>push</mark>하기
```bash
$ git push // 처음에만 git push origin master
```

---

## 원격저장소 → 로컬저장소 복사하기

다른 사람이 만든 저장소를 복사하거나, 나의 원격저장소를 로컬저장소에 복사하고 싶은경우
clone 해서 파일을 받아오면, .git(로컬저장소) 파일이 자동으로 생기면서 init, remote, add과정이 생략됨(자동으로 원격저장소와 연동됨)

- GitHub에서 저장소 주소 복사 후, <mark>clone</mark>하기
```bash
$ git clone https://github.com/아이디/이름.git .
```