---
title: "Git(02)"
excerpt: "Upstage X FastCampus AI Lab - Git"
categories:
  - Bootcamp
tags:
  - [git, bootcamp]

permalink: /bootcamp/bootcamp-03/

toc: true
toc_sticky: true

date: 2024-04-22
last_modified_at: 2024-04-22
---
# 🦥 Git

## **Git Branch**

- 분기점을 생성하여 독립적으로 코드를 변경할 수 있도록 도와주는 모델  
  &emsp;(EX) 스파이더맨 영화를 생각해보자!  
  &emsp;스파이더맨 1, 2, 3 각각 다른 빌런들이 나온다 - **브런치 생성**        
  &emsp;그러다가 통합된 스파이더맨 모두가 나오면 편이 나옴 - **브런치 합치기**  
  &emsp;&emsp;&emsp; **→ 이 모든게 브런치와 비슷함!!!**

  ![branch](https://github.com/huniii32/branch-practice/assets/164001121/54684367-c1e5-4d2e-ae74-b8c1fc70e097)

- **git branch**   
  ```bash
  $ git branch -r
  $ git branch -v
  $ git branch -a
  $ git branch {space}
  $ git branch -D {space}
  ```

- **git switch** 
  ```bash
  $ git switch {space}  
  ```

  **→ 브런치 이동시 확인 및 'ls' 사용하여 파일 확인**  
  **→ 브런치 다 사용시 바로바로 삭제 하기!!**  

**😀이것들을 모두 습관으로 만들자!!**  

- **git merge**  
  ```bash   
  $ git merge {space}   
  ```    

  > ✋vim normal mode✋   
  > dd : 잘라내기   
  > p : 붙여놓기      

## **Git Branching Strategy**

- **git flow**
  - 가장 전통적이고 많이쓰이는 모델
  - 각 단계가 명확히 구분되어 배포주기가 주기적인 서비스에 유리. 하지만 복잡.. 

  ![image](https://github.com/huniii32/branch-practice/assets/164001121/9d041269-8c8c-41fb-8280-af90c40cf042)

- **github flow**
  - 브랜치 모델의 단순화. 
  - CI 의존성이 높고, pull request가 없으면 실수에 대처가 힘듦

  ![image](https://github.com/huniii32/branch-practice/assets/164001121/63517b52-964d-43a0-9b3b-d5b19c99811a)

  ```bash   
  $ git push -u origin {space}    
  ```  

  **→ 올려놓고 Github에서 merge 실행**  

  ```bash  
  $ git pull origin main  
  ```  

  **→ Local Update**

- **gitlab flow**
  - deploy, issue에 대응을 하기 쉽도록 한 모델

  ![image](https://github.com/huniii32/branch-practice/assets/164001121/acc58b29-2563-4c95-ba05-a21202e68515)

## **Trouble-Shoot**

- **Rename**
    ```bash
    $ mv {filename} to {new_filename}
    ```
    → 파일 이름이나 위치를 수정합니다.

- **Undo**
    ```bash
    $ git restore {filename} or .(whole changes)
    ```
    → 작업 디렉토리에서 변경 사항을 취소합니다.

- **Unstaging & Remove**
    ```bash
    $ git reset HEAD {filename}

    $ git rm -f {filename}
    ```
    → 스테이지된 변경 사항(blob)을 작업 디렉토리로 내립니다.  
    → 스테이징 영역의 변경 사항을 내리면서 동시에 삭제합니다.

- **Edit commit message**
    ```bash
    $ git commit --amend

    $ git rebase -i <commit>
    $ git rebase --continue
    ```
    → 직전 커밋 메시지를 수정합니다.  
    → 이전 커밋 메시지를 수정합니다. (rebase 취소: `git rebase --abort`)

- **Reset commit**
    ```bash
    $ git reset --hard HEAD~{nums of commit}
    $ git push -f origin <branch>
    ```
    → {nums of commit}개의 커밋을 삭제한 후 원격 <branch>로 강제 푸시합니다.  
    → 협업 시에는 나의 로컬 및 클론한 원격 리포지토리에서 삭제되었다고 해도 다른 곳에 남아있던 이력 때문에 문제가 발생할 수 있습니다.

- **Revert commit**
    ```bash
    $ git revert --no commit HEAD~{nums of commit}
    $ git commit
    $ git push origin <branch>
    ```
    → {nums of commit}개의 커밋을 되돌린 후 원격 <branch>로 푸시합니다.  
    → 잘못하기 직전 시점으로 되돌리고 해당 되돌림의 이력을 팀원들에게 전달하여 어떤 문제가 있었고, 어떻게 수행되는지에 대해 명확하게 설명할 수 있습니다.  
    - 커밋을 별도로 하지 않을 경우 'no-edit'  
    - 병합 커밋을 되돌릴 경우 '-m'  

    (예시)
    ```bash
    $ git revert -m {1 or 2} {merge commit id}
    ```

## **💻Insight💻**
내가 얻은 것은 크게 두가지이다.  
1. 로컬과 Github의 파일 관리 방법론?? 매커니즘
2. 팀 프로젝트시 팀원들과의 협업?? - 이거는 아직 낯설지만, 하다보면 늘어나겠지~~~

아무튼 이 두 부분을 얻어갔다!! 총총총...  
이제 통계론, 파이썬 EDA 배울텐데 체력 관리 예습!!!! 미리미리 해두자!!  
몰아쳐서 하면 진짜 힘들다!!!! 제발로!!!!💻

![passion](https://github.com/huniii32/branch-practice/assets/164001121/c27c125a-7207-43df-b776-d6958248a33b)


 
#패스트캠퍼스 #업스테이지패스트캠퍼스 #AI부트캠프