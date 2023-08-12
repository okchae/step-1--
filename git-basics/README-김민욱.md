# Git 기초

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

**개인 컴퓨터에서 사용하는 git을 local git이라 부르며, github나 gitlab과 같은 클라우드에 저장하는 git을 remote git이라고 한다.**

### Git

git은 본인의 코드와 수정내역을 기록하고 관리하는 버전 관리 프로그램으로 로컬에서 프로젝트의 기록을 스스로 관리할 수 있도록 해줌
git을 통해 브랜치 생성, 삭제, 복구, 병합이 가능하지만 로컬 저장소를 사용하기 때문에 협업시 사용이 불가능함

### GitHub

github는 git저장소를 관리하는 호스팅 서비스로 다른 사람과 소스코드 공유가 가능하며 한 프로젝트에 여러 명의 사람이 참여하여 버전 제어 및 공동 작업이 가능하다. 즉, git으로 관리하는 프로젝트를 올려둘 수 있는 사이트로 github외 gitlab, bitbucket 등 여러가지 사이트가 있다.

## Git Workflow

![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

### Working Directory

사용자의 현재 작업 공간으로 실제 파일을 수정하거나 생성하는 공간

- 2가지 상태

1. untracked - 아직 tracking이 되지 않은 파일 : 새로 생성한 파일이거나 변경된 상태가 없는 파일
2. tracked - unmodified/modified로 나눌 수 있음. : modified는 수정사항이 있지만 스테이지 영역으로 옮겨지지 않은 파일로 modified된 파일만 스테이징 영역으로 갈 수 있다.

### Git Add

Working Directory상의 변경 내용을 스테이징 영역에 추가한다.

### Git Commit

현재 버전의 코드(스테이징 되어 있는)를 로컬 저장소에 기록한다.

### Git Push

로컬 저장소에 저장된 변경 이력을 원격 저장소에 반영한다.

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

### Commit

git에서 commit은 프로젝트의 현재 스테이징된 변경 사항의 스냅샷을 캡처한 것이다.

### branch

branch는 독립적으로 특정 작업을 진행하기 위해 하나의 버전에서 분기되어 생성된 것으로 여러 작업을 동시에 진행 할 수 있게 한다.

- branch 생성
  git branch [branch 이름]
  git checkout -b [branch 이름]
- branch 삭제
  git branch -d [branch 이름]
- branch 이동
  git checkout [branch 이름]

### HEAD

모든 branch에는 HEAD가 존재하는데, HEAD는 해당 브랜치의 마지막 commit을 가리킨다.

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git 저장소 생성 방법에는 git init과 git clone이 있음

### git init

현재 디렉토리를 git local 저장소로 설정하는 명령어
local -> remote 방향
이용 방법: git으로 관리하기를 원하는 디렉토리에서 $git init

### git clone

이미 만들어진 remote 저장소를 들고오는 명령어
remote -> local로 git repository를 복제해온다.
이용 방법: $git clone [로컬 저장소 경로]

### origin

origin은 원격 저장소의 경로 이름을 의미한다.
git remote add origin [url]형식으로 원격 저장소를 추가하거나
git clone을 통해 원격저장소를 복사하면 자동으로 origin이라는 이름의 원격 저장소가 등록된다.

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

사용법: $ git reset [commitId]

### --hard

해당 commitId의 상태로 이동하고, Working Directory와 스테이징 영역을 모두 초기화한다. 해당 commitId 이후의 모든 내용을 지운다.

### --mixed

해당 commitId의 상태로 이동하고, 스테이징 영역은 초기화되고 Working Directory는 변경되지 않는다. 즉 git add가 실행되기 직전의 상태로 돌아간다.

### --soft

해당 commitId의 상태로 이동하고, 스테이징 영역과 Working Directory모두 변경되지 않는다. 즉 git add가 실행된 직후의 상태로 돌아간다.

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

### Pull Request

Pull Request란 다른 사용자가 작성한 저장소에서 변경 사항을 병합(merge)하기 위한 요청을 의미한다.

Pull Request는 다음과 같은 기능을 제공한다.

- 원본 저장소 소유자에게 코드 변경 사항을 알린다.
- 변경 사항의 리뷰를 받는다.
- 코드 변경 사항이 다른 사람들과 공유될 수 있다.

### Merge

git branch를 다른 branch로 합치는 과정이다.

1. Fast Foward Merge
   가장 기본적인 merge로 현재 branch의 HEAD를 대상 branch의 HEAD까지 옮기는 merge이다.
   사용 방법:
   git switch [현재 branch]
   git merge [대상 branch]
   ![Alt text](image.png)
   사진의 bugfix 브랜치의 이력은 master branch의 이력을 모두 포함하고 있기 때문에 master branch 상태가 변경되어 있지 않으면 master branch는 단순히 이동하기만 해도 bugfix branch의 내용을 적용할 수 있다.
   ![Alt text](image-1.png)

   하지만 bugfix branch로 분기한 후에 master branch에 여러 변경 사항이 적용되는 경우 master branch의 변경 내용과 bugfix branch의 변경 내용을 하나로 통합해야 한다.
   ![Alt text](image-3.png)
   따라서 양쪽의 변경을 가져온 merge commit을 실행하게 된다. (이게 3-Way-Merge로 진행되는 것인가...?)
   ![Alt text](image-4.png)

   만약 두 branch가 같은 부분을 수정했다면 conflict가 생기게 되는데
   ![Alt text](image-2.png)
   conflict를 해결하기 위해 변경 사항을 잘 반영해서 commit을 해주어야 한다.

2. 3-Way Merge
   merge할 때 각 branch의 마지막 commit과 branch의 공통 조상 commit 총 3개의 commit을 비교하여 새로운 commit을 만들어 병합을 수행한다.
   하나의 branch와 다른 branch의 모든 변경 이력을 합치는 방식으로 진행된다.
   base를 기준으로 변경사항이 있는 파일들을 merge commit에 반영한다. 만약 두 commit 모두에서 변경사항이 발생하여 충돌이 발생하면 충돌을 해결한 후 commit 해주면 된다.

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
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지.
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지

## Questions

조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
