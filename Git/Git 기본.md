# Git 

₩₩₩
https://learngitbranching.js.org/
₩₩₩

### git 명령어

- commit
- branch
- checkout
- cherry-pick
- reset
- revert
- rebase
- merge


### 1. Git 기본

> git 주요 명령어

#### 1-1 Git 커밋 소개

```bash
$ git commit -m "내용"
```

#### 1-2 Git에서 브랜치 쓰기 및 이동

브랜치: 하나의 커밋과 그 부모 커밋들을 포함하는 작업 내역

브랜치명 bugFix

```bash
$ git branch [브랜치명]
$ git checkout [브랜치명]
```
#### 1-3 Git에서 브랜치 합치기(Merge)

```bash
$ git branch bugFix
$ git checkout bugFix
$ git commit -m "branch"
$ git checkout master
$ git commit -m "master"
$ git merge bugFix
```

#### 1-4 리베이스(rebase)의 기본

- 브랜치끼리 작업을 접목하는 두번째 방법
- 리베이스는 기본적으로 커밋들을 모아서 복사한 뒤, 다른 곳에 떨궈 놓음
- 리베이스를 하면 커밋들의 흐름을 보기 좋게 한 줄로 만들 수 있다는 장점 -> 저장소의 커밋 로그와 이력이 한결 깨끗해짐
- 내가 bugFix에 있는데 master 최신으로 가게 하려면 `$git rebase master`

```bash
$ git branch bugFix
$ git checkout bugFix
$ git commit -m "bugFix"
$ git checkout master
$ git commit -m "master
$ git checkout bugFix
$ git rebase master
```

