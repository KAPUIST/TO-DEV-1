# TO DEV TIL

### GIT 기초

- Fork
  Fork란 다른사람의 git에서 자신의 레파지토리로 복사해 올수있다 포크로 집어서 복사해 온다는 의미라고 생각하시면 됩니다.

- clone
  clone 을 사용하여 자신의 리모트 레파지토리에서 다운로드 받아 로컬 레파지토리를 만들수있다
- status
  git status 명령어를 통해 staging area와 untracked files 목록에 어떤 것들이 있는지 확인할 수 있습니다.
- restore
  경사항을 폐기(discard changes) 하는 명령어예요.
- add
  add는 파일을 commit 할 수 있는 상태로 만들어 줍니다.
- commit
  staging area 안에 파일을 푸쉬가능한 파일로 만들수있다
- reset
  만약 커밋한 파일에 문제가 있어 수정이 필요하거나 할떄
  git reset HEAD^ 를사용하여 커밋을 취소시킬수있다
- log
  git status 를 통해 어떤 파일이 어떤 상태에 있는지, 그리고 해당 파일에 대해 어떤 행동을 할 수 있는지 알 수 있습니다.
- pull
  Pull Request는 내가 Remote Repository에 Push 해 놓은 변경 사항에 대해서 함께 작업하는 다른 사람들에게 알리는 것을 말합니다. 현업에서는 줄여서 PR이라고 합니다.
- push
  내 Local Repository의 commit 기록들을 Remote Repository로 업로드하기 위해서는 git push origin branch 명령어를 사용할 수 있습니다.
- init
  로컬 레파지토리에서 생성한 폴더를 깃 의 관리하에 둘수있음
- diff
  바뀐 파일이있다면 어느부분이 바뀌었는지 눈으로 확인할수있음
- remote add
- remote -v

### 배열

배열은 순서가 있는 값 값은 요소라고 부르며 element이다
순서는 index라고 하며 0부터 번호를 매긴다
비열은 대관호[] square braket을 이용해 만들수있다. 각각의 element 사이에는 comma로 구분한다

##### 배열 메소드종류

arr.pop() 맨뒤에 배열을 하나 삭제합니다
arr.push('table') 맨뒤에 'table' 을 추가합니다

arr.unshift() 맨앞에 배열을 추가합니다
arr.shift() 맨앞에 배열을 삭제합니다.

Array.isArray() 배열인지 아닌지 확인할수있습니다
console.table 배열을더 보기쉽게 나열할수있습니다.
