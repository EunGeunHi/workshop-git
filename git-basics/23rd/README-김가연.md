# Git 기초

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

## Git != Github

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)  
git과 github는 같은 의미가 아닙니다.  
local, remote와 연관지어 적어주세요.

Git은 버전관리 소프트웨어이며, Git을 통해 로컬 저장소의 모든 변경사항을 기록하여 파일의 버전관리가 용이해진다. 그렇다면 Github는 Git을 사용하는 프로젝트를 지원하는 원격 저장소 기반의 웹 호스팅 서비스이다. Git에서는 로컬 저장소에서 작동하기에 공유 및 협업에 있어서 어려움이 있는데, 이를 Github가 해결해준다. 웹 상에서 클라우드 서버를 통해 로컬 저장소의 코드를 업로드하고 공유할 수 있다.

## Git Workflow

![git-workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)  
위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.  
Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.  
Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory : 사용자의 작업 공간으로써, 로컬 저장소(git)에 접근할 수 있으며, 실제 파일을 수정하거나 생성하는 공간
- Git Add : commit의 전단계로, 커밋을 하기 위해서는 해줘야하는 단계이다.
- Git Commit : 변화한 부분을 git에 저장하는 것을 의미한다.
- Git Push : 커밋을 해서 작업 내용들이 내 컴퓨터에 저장이 됐으니, 그 파일들을 원격 저장소인 github에 업로드하는 단계를 의미한다.

## Branch, HEAD

![branch-and-head](https://ihatetomatoes.net/wp-content/uploads/2020/04/07-head-pointer.png)  
git이 동작하는 기본 단위는 commit과 branch입니다.  
branch와 HEAD, git checkout을 포함하여 작성 바랍니다.  
branch 생성 및 삭제, 이동 커맨드 등 자유롭게 내용을 추가해주세요.

- Commit: 브랜치 간의 변경 사항을 전달하는 주요 수단.
- Branch: 프로젝트의 다른 버전을 병렬적으로 개발할 수 있게 해주는 기능. 각 브랜치는 독립적인 개발 흐름을 나타낸다.
- HEAD: 해당 브랜치의 마지막 커밋.
- git checkout [브랜치명]: 지정한 브랜치로 이동하고 작업 환경을 전환하는 명령어.
- git switch -c [새로운 브랜치명]:
- git branch [새로운 브랜치명]: 새로운 브랜치를 만들고, 그 브랜치로 즉시 전환하는 명령어.
- git branch -d [브랜치명]: 해당 브랜치를 삭제하는 명령어.
- git push origin --delete [브랜치명]: 원격 저장소에서 해당 브랜치를 삭제하는 명령어. 단 로컬 브랜치에서는 그대로 유지된다.

## clone, init, origin

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지

- git init : 새로운 로컬 Git 저장소를 처음부터 생성하여 프로젝트의 버전 관리를 시작하게 하는 명령어. 이용방법으로는 폴더를 생성하고 해당 폴더로 이동한 뒤 git init 을 터미널에서 입력하면 된다.
- git clone : 기존의 원격 Git 저장소를 복제하여 내 로컬 컴퓨터에 가져오는 명령어. 이용방법으로는 git clone [저장소 주소]
- orgin이란 Git에서 원격 저장소의 기본 이름을 뜻한다. 설정방법으로는 git remote add origin [원격 저장소 주소] 로 하면 된다.

## reset

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)  
reset에는 3가지 타입이 있습니다.  
각 타입에 대해 작성 바랍니다.

- git reset --soft [커밋ID] : 현재 브랜치의 HEAD를 지정된 커밋ID로 되돌리면서, 해당 커밋 이후에 변경된 내용들은 add 상태에 그대로 유지한다. 즉, 새 커밋으로 다시 만들거나 수정할 수 있는 상태가 된다.
- git reset --mixed [커밋ID] : 지정한 커밋ID로 브랜치를 이동시킨 후, 해당 커밋 이후의 변경사항들을 working directory에 남겨두고, 스테이징 영역만 초기화한다.
- git reset --hard [커밋ID] : 현재 브랜치의 HEAD, 인덱스, working directory를 지정한 커밋ID 시점의 상태로 완전히 되돌리는 데에 사용된다. 해당 커밋 이후의 모든 변경사항과 커밋 이력을 삭제하게 된다.

## Pull Request, Merge

![pull-request-merge](https://atlassianblog.wpengine.com/wp-content/uploads/bitbucket411-blog-1200x-branches2.png)  
Pull Request와 Merge에 대한 내용을 적어주세요.  
특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- Pull Request : 새로운 코드 변경사항을 원본 소스 코드에 병합하기 위해 제안하는 것을 의미한다. 깃허브의 내 브랜치에서 PR 버튼을 눌러서 적절하게 내용을 쓴 다음, 병합 요청을 하는 것이다.
- Merge : 브랜치와 브랜치를 합치는 과정을 말한다.

1. Fast-Forward Merge : 현재 브랜치의 HEAD가 대상 브랜치의 HEAD까지로 옮기는 merge이다. git switch [현재 브랜치] git merge [대상 브랜치] 명령어를 통해 실행이 가능하다.
2. 3-Way Merge : 두 브랜치의 최신 변경사항과 이들이 갈라진 공통 조상 커밋을 비교하여 자동으로 병합하는 방식의 merge이다.

## rebase

![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)  
rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- rebase란 git에서 한 브랜치의 커밋들을 다른 브랜치의 가장 최신 커밋 뒤로 재배치하는 것을 말한다. 개발자들과 협업할 때 복잡해진 히스토리를 깔끔하게 유지하려고 할 때, 병합 커밋 없이 최신 변경사항을 반영하려고 할 때, 원격 저장소의 최신 커밋을 내 작업 브랜치에 빠르게 반영하려고 할 때 유용하다.

## stash

![stash](https://d8it4huxumps7.cloudfront.net/bites/wp-content/banners/2023/4/642a663eaff96_git_stash.png)  
git stash를 활용하는 방법에 대해 적어주세요.

- git stash : 파일의 변경 내용을 일시적으로 기록해두는 영역

<활용방법>

1. 급하게 다른 브랜치로 이동해야 할 때 현재 작업중인 것의 변경사항을 임시 저장해둔다.
2. 작업 내용을 잠시 보류하고 깨끗한 상태로 돌아가야할 때
3. 여러 작업을 동시에 진행할 때 유용하다.
4. stash를 통해 변경 사항을 다른 곳에 담을 수 있다.
5. 다른 브랜치에 저장해둔 stash로 저장해둔 코드들을 적용할 수 있다.
6. 원하는 것만 stash가 가능하다.

## Advanced

다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다.

- 브랜치관리전략에 대표적으로 Github Flow, Git Flow가 있습니다. 두 방식에서는 리포지토리를 어떻게 관리할까요?
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지.
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지.
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지

## Questions

조사/실습하면서 생긴 궁금점이 있다면 여기에 적어서 공유해주세요.
