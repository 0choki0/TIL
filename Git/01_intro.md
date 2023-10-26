## Git, 분산버전 관리시스템

- Git은 작업파일을 로컬 뿐만아니라 *원격 저장소에도 배포하여 저장*할 수 있다.
- 작업 이력을 관리하고 **분기**하여 원하는 시점으로 파일을 **복원**하거나 **통합**할 수 있다.
- 따라서 Git은 원격저장소를 이용하여 팀 단위로 협업이 가능하고 버전별로 관리를 할 수 있다.

### Github?
: Git을 사용하는 사람들을 위한 웹기반 호스팅 서비스이다. 

### How to work git
git은 파일을 **committed**, **modified**, **staged** 세가지 상태로 관리한다.

- committed : 데이터가 *로컬 저장소에 안전하게 저장*되었다는 것을 의미한다.
- modified : 수정한 파일을 *아직 로컬 저장소에 commit하지 않은 것*을 의미한다.
- staged : 현재 수정한 파일을 곧 commit할 것이라고 표시한 상태를 의미한다. 

1. 저장소를 생성 or 복제하여 working directory 만들기
- 로컬 저장소 만들기
> git init
- 로컬 저장소 복제하기
> git clone /로컬저장소경로

2. 작업할 파일 생성하기
> touch <파일명>  
git status

파일을 추가 `touch` 명령어를 사용하여 생성할 수 있다.  
`git status`는 파일의 관리 상태를 표시하는데, commit하지 않았을 경우 untrack으로 표시된다.

3. 파일을 staging area에 추가 혹은 제거하기
- 파일 추가하기
> git add <파일명>
- 파일 제거하기
> git rm <파일명>
- 파일 캐시 삭제
> git rm --cached <파일명>

4. commit 하기
> git commit -m <설명>
commit은 변경된 소스를 저장소에 저장하는 명령으로, staging area에 있는 파일을 대상으로 이루어진다. 

5. remote 저장소에 push
> git push <원격저장소> <관리버전>
