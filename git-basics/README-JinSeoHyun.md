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
- 브랜치 이름은 `parent/child-1`, `parent/child-2`는 가질 수 있지만 `parent`, `parent/child`는 가질 수 없다. 무슨 이유 때문인지. 
- 리포지토리의 두 타입인 bare, non-bare

## Questions
조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.