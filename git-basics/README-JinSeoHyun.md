# Git 기초
Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.
노션링크를 첨부할게요! 

## Git != Github
![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  

Git : 개인 컴퓨터에서 돌아가는  분산 버전 관리 시스템이다.

**버전 관리 시스템**

- 파일 변화를 시간에 따라 기록했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템이다

**분산 버전 관리 시스템** 

- 저장소 자체를 히스토리와 더불어 전부 복제한다.

Local 저장소 : 개발자는 로컬 저장소에서 작업한다. 로컬저장소는 개발자 개인의 작업 공간이다.
(Local저장소에서 Remote저장소로 : push)

Remote 저장소 : 원격저장소는 인터넷 상의 서버에 위치한 Git 저장소이다. 여러 개발자가 협업을 위해서 사용하고, 코드의 변경사항을 받아올 수 있다. 
(Remote저장소에서 local 저장소로: pull)

github : 원격 저장소를 호스팅하고 관리하는 플랫폼이다. 



## Git Workflow
![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Director : 작업 디렉토리는 현재 작업 중인 프로젝트의 실제 파일들이 위치하는 디렉토리입니다. 여기서 코드를 수정하거나 파일을 추가하거나 삭제할 수 있습니다.

Git Add : 변경된 파일을 Staging Area에 올리는 명령어이다. 

Staging Area : 커밋(Commit)을 수행할 파일들이 올라가는 영역

Git Commit : git commit 명령은 스테이지 영역에 있는 변경 사항들을 로컬 저장소에 커밋하는 역할을 합니다. 

Git Push : git push 명령은 로컬 저장소에 커밋된 변경 사항들을 원격 저장소로 업로드하는 역할을 합니다

## Branch, HEAD
![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  

Commit (커밋):
커밋은 Git에서 변경 사항의 스냅샷을 의미합니다.
코드 변경 내용을 스테이징한 후 git commit 명령으로 로컬 저장소에 저장합니다.
각 커밋은 고유한 해시값을 가지며, 변경 내용과 메시지를 포함합니다.

Branch (브랜치):
브랜치는 독립적인 작업 흐름을 나타내는 것으로, 기존 코드를 기반으로 새로운 작업을 진행할 때 사용합니다.
git branch 명령으로 브랜치를 생성하고, git branch -d 명령으로 브랜치를 삭제할 수 있습니다.

HEAD:
HEAD는 현재 작업 중인 커밋을 가리키는 포인터입니다.
일반적으로 HEAD는 현재 체크아웃된 브랜치의 가장 최신 커밋을 가리킵니다.

**명령어 설명**
git branch <new-branch-name> : 새로운 브랜치를 생성

git branch -d <branch-name> : 브랜치를 삭제

git checkout <branch-name> : 다른 브랜치로 이동

git checkout -b <new-branch-name> : 새 브랜치를 생성하고 이동

git merge <source-branch> : 다른 브랜치의 변경 사항을 현재 브랜치로 병합할 수 있습니다.

## clone, init, origin
리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.
- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

git init:
git init 명령은 현재 디렉토리를 Git 저장소로 초기화합니다. 이 명령을 사용하면 새로운 Git 저장소가 생성되며, 이후에 파일을 추가하고 커밋할 수 있습니다.

git clone:
git clone 명령은 원격 저장소의 내용을 로컬로 복제합니다. 기존에 원격 저장소에 있는 코드를 로컬 환경으로 가져올 때 사용합니다. git clone 명령을 사용하면 원격 저장소의 모든 커밋 이력과 파일들을 로컬로 가져옵니다.

origin:
origin은 기본적으로 Git 원격 저장소를 가리키는 이름입니다. 일반적으로 git clone 명령을 사용하여 원격 저장소를 로컬로 복제할 때, **원격 저장소의 이름으로 origin이 자동으로 설정됩니다.** 이후에 origin이라는 이름으로 원격 저장소에 푸시(push)하거나 풀(pull)하는 등의 작업을 수행할 수 있습니다
origin 설정:
origin을 직접 설정하려면 git remote add 명령을 사용합니다. 이 명령을 통해 원격 저장소의 URL과 이름을 연결합니다.

## reset
![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

Soft Reset:`git reset --soft <commit> `
커밋을 특정 지점으로 이동시키며, 작업 트리와 스테이징 영역은 변하지 않습니다.
이전 커밋 이후의 변경 사항을 다시 스테이징 영역에 추가하고, 새로운 커밋을 생성하거나 이전 커밋을 수정할 수 있습니다.
사용 예시: git reset --soft HEAD~1 (마지막 커밋 취소 후 변경 사항을 스테이징 영역에 유지)

Mixed Reset (Default) `git reset <commit>` --mixed 옵션이나 아무 옵션 없이 git reset만 사용해도 됩니다.
커밋을 특정 지점으로 이동시키며, 스테이징 영역은 비워집니다. 하지만 작업 트리는 변경 사항을 유지합니다.
변경 사항을 스테이징 영역에 다시 추가하여 커밋을 수정하거나, 새로운 커밋을 생성할 수 있습니다.
사용 예시: git reset HEAD~1 (마지막 커밋 취소 후 변경 사항을 작업 트리에 유지)

Hard Reset:`git reset --hard <commit>` 
커밋을 특정 지점으로 이동시키며, 작업 트리와 스테이징 영역을 완전히 해당 커밋 상태로 변경합니다.
변경 사항을 모두 제거하고 이전 커밋 상태로 되돌립니다. 주의해서 사용해야 합니다.
사용 예시: git reset --hard HEAD~1 (마지막 커밋과 변경 사항 모두 제거)

## Pull Request, Merge
![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

Pull Request 

Pull Request는 코드 변경 사항을 원격 저장소에서 다른 브랜치로 병합하도록 요청하는 기능입니다. 주로 협업 프로젝트에서 사용됩니다.
개발자는 자신이 작업한 브랜치를 원격 저장소로 푸시하고, 그 브랜치를 기반으로 Pull Request를 생성합니다.
Pull Request는 다른 개발자들에게 코드 변경 사항을 검토하고 논의하는 기회를 제공하며, 이후에 코드 변경이 승인되면 브랜치가 병합(merge)됩니다.

Merge

Merge는 다른 브랜치의 변경 사항을 현재 브랜치에 통합하는 과정입니다.
주로 Pull Request가 승인되었을 때나, 혹은 작업이 완료되어 브랜치를 메인 브랜치에 병합할 때 사용됩니다.

  Fast-Forward Merge

  Fast-Forward Merge는 브랜치가 단순히 직선적으로 업데이트된 경우에 발생합니다.
  현재 브랜치가 병합 대상 브랜치의 모든 커밋을 포함하고 있는 상태에서 Fast-Forward Merge가 수행됩니다.
  따라서 추가적인 병합 커밋 없이 단순히 브랜치의 포인터가 업데이트됩니다.

  3-Way Merge

  3-Way Merge는 브랜치들이 독립적으로 변경된 경우에 사용됩니다.
  현재 브랜치와 병합 대상 브랜치, 그리고 공통 조상 커밋 세 개를 기반으로 병합 커밋을 생성합니다.
  변경 사항이 겹치거나 충돌할 수 있는 경우에도 자동으로 해결하려고 시도하며, 충돌이 발생하는 경우에는 수동으로 충돌을 해결해야 합니다.


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