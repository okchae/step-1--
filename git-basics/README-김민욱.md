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

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

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
