
---
title: Git 시작하기
date: 2021.1.28.
tags: [git,github]
categories: [git, github]
---

<!-- excerpt -->
1. Git을 시작하기 전 해야 할 작업
2. Git init
3. Git clone


# 1. git을 시작하기 전 해야 할 작업
```
$ git config --global user.name "당신의유저네임"
$ git config --global user.email "당신의메일주소"
$ git config --global core.editor "vim"
$ git config --global core.pager "cat"
```

# 2. git init
 1) 프로젝트 폴더 만들기
      mkdir first-git-repo
      cd first-git-repo 
 2) local repository로서 역할 시작하기   
      git init
 3) github에서 새로 비어있는 remote repository생성 
     복사한 주소를 local repository에 등록하기
      https://github.com/당신의유저네임/first-git-repo.git
      git remote add orignhttps://github.com/당신의유저네임/first-git-repo.git
     (origin은 복사한 주소를 부리기 위한 이름이므로 다른 이름을 사용해도 무방)

  ✅ 잘 추가 되었는지 확인하기
     git remote get-url origin
     명령어를 입력하면 추가된 주소가 보인다. 

4) 새 파일을 만들고 작업 수행하기
    touch README.md
    vi README.md
    
    i를 눌러 insert모드 활성화
    텍스트 편집
    esc를 눌러 다시 nomal mode 활성화
    :wq 를 입력하여 저장한 뒤  vim을 종료

5) 현재 프로젝트 상태 확인하기
    git status
    untracked files : README.md 가 보이면 다음 작업할 준비 완성 

6)  work space에 추가된 새로운 파일을 index로 staging
     git add README.md

7) 추가된 README.md에 대한 설명을 commit 하기
     git commit
     i를 눌러 insert mode 활성화
     커밋 메세지 작성
     esc키를 눌러 nomal mode 활성화
     :wq 입력하여 저장한 후 vim 종료
     git status 입력 commit 내역 확인
      (vim이 아직 어색하다면 
      git commit -m "입력 내용" 바로 커밋 작성 가능)

     ✅ commit message 깔끔하게 입력하기
      ·commit message의 제목에 말머리를 달아 카테고리를 바로 확인할 수 있도록 하기
      feat:, docs:, test:, refactor:

8) remote repository로 push
    ❗첫 커밋이라면 -u (-set-upsteam) flag를 붙여 push
    git push -u origin mast
    ‼ 두번째 커밋부터는 -u 없이 바로 push
    git push origin master

# 3. git clone
1) github에서 remote repository를 먼저 생성한 뒤, 작업 공간으로 끌어와 작업 시작
LICENSE, README.md, .gitignore 등의 파일과 함께 생성
 
 2) clone or download 버튼을 눌러 해당 repository 주소 복사
 
 3) 터미널에서 git clone 복사한remoteRepo주소 를 입력하여 작업공간에 local repository생성

 4) 새 파일을 만들고 작업 수행
  touch README.md
  vi README.md
  i를 눌러 insert mode 활성화
  텍스트 편집
  esc키 눌러 nomal mode 활성화
  :wq 를 입력하여 저장한 뒤 vim 종료
  
 5) 현재 프로젝트 상태 확인
   git status
   untracked files: README.md 가 보인다면 다음 작업할 준비 끝

6) workspace에 추가된 새로운 파일을 index로  staging
  git add README.md

7) 추가된 README.md에 대한 설명을 commit
  git commit

8) commit이 끝났다면 remote repository로 push
  git push origin master
 
✅ gitin과 다르게 remote repository에서 먼저 끌어와 사용하는 구조이기 때문에 -u flag를 붙이지 않아도 됨
