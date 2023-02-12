# ._.) 터미널을 사용해보자

## 🖥 Shell이란?
* 우리가 명령어를 입력하면 해석을 해 OS 에 전달하는 프로그램

* Shell의 종류: sh, ksh, csh, bash, tcsh, zsh (맥은 카탈리나 OS 부터 기본 쉘로 zsh 를 사용하고 있다.)

* Oh My Zsh 플러그인을 사용하면 경로를 예측해서 알려주거나 명령어를 추천 하는 등 zsh 를 더욱 강력하게 사용 할 수 있다.
<br/><br/>

## 🖥 Terminal이란?

* 입력한 명령어를 받아 shell 에 전달하고 OS 가 보내준 결과를 출력하는 곳이 Terminal 이라고 할 수 있다.

* Shell 과 Terminal 은 꼭 붙어다니는 짝꿍이다. (그냥 Shell 과 Terminal 은 한 몸으로 생각해도 될 것 같다.)

* 맥에 기본 Terminal 이 있지만 기능을 확장한 iTerm 을 사용하면 더 편하게 사용 할 수 있다.

* 리눅스를 다루려면 쉘을 잘 알아야 하기 때문에 열심히 공부하도록 한다 !
<br/><br/>

## ⚙️ 터미널 명령어Permalink
다양한 명령어들이 있는데 이 중에서 아주 기초적인 명령어를 정리해봤다.

### ⌨️ $ pwd
* Print Working Directory

* 현재 자신이 있는 디렉토리를 표시한다.

<br/>

### ⌨️ $ cd + [경로명]
Change Directory를 의미하며, 가고자 하는 디렉토리로 이동 할 수 있다.

* `$ cd /` : 루트 디렉토리로 이동한다.

* `$ cd ~` : 홈 디렉토리로 이동한다.

* `$ cd ~/Desktop` : 데스크탑으로 이동한다.

* `$ cd ..` : 부모 디렉토리로 이동한다.

cd 명령을 사용 하는 경우에 zsh 의 자동완성 기능이 아주 많은 도움을 준다. 가고자 하는 디렉토리의 일부만 입력해도 자동으로 완성 해 준다.

$ cd k/p/pr 만 입력 한 뒤 Tab 을 누르면 경로가 자동으로 완성된다.

<br/>

### ⌨️ $ ls + [옵션명] + [경로명]
List Segment 로 경로의 구성요소를 보여준다.

* `$ ls` : 현재 경로의 하위 파일 / 디렉토리를 보여준다.

* `$ ls -l` : 현재 경로의 하위 파일 / 디렉토리의 자세한 정보 (사용권한, 소유자, 그룹, 크기, 날짜) 를 보여준다.

* `$ ls -la` : 숨김 파일까지 모두 보여준다.

* `$ ls -l 경로명` : 해당 경로의 하위 파일 / 디렉토리를 보여준다.

<br/>

### ⌨️ $ cp [원본파일] [대상파일] / $ mv [원본파일] [대상파일]
* `$ cp ~/Test/testFile ~/Test2/`

Test 폴더에 있던 testFile 이 Test2 디렉토리에 복사된다.

* `$ mv ~/Test/testFile ~/Test2/`

Test 폴더에 있던 testFile 이 Test2 디렉토리로 이동된다.

모두 파일 대상 명령어이기 때문에 디렉토리를 다루고 싶다면 명령어 뒤에 -r 을 붙여 사용하면 된다.

<br/>

### ⌨️ $ touch / $ mkdir

* `$ touch ~/Test/testFile`

Test 디렉토리에 testFile 의 이름을 가진 빈 파일을 생성한다.

* `$ mkdir ~/Test/test`

Test 디렉토리에 test 의 이름을 가진 빈 디렉토리를 생성한다.

<br/>

### ⌨️ $ rm
* `$ rm ~/Test/testFile`

Test 디렉토리에 있는 testFile 을 삭제한다.

* `$ rm -rf ~/Test/`

Test 디렉토리를 삭제한다.

디렉토리를 삭제하고 싶다면 $ rmdir 명령어를 사용해도 가능하다.

또 $ rm -r 명령을 사용하면 삭제하고자 하는 디렉토리가 없는 경우 에러메시지가 출력 되지만

$ rm -rf 명령을 사용하면 디렉토리가 없는 경우 아무 일도 일어나지 않는다.


***
## 참고
* [맥 터미널 명령어 입문1: 파일, 디렉토리 명령어](https://haloaround.tistory.com/7)
* [[Backend] 터미널 사용방법](https://nam-ki-bok.github.io/backend/Backend_6/)
