# 윈도우 환경에서 git 사용하기

## 배경
앞에서 문서화 하는 데 많은 기여를 해 줄 Atom편집기에 대해 알아 보았다. 다양한 플러그인을 지원해 주는 아톰을 사용하기 위해선 윈도우 환경에서 git을 사용 할 수 있는 환경이 필요하였다. 항상 가상머신을 설치하여 우분투 리눅스 터미널 에서 git을 사용하였던 이전과는 다른 환경을 구축해 줄 필요성을 느끼게 되었다.

그리고 찾게 된 것이 바로 이 gitbash와 gitkraken 이라는 프로그램 이다.

--------------------------------------------

# Git bash
### Git bash 장점
> 기존에 git 을 사용하기 위해서는 가상머신 -> 리눅스 실행 -> 터미널 과 같은 과정을 통해 접근 할 수 있었다. 하지만 저번 포스팅에서 언급하였던 아톰을 사용하기 위해서는 가상머신 내 에서가 아닌 윈도우 에서 git을 사용할 환경이 필요 하였다. 이를 해결해 주는 것이 git bash 이다.
git bash 이미지 삽입
> 설치를 마치고 git bash를 실행 해 보면 터미널에서 git을 사용한 것과 같이 동일한 모습으로 git을 윈도우 에서 사용 할 수 있다.

### Git bash 기본 명령어
> 기본 명령어는 리눅스 터미널 에서 지원하던 것과 비슷하다.

#### 사용자 정보
>$ git config --global user.name "이름"
>
>$ git config --global user.email 메일주소@example.com

#### 설정 확인
>$ git config --list
#### git 저장소 만들기
>$ git init
#### repository 연결하기
>$ git remote add origin repository주소
#### git push 하기
>$ git add .
>
>$ git commit -m "내용"
>
>$ git push -u origin master

-----------------------
# Git Kraken
## 브랜치 시각화
리눅스 터미널 환경에서 다음과 같은 명령어를 입력하면 현재 github 저장소 에서 생성된 브랜치 들의 모습을 가지의 모습으로 볼 수 있었다.
>
