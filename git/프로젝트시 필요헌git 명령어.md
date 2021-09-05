# git 명령어 정리

```text
# branch 구조

	main
	 │
	 └──  develop
             │
             └──  feature
---------------------------------------------------- 원격에 만들어 놓는 건 여기 까지
                     │└── feature/login
                     └───── feature/signup
---------------------------------------------------- 로컬에서 진행(pull request보내면 원격에 자동으로 브랜치 생성됨)
```

## 1. 원격 저장소를 clone 한다.

1-1. 

```bash
git clone <원격저장소 주소>
```

1-2. 폴더에서 원격 저장소를 연결하고 pull해도 된다.

```bash
git init
git remote add origin <원격저장소 주소>
git pull origin master
```



## 2. 원격 저장소의 다른 모든 branch를 가져온다

:exclamation: 주의할점 : git clone 시 master branch만 가져옴

:exclamation: 주의할점 : 최초 update 후에 브랜치들의 최신 내용까지 업데이트되지는 않으므로 해당 브랜치에서 pull 해주어야 함

```bash
git remote update
```

2-1. 특정 원격 브랜치 로컬 브랜치에 가져오기 (tracking)

```bash
git checkout -t <원격브랜치 이름> 
ex) git checkout -t origin/develope
```

cf. `git checkout -r` // 원격 저장소에 있는 브랜치 조회

​	 `git checkout -b < 브랜치 이름 >` // 해당 브랜치를 생성하여 이동

​	 `git checkout < 브랜치 이름 >` // 해당 브랜치로 이동



## 3. branch 이동

```bash
ex)
git switch feature
```



## 4. feature에서 하위 branch 생성 및 이동

```bash
ex)
git switch -c feature/login
```

cf. git branch <브랜치 명> // 브랜치 생성

​	

## 5. 변경한 로컬 코드를 원격 브랜치에 merge하기

1. pull request를 보낸 후 원격 저장소에서 merge하는 방법

```bash
// 현재 브랜치 : feature/login
git status                   // 로컬 변경사항 확인
git add <추가할 파일이름>               // stage area에 파일 추가
git commit -m '변경사항 메세지 입력'                     // commit 남기기
git push origin feature/login                
```

이 경우 원격저장소에서 merge 할 브랜치 선택 후 merge하면 된다.



2. 로컬에서 pull 받아 동기화 한 후 merge하기

```bash
git status                   // 로컬 변경사항 확인
git add <추가할 파일이름>               // stage area에 파일 추가
git commit -m '변경사항 메세지 입력'
----------------------------------------------------stage area에 추가해놓는건 똑같다.
git switch feature                     // merge할 브랜치로 이동
git pull origin feature                // feature branch 원격코드 가져오기
git merge feature/login                // 현재 브랜치와 merge
```

이 때, 충돌 발생 시 git에서 자동으로 merging 브랜치를 생성하여 이동하게 된다. 충돌이 난 부분의 파일에 들어가서 직접 코드를 수정하고, commit하면 자동으로 원래 브랜치(feature)로 돌아가진다. 이후 push하면 원격에도 merge 된다.

