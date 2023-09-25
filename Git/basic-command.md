# basic command

> Git의 basic 문법을 학습해보자

## 초기 설정
- 다음의 과정은 git을 설치 후 한번만 실행하면 된다.
```bash
git config --global user.email <email>
git config --gloobal user.name <name>
```

## git 저장소 만들기

- `git init` 
    - `.git directory`를 생성해주는 명령어 / 관리하고 싶은 최상위 위치에서 실행

## 코드 수정하고 저장소에 저장하기

- `status`
    - `git status` : 현재 git으로 관리되고있는 파일/폴더의 상태를 출력
    
- `add`
    - `git add <file/folder name>` : working directory에서 `staging area`로 추가 
    - `git add .` : 모든 파일, 폴더를 추가하기 위해 사용하는 코드

- `commit`
    - `git commit -m "메세지"`
    - `staging area`에 올라간 파일들의 스냅샷을 찍어서 `.git directory`에 저장
    - 일반적으로 `-m` 옵션을 넣어서 메세지를 추가하여 등록

- `log` 
    - `log`가 길 경우 q 눌러서 나오면 됨



## 원격저장소에 업로드하기

- `remote add`
    - `git remote add <원격저장소이름> <URL>`
    - 원격저장소 주소를 <원격저장소이름> 이라는 이름으로 저장

- `push`
    - `git push <원격저장소이름> <브랜치이름>`
    - 원격저장소에 브랜치를 업로드


