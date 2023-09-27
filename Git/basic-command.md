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
    - `git add <file/folder name>/` : working directory에서 `staging area`로 추가 
    - `git add .` : 모든 파일, 폴더를 추가하기 위해 사용하는 코드

- `commit`
    - `git commit -m "메세지"`
    - `staging area`에 올라간 파일들의 스냅샷을 찍어서 `.git directory`에 저장
    - 일반적으로 `-m` 옵션을 넣어서 메세지를 추가하여 등록

- `log` 
    - q를 누르면 log에서 나올 수 있다.



## 원격저장소에 업로드하기

- `remote add`
    - `git remote add <원격저장소이름> <URL>`  
    &nbsp; : 원격저장소 주소를 <원격저장소이름> 이라는 이름으로 저장

- `push`
    - `git push <원격저장소이름> <브랜치이름>`  
    &nbsp; : 원격저장소에 브랜치를 업로드


## 원격저장소에서 가져오기

- `pull`
    - `git pull <원격저장소이름> <브랜치이름>`  
    &nbsp; : 원격저장소에 등록된 브랜치를 다운로드

- `clone`
    - `git clone <복사할 주소>`  
    &nbsp; : 원격저장소에 등록된 브랜치를 로컬에 가져와서 새로이 폴더를 만듬.  
    &nbsp; clone을 위해서 TERMINAL에서 git clone을 입력한다. 
    &nbsp; &nbsp; `clone`을 할 경우 인지되어있는 저장소에서 브랜치를 가져온 것이기 때문에 따로 remote나 init을 할 필요가 없다.

- `fork`  
    git에 올라와있는 code가 public이 아니면, 로컬에서 push하거나 pull 할 수 없다. 따라서 새로이 code를 clone 해야한다. 이를 fork라 한다.  


## 코드 공유하기
    
- ***협업***  
&nbsp; repository의 권한이 있는 사람이라면 `push` 와 `pull` 을 이용하여 내용을 update 할 수 있다.

- ***충돌***  
&nbsp; 협업 도중에 서로 *같은 line을 수정는 경우 등* 충돌이 일어날 수 있다. 선행자A가 update한 내용이 후행자B 충돌이 일어날 경우 B의 push는 오류가 생긴다. 이때 B는 repository를 pull하여 충돌이 일어난 부분을 확인할 수 있다.  
 &nbsp; VS code의 확장 프로그램인 *open in browser* 이 설치되어 있다면, 충돌이 일어난 부분을 쉽게 수정할 수 있다.

- ***Request***  
&nbsp; : 코드를 fork후 clone 이후에 나의 code를 push 할 순 없지만 request로 코드를 공유할 수 있다. 
    - clone과 remote 설정을 한 뒤, 수정 작업 후 push 한다.
    - Repository에서 *pull request*로 들어가서 메세지와 함께 pull request를 생성한다. 
    - request를 받은 사용자는 code review, merge 등을 수행한다.

## Branch  
&nbsp; `branch`는 code를 복사하고 원래의 code와는 상관없이 *독립적으로 개발을 진행*할 수 있게 도와주는 기능을 한다.  

- ***조회***  
&nbsp; `git branch` : 현재 브랜치의 위치를 확인할 수 있다.  
&nbsp; `git branch -a` : 로컬 브래친와 원격저장소의 브랜치를 전부 확인할 수 있다.  

- ***생성***  
&nbsp; `git branch <name>` : name의 이름으로 branch를 현재 head에 생성한다.  

- ***이동***  
&nbsp; `git switch <branch name>` : 해당 브랜치로 이동한다.  
&nbsp; `git switch -c <branch name>` : 해당 브랜치를 생성하면서 브랜치로 이동한다.  

- ***삭제***  
&nbsp; `git branch -d <branch name>` : 브랜치를 지우지만, 해당 브랜치를 지울 경우 문제가 생기면 error가 난다.  
&nbsp; `git branch -D <branch name>` : 브랜치를 지운다.  

- ***병합***  
&nbsp; `git merge <branch name>` : 현재의 브랜치에 해당 브랜치(branch name)을 병합한다.  

- ***Rebase***


