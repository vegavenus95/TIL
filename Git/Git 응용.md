# Git 응용

## Git hook

> git에서 제공하는 프로세스(커밋, 푸시, 리베이스 등)의 전, 후 이벤트를 후킹하여 특정 액션을 실행하는 스크립트
> 즉, 특정 상황에 특정 스크립트를 실행할 수 있도록 하는 기능
> 설치가 필요한 것이 아니라 git repository에서 이미 지원
```
cd .git/hooks/
```
#### 여러가지 Git hooks

- applypatch-msg
- pre-applypatch
- post-applypatch
- pre-commit
- prepare-commit-msg
- commit-msg
- post-commit
- pre-rebase
- post-checkout
- post-merge
- pre-receive
- update
- post-receive
- post-update
- pre-auto-gc
- post-rewrite
- pre-push

### 클라이언트 훅  
##### 커밋, Merge가 발생하거나 push가 발생하기 전 클라이언트에서 실행하는 훅

1. 커밋 워크플로 훅  
###### ```git commit``` 명령으로 커밋할 때 실행하는 훅

pre-commit, prepare-commit-msg, commit-msg, post-commit  

- pre-commit : 커밋할 때 가장먼저 호출되는 훅으로, 커밋 메시지를 작성하기 전에 호출.
> 이 훅에서 커밋하는 스냅샷을 검사 하며, 빠트린 것이 없는지, 테스트 유무를 점검. 
> 커밋할 때 꼭 확인할 게 있으면 pre-commit훅을 사용하여 확인. 
> 이 훅은 exit가 0이 아니면 커밋이 취소되고, ```git commit --no-verify```를 해주면 해당 pre-commit훅을 일시적으로 생략할 수 있음.
> 추가적으로 lint같은 프로그램으로 코드 스타일을 검사하거나, 라인 끝 공백 문자를 검사하거나(.sample로 작성된 코드가 하는 행위입니다), 
> 새로 추가한 코드에 주석이 달려있는지 검사를 할 땐 pre-commit훅 이용

- prepare-commit-msg : 깃이 커밋 메시지를 생성하고 나서 편집기를 실행하기 전에 실행. 
> 이 훅은 사람이 커밋 메시지를 수정하기 전에 먼저 프로그램으로 손보고 싶을 때 사용.(커밋 메시지 자동으로 변경하고 싶을 때 사용)
> 커밋 메시지가 들어있는 파일 경로, 커밋의 종류 두 개의 인자를 받음.
> 최근 커밋을 수정할 때는(Amending 커밋) SHA-1 값을 추가적으로 더 받음.
> prepare-commit-msg은 Merge 커밋, Squash 커밋, Amend커밋일 때 유용함.

- commit-msg : 커밋 메시지가 들어 있는 임시 파일의 경로를 인자로 받음. 
> pre-commit과 마찬가지로 exit 0이 반환되지 않으면 커밋이 취소되며, 최종적으로 커밋이 완료되기 전에 프로젝트 상태나 커밋 메시지를 검증.
> 커밋 메시지가 해당 프로젝트 정책에 맞는지 검사 등을 수행.

- post-commit : 커밋 완료 시 실행 
> 이 훅은 넘겨받는 인자가 하나도 없지만 ```git log -l HEAD``` 명령으로 커밋 해시정보를 가져올 수 있음. 
> 보통 커밋된 것을 누군가 혹은 다른 프로그램에게 알릴 때 사용함.

2. 이메일 워크플로 훅  
###### ```git am``` 명령으로 이메일을 통해 patch 파일을 적용할 때 실행하는 훅

applypatch-msg, pre-applypatch, post-applypatch  

- applypatch-msg : ```git am```명령 실행 시 가장 먼저 실행 되는 훅. 
> exit 0을 하지 않으면 patch를 하지 않음. 
> 이 훅은 Author가 보내온 커밋 메시지 파일의 이름을 인자로 받음. 
> 커밋 메시지가 규칙에 맞는지 확인하거나 자동으로 메시지를 수정할 때 사용.

- pre-applypatch : ```git am```으로 patch할 때 두번째로 실행되는 훅. 
> 이 훅은 인자를 받지 않고, 단순하게 patch 적용 후 실행하며, patch를 중단 시킬 수 있음. (0이 아닌 값을 반환시켜서 git am명령을 취소 할 수 있음.)
> 커밋이 스냅샷을 점검할 때 사용. 

- post-applypatch: ```git am```명령에서 마지막으로 실행 되는 훅. 
> patch를 보낸 사람이나 그룹에게 알림 메시지를 보낼 수 있으며, patch를 중단 시킬 수 없음.
