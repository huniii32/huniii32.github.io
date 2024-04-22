---
title: "Git(01)"
excerpt: "Upstage X FastCampus AI Lab - Git"
categories:
  - Bootcamp
tags:
  - [git, bootcamp]

permalink: /bootcamp/bootcamp-02/

toc: true
toc_sticky: true

date: 2024-04-19
last_modified_at: 2024-04-22
---
# 🦥 Git

 **!!!! ✋잠깐✋ !!!!** 


## **UNIX 명령어**  

- pwd : 현재 디렉토리 경로 확인  

- ls : 디렉토리 내용 확인 
  - ls -a : 숨김 파일 확인('.' 유닉스 처리 방식)   
  - ls -l : 상세정보 확인  
  - ls -al : 숨김 파일 상세 확인  

- cd {name} : 디렉토리 이동  
- mkdir {name} : 디렉토리 생성  
- touch {name} : text 기반의 파일 생성  

- mv {file} {space} : '경로'로 '파일' 이동  
  - mv ../*.py ./ : py 파일을 해당 경로에 이동  
  - .. : 상위 디렉토리  
  - . : 해당 디렉토리    

- cp main.py ./main_copy.py : main.py를 해당 디렉토리에 main_copy.py 복사
  - cp main.py ..  

- mv LICENSE ./license.txt : LICENSE를 해당 디렉토리에 license.txt 이름으로 이동(변경)  

- rm '파일' : '파일' 삭제   
  - rm -rf '디렉토리' : 디렉토리 삭제 

- vi '파일' : 파일 편집기

- cat '파일' : 파일 내용 확인  


## **Git**

- **1. Git 개념**
  - 분산형 버전관리 시스템(Distributed Version Control System)  
  - 일주일만에 만들었다고한다... ㄷㄷㄷ  
  - 단순한 구조와 빠른 속도!!  
→ 압도적 업계 1위  

간단하게 Git은 이러한 방식으로 작동한다!  
이것만 기억하자 **add / commit / push!!**

![flow](https://github.com/huniii32/first-repo/assets/164001121/3f19c941-83d1-44b0-979e-2c35bb3c15c0)

- **기본 설정(config)**

  - gitconfig 편집
  ```
  $ vi ~/.gitconfig  
  ```

  - **global 설정**
  ```
  $ git config --global core.autocrlf false  
  $ git config --global user.name "username"  
  $ git config --global user.email "email"  
  $ git config --global core.editor "vim"  
  $ git config --global core.pager "cat"  
  $ git config --global alias.lg "log --graph --pretty=tformat:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --decorate=full"  
  ```

  - **repositories 생성**
  1. Name 설정
  2. License 설정
  3. Terimal - git clone '주소'

  - **Git 명령어**
  ```
  $ git status
  $ git add
  $ git commit
  $ git diff {filename}
  $ git push origin main
  ```

### **Converntional Commits**
- commit의 제목은 commit을 설명하는 문장형이 아닌 구나 절의 형태로 작성
- importancefcapitalize 'Importance of Capitalize'
- prefix 달기!!
    - feat : 기능 개발 관련
    - fix : 오류 개선 혹은 버그 패치
    - docs : 문서화 작업
    - test : test 관련
    - conf : 환경설정 관련
    - build : 빌드 작업 관련
    - ci : Continuous Integration 관련
    - chore : 패키지 매니저, 스크립트 등
    - style : 코드 포매팅 관련

- **형태** 
  > {type}: {description} 작업단위 축약(breaking change가 있다면 type 뒤에 !)  
  > {body} 작업 상세 기술  
  > {footer} 부가정보(ex) BREAKING CHANGE: Drop email sign up support

- 예시(1)
  > feat: add sign up component   
  > This commit adds the sign up component to the application.   
  > Closes #123  

  - 예시(2)
  > fix!: resolve issue with login page   
  > This commit fixes an issue with the login page that prevented users from logging in.   
  > Closes #123   
  > BREAKING CHANGE: drop social login support  

**강사님께서 정말 강조하셨다!!!!**  
이러한 방식으로 하지 않으면 아싸취급...? 사회 적응 못함...!! 이런 느낌이다!!  
지킬건 지키자!!!

### **.gitignore**  

  - 특정 파일이나 디렉토리를 추적하지 않도록 명시하기 위한 파일  

(템플릿 참고 사이트)  
.gitignore file 생성 사이트 : <https://www.toptal.com/developers/gitignore/>  
이곳을 잘 활용해보자!  


## **Git Blog**
내가 하던 부분이라 패스하겠음!!!  
나는 **Jekyll** 사용했는데  
해당 강의에서는 Hexo 사용함!  

![blog](https://github.com/huniii32/first-repo/assets/164001121/5c95d1b9-2fca-4a47-86c8-ebe38b2e4864)  

아직 많이 부족한 블로그 ㅎㅎㅎ  
계속 추가할 예정임!!!

## **총총**
1. TIL(Today I Learned) 배운 내용 정리  
    - 매일 git으로 업로드!
    - 커맨드 연습도 가능! 
2. Git Blog 
    - 블로그로 정리하는 습관 길들이기!
    - Markdown 학습!
3. Side Project
    - 짧은 단위의 프로젝트를 자주 수행하여 **생성-완성**까지의 과정을 반복해보자!

![fighting](https://github.com/huniii32/first-repo/assets/164001121/740ac834-ef67-47e9-a219-6899c856af07)

#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프