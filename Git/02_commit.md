## What is commit?
작업의 이력을 기록하여 저장소로 보내는 행위이다. 즉, staging area에 tracked 된 파일들을 로컬 저장소에 저장하는 것이다.

### commit ID
각각의 commit은 고유한 식별 ID가 존재한다. 이를 통해 commit을 구분할 수 있다. 

### commit의 흐름
![commit_flow](../assets/git_commit.png)

- git commit -m / git commit -a -m
커밋은 staging area에 tracked된 파일들 만이 commit 명령어를 사용하여 커밋된다.
> git commit -m 'update'
기존에 추적한 파일의 변경사항을 staging에 추가하고 커밋을 하려면 다음과 같이 하면 된다.
> git commit -a -m 'update'