# TIL Day 01

> 2022년 09월 22일 목요일

## 0) Why Git & Github?
---
![Git로고](https://user-images.githubusercontent.com/49775540/168756716-68f9aebb-380f-4897-8141-78d8403f6113.png)

### Git

+ 분산 버전 관리 프로그램
+ 백업, 복구, 협업을 위해 사용
+ [Git 공식문서](https://git-scm.com/book/ko/v2)

### Github

- Git을 사용하는 프로젝트의 협업을 위한 웹호스팅 서비스
- 포트폴리오를 자랑할 수 있는 공간
- 1일 1커밋 하기
- [이동욱님 Github 계정](https://github.com/jojoldu)



## 1) CLI
---
> CLI (Command Line Interface, 커맨드 라인 인터페이스)는 터미널을 통해 사용자와 컴퓨터가 상호 작용하는 방식을 뜻한다.

### 터미널 명령어 정리

| 명령어 |  설명  |
| :----:  | :-----:   |
| mkdir | 폴더 생성 |
| touch | 파일 생성 |
| ls | 현재 폴더의 파일 목록 출력|
| cd | 다른 폴더로 이동 |
| rm | 파일 삭제/폴더 삭제(-r 옵션)|

### 예시
```bash
$ mkdir test

$ touch a.txt

$ ls
$ ls -a

$ cd ..
$ cd test

$ rm a.txt
$ rm -r test
```


## 2) Visual Studio Code
---
> Visual Studio Code (비주얼 스튜디오 코드)는 마이크로소프트에서 개발한 텍스트 에디터의 한 종류이다.

### 장점

- Windows, Mac, Linux 운영체제를 모두 지원한다.
- 기존 개발 도구보다 빠르고 가볍다.
- Extension을 통해 다양한 기능을 설치할 수 있어서, 무한한 확장성을 가진다.
- 무료로 사용 가능하다.

### Git Bash 연동하기

1. 터미널을 연다. (Ctrl + `)
2. 화살표를 누르고 *Select Default Profile*을 클릭한다.
3. Git Bash를 선택한다.
4. 휴지통을 눌러서 터미널을 종료하고, 재시작한다.
   + 휴지통은 Kill Terminal로, 터미널 자체를 아예 종료한다.
   + 닫기는 Close Terminal로, 터미널을 종료하지 않고 창만 보이지 않게 만든다.
5. 기본 터미널이 Git Bash로 열리는지 확인한다.



## 3) Markdown
---
> **Markdown(마크다운)** 은 일반 텍스트 기반의 경량 **Markup(마크업)** 언어이다.

### Markup(마크업)이란?

+ 마크(Mark)로 둘러싸인 언어를 뜻한다. 마크란 글의 역할을 지정하는 표시이다.
+ HTML도 마크업 언어인데, 글에 제목의 역할을 부여할 때 `<h1>제목1</h1>` 과 같이 작성한다.

### 마크다운의 장점과 단점

1. 장점
   + 문법이 직관적이고 쉽다.
   + 지원 가능한 플랫폼과 프로그램이 다양하다.
2. 단점
   + 표준이 없어서 사용자마다 문법이 상이하다.
   + 모든 HTML의 기능을 대신하지는 못한다.

### 주의 사항

+ 마크다운의 본질은 글에 **역할**을 부여하는 것이다.
+ 반드시 역할에 맞는 마크다운 문법을 작성한다. 글씨를 키우고 싶다고 해서 본문에 제목의 역할을 부여하면 안된다.

### 참고 자료

+ [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
+ [마크다운 문법 정리](https://gist.github.com/ihoneymon/652be052a0727ad59601)

## 4) Git 기초
---
### [1] Git의 초기 설정   
> 최초 한 번만 설정하는 것으로, 매번 할 필요가 없다.
1. 이름과 이메일을 설정한다. 작성자를 수정하고자 할 경우 이름과 메일 주소만 다르게 하여 동일한 방법으로 입력한다.

```bash
$git config --global user.name "이름"
$git config --global user.email "메일 주소"
```

2. 작성자가 잘 설정됐는지 확인하는 법
```bash
$git config --global -l
또는
$git config --global -list
```

### [2] Git의 기본 명령어   
### (0) 로컬 저장소   
![개요도](https://hphk-edu.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F7142d992-3d01-481c-9d4e-e818c6e185d8%2FUntitled.png?table=block&id=562d8e79-6490-433e-ac91-9c4f3e1f29ce&spaceId=f7ab64f0-6613-4035-b609-06b6865d9b61&width=1600&userId=&cache=v2)
- Working Directory(= Working Tree) : 사용자의 일반적인 작업이 일어나는 곳
- Staging Area(= Index) : 커밋을 위한 파일 및 변경사항(커밋)을 저장하는 곳
- Repository : Staging Area에 있던 파일 및 폴더의 변경사항(커밋)을 저장하는 곳
- Git은 Working Directory -> Staging Area -> Repository의 과정으로 버전 관리를 수행한다.

### (1) git init
```bash
$ git init
Initialized empty git repository in C:/Users/kyle/git-practice/.git/

kyle@KYLE MINGW64 ~/git-practice (master)
```
- 현재 작업 중인 디렉토리를 git으로 관리한다는 명령어
- `.git`이라는 숨김 폴더를 생성하고, 터미널에는 `(master)`라고 표기됨.
- Mac의 경우 `(master)`가 표기되지 않는데, 터미널 업그레이드를 통해 표기가능.

>주의 사항
>1. 이미 git 저장소인 폴더 내에 또 다른 git 저장소를 만들지 않을 것. (중첩 금지) 즉, 터미널에 이미 (master)가 있다면, git init을 절대 입력하면 안됨.   
>2. 절대로 홈 디렉토리에서 git init을  하지 않는다. 터미널의 경로가 `~`인지 확인할 것.

### (2) git status
```bash
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
- Working Directory와 Staging Area에 있는 파일의 현재 상태를 알려주는 명령어
- 어떤 작업을 시행하기 전에 수시로 status를 확인하면 좋다.
- 상태
   1. `untracked` : git이 관리하지 않는 파일(한번도 Staging Area에 올라간 적 없는 파일)
   2. `tracked` : git이 관리하는 파일.
      - `unmodified` : 최신 상태
      - `modified` : 수정되었으나 아직 Staging Area에는 반영하지 않은 상태
      - `staged` : Staging Area에 올라간 상태

![파일의 라이프사이클](https://hphk-edu.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F67719520-a1d8-4cbb-81dd-49dea429a7f4%2FUntitled.png?table=block&id=d6d96301-5629-4d6f-95c8-ce5acb37cd43&spaceId=f7ab64f0-6613-4035-b609-06b6865d9b61&width=1600&userId=&cache=v2)

### (3)git add
``` bash
# 특정 파일
$ git add a.txt

# 특정 폴더
$ git add my_folder/

# 현재 디렉토리에 속한 파일/폴더 전부
$ git add .
```
- Working Directory에 있는 파일을 Staging Area로 올리는 명령어
- git이 해당 파일을 추적(관리)할 수 있도록 만듦.
- `untracked, modified → Staged`로 상태를 변경
- e.g.
  ```bash
  $ touch a.txt b.txt

$ git status
On branch master

No commits yet

Untracked files: # 트래킹 되고 있지 않는 파일 목록
  (use "git add <file>..." to include in what will be committed)
        a.txt
        b.txt

nothing added to commit but untracked files present (use "git add" to track)
  ```
```bash
# a.txt만 Staging Area에 올립니다.

$ git add a.txt
```
```bash
$ git status

On branch master

No commits yet

Changes to be committed: # 커밋 예정인 변경사항(Staging Area)
  (use "git rm --cached <file>..." to unstage)
        new file:   a.txt

Untracked files: # 트래킹 되고 있지 않은 파일
  (use "git add <file>..." to include in what will be committed)
        b.txt
 ```



### (4) git commit
```bash
$ git commit -m "first commit"
[master (root-commit) c02659f] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 a.txt
 ```
 - Staging Area에 올라온 파일의 변경 사항을 하나의 버전(commit)으로 저장하는 명령어
 - `커밋 메세지`는 현재 변경 사항들을 나타낼 수 있도록 `의미`있게 작성하는 것을 권장.
 - 각각의 커밋은 `SHA-1` 알고리즘에 의해 반환된 고유의 hash 값을 ID로 가진다.
 - `(root-commit)`은 해당 커밋이 최초의 커밋일 때만 표시. 이후 커밋부터는 사라진다.
  
### (5) git log
```bash
$ git log
commit 1870222981b4731d14ef91d401c68c0bbb2f6e7d (HEAD -> master)
Author: kyle <kyle123@hphk.kr>
Date:   Thu Dec 9 15:26:46 2021 +0900

    first commit
```
- 커밋의 내역(`ID, 작성자, 시간, 메세지 등`)을 조회할 수 있는 명령어
- 옵션
  - `--oneline` :  한 줄로 축약해서 출력
  - `--graph` : 브랜치와 머지 내역을 그래프로 출력
  - `--all` : 현재 브랜치를 포함한 모든 브랜치의 내역을 출력
  - `--reverse` : 커밋 내역의 순서를 반대로 출력(최신이 가장 아래)
  - `-p` : 파일의 변경 내용도 같이 출력
  - `-2` : 원하는 갯수만큼의 내역을 출력(2 말고 임의의 숫자 사용 가능)

>옵션과 인자

>>명령어를 사용하면서 `-` 혹은 `--`를 통해 옵션을 사용하는 것을 배웠습니다. 
옵션과 더불어서 인자라는 개념도 존재하는데요. 옵션과 인자 무엇이 다를까요?

>>**옵션**은 명령어의 동작 방식을 지정하는 것입니다. 따라서 **생략 가능**합니다. 
단순히 기존 기능보다 부가적인 기능을 원할 때 사용합니다. 예를 들면 `git log --oneline`은 커밋 내역을 한 줄로 보고 싶을 때 사용합니다. `oneline` 옵션은 말 그대로 부가적인 기능이므로, 생략해도 `git log`는 정상 동작합니다.

>>인자는 명령어의 동작 대상을 지정하는 것입니다. 따라서 **생략이 불가능** 합니다.
예를 들면 `git add`라고만 작성하면 어떤 파일을 Staging Area에 올릴지 모르게 됩니다.
반드시 `git add a.txt`와 같이 `git add` 명령어가 동작할 대상을 지정해야 하는데
이때 `a.txt`와 같은 대상을 인자라고 합니다. 

### (6) 한눈에 보는 git 명령어
![명령어의 도해](https://hphk-edu.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2Fc86c667a-616f-45b6-892e-15da6a3c494e%2FUntitled.png?table=block&id=8ff341ce-190a-483a-9ca1-6c20ac872101&spaceId=f7ab64f0-6613-4035-b609-06b6865d9b61&width=2000&userId=&cache=v2)

## 5) Github
---
### [1] 원격 저장소 (Remote Repository)
> 여태까지는 내 컴퓨터라는 한정된 공간에 있는 로컬 저장소에서만 버전 관리를 진행. Github의 원격 저장소를 이용하면 내 컴퓨터의 로컬 저장소를 다른 사람과 `공유`할 수 있다. Git의 주요 목적 중 하나인 `협업`을 위해 로컬과 원격을 연동해보자.

### (1) github에서 원격 저장소 생성

![원격1](https://hphk-edu.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F55e28914-796f-487f-9ce1-972cf15cc1d1%2F%EA%B7%B8%EB%A6%BC3.png?table=block&id=9ae6ef88-cec1-46d7-9160-006ca8e5d4dd&spaceId=f7ab64f0-6613-4035-b609-06b6865d9b61&width=2000&userId=&cache=v2)
![원격2](https://hphk-edu.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F40d4c341-35df-4cf7-8586-83afe060d56c%2F%EA%B7%B8%EB%A6%BC4.png?table=block&id=f02b266c-18ca-45fc-90fa-1074a9c1c051&spaceId=f7ab64f0-6613-4035-b609-06b6865d9b61&width=1340&userId=&cache=v2)
- 우측 상단 + → New Repository → 저장소의 이름, 설명, 공개 여부를 선택 → Create Repository를 클릭

### (2) 로컬 저장소와 원격 저장소 연결 
1. 원격 저장소의 생성 여부를 확인 후, 저장소의 주소를 복사
2. git init을 통해 공유하고자 하는 폴더를 로컬 저장소로 만든다.
3. `git remote` : 등록, 조회, 삭제
   - `git remote add <이름> <주소>` : 등록
   - `git remote -v` : 조회, 이름과 주소를 보여준다.
   - `git remote rm <이름>`, `git remote remove <이름>` : 목표 저장소와의 연결을 삭제한다.
  
### (3) 원격 저장소에 업로드
- 파일을 업로드 하는 것이 아니라, 커밋을 업로드 하는 것임을 명심하자.
- 먼저 로컬 저장소에서 커밋을 생성해야 원격 저장소에 업로드 가능
  
1. 로컬 저장소에서 커밋 생성
2. `git push`
   - 로컬 저장소의 커밋을 원격 저장소에 업로드 하는 명령어
   - `git push <저장소 이름> <브랜치 이름>` 형식으로 저장
   - `-u` 옵션을 사용하면, 두 번째 커밋부터는 `저장소 이름, 브랜치 이름`을 생략 가능
```bash
$ git push origin master

[풀이]
git 명령어를 사용할건데, origin이라는 이름의 원격 저장소의 master 브랜치에 push 한다.

------------------------------------------------

$ git push -u origin master
이후에는 $ git push 라고만 작성해도 push가 된다.
```
3. vscode 자격 증명 → 이후 git push 완료
```bash
$ git push -u origin master
info: please complete authentication in your browser...
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 218 bytes | 218.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/edukyle/TIL.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

4. 원격 저장소에서 정상 업로드 여부 확인

>(주의) Github 원격 저장소에 절대로 파일을 드래그해서 업로드 하지 않습니다!!!!

>>가끔 Github를 구글 드라이브처럼 여겨서, 파일을 직접 드래그해서 올리는 경우가 있습니다. Git 명령어를 학습했기 때문에, 반드시 git add → git commit → git push의 단계로만 업로드 해야합니다.

>> 그 이유는 로컬 저장소와 원격 저장소의 동기화 때문입니다. 로컬 저장소에서 변경이 먼저 일어나고, 그 변경 사항을 원격 저장소에 반영하는 형태여야 합니다. 하지만, Github에 드래그를 해서 파일을 업로드하면 원격 저장소에 변경이 먼저 일어나는 형태가 되기 때문에 이러한 행동을 지양해야 합니다.

1. `git push`를 그림으로 이해하기
![도해](https://hphk-edu.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F357df618-2ddf-4f18-b96c-c1b0787a1a45%2FUntitled.png?table=block&id=64b87056-ad32-4c3c-b8fc-172ba1f53fde&spaceId=f7ab64f0-6613-4035-b609-06b6865d9b61&width=2000&userId=&cache=v2)