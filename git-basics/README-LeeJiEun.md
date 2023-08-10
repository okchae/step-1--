# Git 기초

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.
- git
   - local에서 프로젝트 기록을 스스로 관리할 수 있다. 
   - 다른 개발자와 코드를 실시간으로 공유할 수 없다. 
   - **버전 관리 '프로그램'**
- github
  - 클라우드 서버를 사용하여 local에서 버전 관리한 코드를 업로드하여 공유 가능하다.
  - **버전 관리, 소스 코드 공유, 분산 버전 제어 등이 가능한 원격 저장소**


## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.
- Working Directory
  - 실제 코드를 수정&추가하여 변경이 이루어지는 영역
  - git 이력과 관련된 정보가 저장되어 있는 .git 을 제외한 모든 영역
- git add
  - 현재 Working Directory 상의 변경 내용을 Staging Area로 이동시키는 명령어, 새로운 파일이 생겼다는 것을 알리는 행위
    - Staging Area : Working Directory 에서 Repository로 정보가 저장되기 전 준비 영역

- git commit
  - 파일 및 폴더의 변경 사항을 Local Repository에 기록하는 명령어
  - 특정 작업이 완결된 상태로 바뀌었다는 것을 의미함

- git push
  - 변경 사항을 Remote Repository에 기록하는 명령어


## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.
- branch : 독립적으로 작업을 진행하기 위한 개념
- HEAD : branch의 가장 최신 commit을 가리키는 포인터
- branch와 HEAD
  - commit을 하면 HEAD가 가리키는 branch가 최신 commit으로 이동한다.
  - <img src ="img.png" width="400" height="300"/>

  - 여기서 highlevel branch를 만들면 highlevel branch은 HEAD가 가리키던 커밋을 가리키게 된다.
  - <img src="img_1.png" width="400" height="300"/>

  - **git checkout highlevel**을 입력하면 HEAD가 highlevel branch를 가리키게 된다.
  - <img src="img_2.png" width="400" height="300"/>

  - 여기서 commit을 2번 진행하면 아래와 같이 된다.
  - <img src="img_3.png" width="600" height="300"/>

- [출처 : https://charles098.tistory.com/24]
  


## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
  - git clone : 저장소로부터 프로젝트를 복제하는 명령어
  - git init : 해당 폴더를 git으로 관리할 수 있게 해주는 명령어
  - git clone은 **기존 저장소를 복제하는 것** / git init은 **기존에 사용하던 디렉토리를 Git 저장소로 만드는 것**
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
  - origin : 깃허브 저장소 주소를 가리키는 키워드
  - git remote add origin {원격 저장소 주소} : 로컬 저장소에 원격 저장소를 등록
  - git remote remove origin : 원격 저장소를 git의 설정에서 삭제



## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.
- git reset <커밋ID> : 과거 commit 지점으로 이동하고, 이동된 이후의 commit은 삭제하는 명령어
  1. git reset –hard : 해당 커밋ID의 상태로 이동하고, Working Directory와 Index영역 모두 초기화한다.
  2. git reset –mixed : 해당 커밋ID의 상태로 이동하고, Index영역은 초기화되고 Working Directory는 변경되지 않는다.
  3. git reset –soft : 해당 커밋ID의 상태로 이동하고, Index영역과 Working Directory 모두 변경되지 않고, commit된 파일들을 staging area로 돌려놓는다.

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.
- Pull Requst(PR) 
  - 사용자가 원격 저장소에 push했을 때, 다른 사용자에게 push된 상황을 알리는 것을 말한다.
  - PR를 보내면 여러 동료들에게 리뷰를 받을 수 있고, 내가 올린 코드에 동료가 병합하여 진행할 수도 있다.
- Merge
  - git branch를 다른 branch로 합치는 과정
  - 기본 단위는 branch
  - 종류
    - Fast-Forward
    - ![fast-forward](https://wikidocs.net/images/page/153693/05.03.01.jpg)
      - Fast-foward 상태 : master와 dev1이 각각 가리키는 commit은 동일 선상에 위치하고 있다. 이때 두 branch는 Fast-foward 상태에 있다고 한다.
      - 새로운 commit이 생성되지 않는다.
      - 빨리 감기(fast-forward) : 뒤에 쳐진 branch(master)의 참조 개체가 앞서있는 branch가 가리키는 개체를 참조하도록 이동한다.(마치 브랜치가 점프 하듯)
      - 사용 예 : master로 개발을 진행하다 어떤 내용을 수정해야 하는데, master에서 테스트하기 힘든 경우 다른 branch로 해당 내용을 수정하고 후에 합병할 때 사용
    - 3-Way Merge
    - ![3-way merge](https://wikidocs.net/images/page/153693/05.03.03.jpg)
      - 두 브랜치 모두 base에서 commit을 진행해서 분기해 나간 상태가 되었다. 두 브랜치 중 어느 것도 base에 위치하지 않는다.
      - 새로운 commit이 생성된다. 
      - 3-way : 내용을 병합할 때, base와 각 브랜치 2개가 참조하는 commit을 기준으로 병합을 진행하기 때문이다.



## rebase
![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

## stash
![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

## Advanced
다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다. 
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지. 
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push/pull --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 `parent/child-1`, `parent/child-2`는 가질 수 있지만 `parent`, `parent/child`는 가질 수 없다. 무슨 이유 때문인지. 
- 리포지토리의 두 타입인 bare, non-bare

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.