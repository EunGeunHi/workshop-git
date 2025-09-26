**Git 기초**

Git을 사용하려면 알아야 할 기본 지식을 학습합시다. 아래 항목 위주로 조사하여 나름 이해한대로 채워주시기 바랍니다. 이 템플릿을 이용해도 되고, 자유 형식으로 정리하셔도 됩니다. 블로그 등에 정리한 경우 링크를 첨부해주세요.

**Git != Github**

![git-is-not-github](https://user-images.githubusercontent.com/51331195/160232512-3d6686ca-4ae3-4f11-a8d7-c893c0a7526a.png)

git과 github는 같은 의미가 아닙니다.

local, remote와 연관지어 적어주세요.

git은 local에서 소스 코드를 관리하는 형상 관리 툴입니다. 코드의 변경사항을 커밋의 형태로 저장하고 원하는 시점으로 돌아갈수 있도록 하는 명령어들의 집합이라고 생각합니다

github 는 로컬에서의 변경사항을 웹 사이트의 원격저장소에 저장할 수 있도록 지원해주는 웹사이트입니다

**Git Workflow**

[git-workflow](https://camo.githubusercontent.com/3205d73aa03bb84ccf95c26b1206102552731e30a4c277b2cebe47383bd8f4b5/68747470733a2f2f63646e2d6d656469612d312e66726565636f646563616d702e6f72672f696d616765732f312a694c324a386b347967516c67337872694b47696d62512e706e67)

위는 git이 어떻게 동작하는지 나타낸 다이어그램입니다.

![image.png](attachment:4ee101e9-38dd-4f94-bcd3-51b9a00a9f41:image.png)

Working Directory, Git Add, Git Commit, Git Push 등 각 항목에 대해 작성 바랍니다.

Git Merge, Git Fetch는 생략해도 됩니다.

- Working Directory : 현재 작업 디렉토리를 의미합니다
- Git Add : 변경된 파일을 git의 스테이징 영역에 올려둡니다. 커밋할 대상을 주로 추가합니다
- Git Commit : 스테이징 영역에 올려둔 파일들을 하나의 단위로 묶어서 로컬에 저장해 둡니다.
- Git Push : 로컬 브랜치의 커밋을 원격 저장소(깃허브)에 저장합니다(원격 저장소로 밀어낸다 라고 생각하기)
- Git Fetch : 원격에서의 브랜치와 같은 정보(어떤 정보인지 구체화하기)를 가져옵니다. 단 pull처럼 로컬 브랜치와 원격 브랜치를 연결해서 생성해주지는 않습니다
- Git Merge : main 브랜치에 작업한 feature 브랜치를 합칠 때 사용합니다
- Git Pull : 원격에서의 정보를 로컬로 가져오고 로컬 브랜치와 원격 브랜치를 연결해줍니다

**Branch, HEAD**

[branch-and-head](https://camo.githubusercontent.com/6ffceb8f5b2cd3c9972ed2cff239c4d8074c12767287af2b1429ae2423b8d9ae/68747470733a2f2f6968617465746f6d61746f65732e6e65742f77702d636f6e74656e742f75706c6f6164732f323032302f30342f30372d686561642d706f696e7465722e706e67)

git이 동작하는 기본 단위는 commit과 branch입니다.

branch와 HEAD, git checkout을 포함하여 작성 바랍니다.

- Commit: 현재 소스코드의 변경사항을 하나의 단위로 묶어 저장하고 로컬에 저장해 둡니다
- Branch: 브랜치는 개발하고 싶은 기능이 있을 때 곁가지의 형태로 기능을 독립적으로 개발할 수 있게 함
- HEAD: 현재 체크아웃된 브랜치의 가장 최근 커밋을 가리키는 포인터, 현재 작업 브랜치의 현재 위치
- git checkout [브랜치명]: 해당 브랜치명으로 로컬 브랜치를 이동함
- git switch -c [새로운 브랜치명]: 새로운 브랜치를 생성하고 바로 이동
- git branch [새로운 브랜치명]: 로컬에서 새로운 로컬 브랜치를 [새로운 브랜치명]으로 생성
- git branch -d [브랜치명]: 로컬에서의 브랜치명에 해당하는 브랜치를 삭제
- git push origin --delete [브랜치명]: 원격 저장소의 원격 브랜치를 삭제

**clone, init, origin**

리포지토리를 로컬에 생성하는 방법은 clone, init이 있습니다. 다음을 포함하여 작성 바랍니다.

- git clone과 git init의 차이점, 이용방법
- origin이란 키워드는 무엇인지, 어떻게 설정하는지
- git remote add origin [원격 저장소] 의 형태로 원격 저장소명을 간단하게 alias 로 지정한다고 생각해도 된다
- git init : 깃이 관리하는 폴더임을 알려줌과 동시에 이 디렉토리를 깃이 추적하도록 합니다(로컬 저장소로 등록한다)
- git clone : 원격 레포에서 로컬에 코드를 내려받을 때 사용합니다(코드뿐만이 아닌 커밋, 브랜치도 같이 가져옴)

**reset**

![reset](https://user-images.githubusercontent.com/51331195/160235594-8836570b-e8bf-484a-bb92-b2bd6d873066.png)

reset에는 3가지 타입이 있습니다.

각 타입에 대해 작성 바랍니다.

reset 이란? 
- 커밋을 취소하는 명령어, 스테이징 또한 취소 가능

- git reset --soft [커밋ID] : 커밋취소, Staging 상태를 유지(add), 커밋 메시지를 수정하고 싶다
- git reset --mixed [커밋ID] : 커밋 취소, Staging 취소, local은 변경 상태로 유지,커밋할 대상 파일을 잘못 그룹화해서 커밋했을 때
- git reset --hard [커밋ID]: 커밋 취소, staging 취소, local의 변경 상태도 취소
, 이제까지의 변경사항이 회의후 적용을 하지 않기로 했다.ㅠㅠ reset —hard

→ 셋다 커밋을 취소하지만, 각각의 상황에 따라 어떤 reset을 사용할지 고민

**Pull Request, Merge**

[pull-request-merge](https://camo.githubusercontent.com/cce381570e6cf4a6559dfe0b4b1e42dd7bf44edcba15dc4a4928d6aa36be215d/68747470733a2f2f61746c61737369616e626c6f672e7770656e67696e652e636f6d2f77702d636f6e74656e742f75706c6f6164732f6269746275636b65743431312d626c6f672d31323030782d6272616e63686573322e706e67)

Pull Request와 Merge에 대한 내용을 적어주세요.

특히 Merge의 두 타입인 Fast-Forward와 3-Way Merge를 포함해주세요.

- Pull Request : 브랜치에서 기능 개발 후 메인 브랜치에 합치기 위해서 이 코드를 리뷰하고 확인하는 과정을 요청하는 것을 의미합니다
- Merge : 브랜치 단위로 개발한 기능을 메인 브랜치에 합칠 때 사용합니다
1. Fast-Forward Merge : 메인 브랜치와 분기된 작업 브랜치를 비교했을 때, 작업 브랜치가 메인 브랜치의 커밋을 포함하고 추가 분기가 없으면 Fast-Forward 상태이며, 이 상태에서는 작업 브랜치의 커밋을 따라 메인 브랜치 포인터를 단순히 앞으로 이동시키는 방식으로 Merge가 가능하다. HEAD 만 작업 브랜치로 옮기기 때문에 별도의 merge commit은 생성되지 않는다
2. 3-Way Merge : 병합하려는 메인 브랜치에서도 커밋이 존재하고, 작업 브랜치에도 메인 브랜치에 존재하지 않는 커밋이 존재할 때 공통 조상(base) 뒤에 들어온 커밋들을 합쳐서 하나의 커밋 단위로 만들어서 커밋 히스토리를 선형적으로 유지
- git merge 시 base를 기준으로 3-way를 비교 후 새로운 merge commit 생성
- 3-way Merge 텍스트 다이어 그램
    
    ```java
    초기 상태:
    main: A --- B --- E
    feature: A --- B --- C --- D
    
    Merge 후 (3-Way):
    main: A --- B --- E --- M
                     \ 
    feature:          C --- D
    
    M = Merge Commit (C+D+E를 합친 새로운 커밋)
    
    ```
    

**rebase**

![rebase](https://user-images.githubusercontent.com/51331195/160234052-7fe70f85-5906-4474-b809-782adae92b3c.png)

rebase란 무엇인지, 어떤 때에 유용한지 등에 대해 적어주세요.

- rebase : rebase 란 현재 같은 부모 브랜치에서 갈라진 형태의 커밋이 생겼을 때 이 갈라진 커밋 히스토리를 선형적인 형태로 정리하는 명령어
- merge와 다르게 새로운 merge 커밋을 만들지 않고 한줄로 이어 붙임

<활용방법>

1. 공유 브랜치의 변경사항을 즉각 반영하는 것이 가능하다 - 동료 개발자의 커밋을 내가 작업하는 브랜치에 즉각 반영이 가능하다
2. 커밋 히스토리를 깔끔하게 유지할 수 있다 feature가 많아졌을 때도 git flow를 단순하게 확인이 가능하다

**stash**

[stash](https://camo.githubusercontent.com/8b8ecb57802391d6e07f11a5611d1ec93b653b8c7f4b226241dfeba32486cb8a/68747470733a2f2f6438697434687578756d7073372e636c6f756466726f6e742e6e65742f62697465732f77702d636f6e74656e742f62616e6e6572732f323032332f342f363432613636336561666639365f6769745f73746173682e706e67)

git stash를 활용하는 방법에 대해 적어주세요.

- git stash :  현재 로컬 브랜치에서의 변경사항을 stash라는 스택에 넣어뒀다가 브랜치를 체크아웃 후 pop 을 통해서 변경사항을 커밋하지 않고 옮길 수 있습니다

<활용방법>

1. 핫픽스 발생시 현재 변경사항은 stash에 저장해 뒀다가 수정 후 다시 돌아올 떄
2. 아직 완료하지 않은 작업을 커밋하기 전에 잠시 보관할 때 
3. 저장된 stash의 목록들을 확인하기 (git stash list)
4. stash에서 꺼내면서 삭제하기 pop, 꺼내는데 stash에서 삭제하지는 않기 apply
5. 특정 stash를 삭제하기 git stash drop [stash 항목]

**Advanced**

다음 주제는 더 조사해볼만한, 생각해볼만한 것들입니다.

- 브랜치관리전략에 대표적으로 Github Flow, Git Flow가 있습니다. 두 방식에서는 리포지토리를 어떻게 관리할까요?
- `git rebase --interactive`란?
- branch의 upstream이란? (`git push --set-upstream`)
- PR은 브랜치 뿐만 아니라 Fork한 리포지토리에서도 가능하다. fork은 언제 유용한지.
- `git fetch`와 `git pull`의 차이점, fetch는 언제 쓰는지
- `reset --hard`와 `push --force`의 적절한 사용법
- `.gitignore` 사용법
- 브랜치 이름은 슬래시를 통해 계층적으로 가질 수 있다. 단, `parent/child-1`, `parent/child-2`는 동시에 가질 수 있지만 `parent/child/grandchild`, `parent/child`는 그러지 못한다. 무슨 이유 때문인지.
- detached HEAD란 어떤 상태인지, 이 상태에서 커밋을 하게 되면 어떻게 되는지, detached HEAD는 어떤 상황에서 발생할 수 있는지
