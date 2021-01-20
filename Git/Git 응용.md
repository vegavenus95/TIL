# Git 응용

### 1. Git hook

> git에서 제공하는 프로세스(커밋, 푸시, 리베이스 등)의 전, 후 이벤트를 후킹하여 특정 액션을 실행하는 스크립트
> 즉, 특정 상황에 특정 스크립트를 실행할 수 있도록 하는 기능
> 설치가 필요한 것이 아니라 git repository에서 이미 지원
```
cd .git/hooks/
```
#### 1-1 여러가지 Git hooks

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
