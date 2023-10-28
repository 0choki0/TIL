## What is commit?
작업의 이력을 기록하여 저장소로 보내는 행위이다. 즉, staging area에 tracked 된 파일들을 로컬 저장소에 저장하는 것이다.

### commit의 흐름
![commit_flow](../assets/git_commit.png)

- git commit -m / git commit -a -m
커밋은 staging area에 tracked된 파일들 만이 commit 명령어를 사용하여 커밋된다.
> git commit -m 'update'
기존에 추적한 파일의 변경사항을 staging에 추가하고 커밋을 하려면 다음과 같이 하면 된다.
> git commit -a -m 'update'

### 커밋 식별하기
- commit ID
각각의 commit은 고유한 식별 ID가 존재한다. 이를 통해 commit을 구분할 수 있다.
- HEAD
HEAD 참조는 항상 현재 브랜치의 끝을 참조한다. 즉, 해당 브랜치 내에서 최신의 커밋을 참조한다.
 
### git diff
git은 작업디렉토리의 변경사항, 스테이징 되어 커밋하려는 변경사항, 저장소간의 차이점을 보여줄 수 있다. 
```python
git diff
``` 
(스테이징 되지 않고 커밋되지 않은)작업 디렉토리의 untracked 파일의 변경사항을 보여준다.
```python
git diff --cached
git diff --staged
```
스테이징되어 커밋 대기상태에 있는 tracked된 파일의 변경사항을 보여준다.
```python
git diff HEAD
```
현재 작업중인 브랜치에서 가장 최신의 커밋을 보여준다.

### 작업 디렉토리의 파일 삭제

참고 https://mylko72.gitbooks.io/git/content/commit/remove.html