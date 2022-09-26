# ._.) 터미널 기본명령을 알아보자! (下)
### grep, awk, sed, lsof, curl, wget, tail, head, less, find, ssh, kill
> 터미널 기본명령을 알아보자!（上） - grep, awk, sed, lsof, curl, wget
> 
> 터미널 기본명령을 알아보자!（下） - tail, head, less, find, ssh, kill

<br/>

## 🖥　head, tail - 리눅스 파일 시작, 끝 출력 명령어
리눅스에서 파일의 길이가 매우 길어서 일부만 확인해야 하는 경우가 있다.

예를들어 로그파일이 잘 작성되고 있는지 보려면전체를 보는 대신 끝의 몇줄을 보고 최신 날짜까지 작성이 됬는지 확인할 수 있다.

이때 사용하는 명령어가 `head`, `tail` 명령어이다.

* `head`는 파일의 앞부분을 확인하는 명령어

* `tail`은 파일의 뒷부분을 확인하는 명령어

<br/>

## ⌨️ 사용법
```
head [option] filename1, filename2, ...
tail [option] filename1, filename2, ...
```

사용 예시를 보려면 [여기를 클릭](https://arer.tistory.com/148)
<br/>

## ⌨️ 옵션
* -n num : num수 만큼 출력해준다.

* -c num : num byte만큼 출력해준다.

* -q : 여러개의 파일을 출력할 때 제목을 출력하지 않는다.

* -f : 내용이 변경될 때마다 실시간으로 출력해준다. 로그파일 모니터링 등에 활용. (tail만 있음)
<br/><br/>

## 🖥 less 명령어 - 한 페이지씩 보기
less는 파일 또는 명령 출력의 내용을 한 번에 한 페이지씩 표시하는 명령줄 유틸리티

more와 비슷하지만 고급 기능이 있어 파일을 앞뒤로 탐색할 수 있다.

<br/>

## ⌨️ 사용법
```
less [OPTIONS] filename
```

<br/>

## ⌨️ 옵션
* -N : 줄 번호를 출력

* Space :	줄 번호를 출력하는 옵션

* f	: 다음 페이지로 표시

* Enter :	행 단위로 표시하는 명령

* /[String] :	표시되는 파일에 내용 기준 이후에 내용의 문자열을 찾기

* ?[String]	: 표시되는 파일에 내용 기준 이전에 내용의 문자열을 찾기

* q	: less 명령어를 종료하는 명령
<br/><br/>

## 🖥 find - 검색하기
리눅스의 find 명령어는 리눅스 파일 시스템에서 파일을 검색하는 데 사용되는 명령어

다양한 표현식을 사용하여 원하는 파일의 목록을 추출할 수 있다.

<br/>

## ⌨️ 사용법
```
$find [경로] [플래그] [표현식]
```
* 경로 : ‘/’, ‘~’, ‘~/Desktop’ 등 경로를 입력

* 플래그 : -name 등의 플래그(옵션) 입력

* 표현식 : 검색할 파일의 이름 혹은 패턴 등 표현식을 입력

<br/>

## ⌨️ 사용 예

* 현재 디렉토리(.) 내 ‘.txt’를 포함한 모든(*) 파일 검색 ▼
```
$find . -name "*.txt"
```
* root 디렉토리(/) 내 ‘.txt’를 포함한 모든(*) 파일 검색 ▼
```
$find / -name "*.txt"
```
* 홈 디렉토리(~) 내 ‘.txt’를 포함한 모든(*) 파일 검색 ▼
  * ~을 $HOME으로 대체해주셔도 결과는 같다.
```
$find ~ -name "*.txt"
```
* root 경로의 모든 파일, 링크, 소켓, FIFO, 디렉터리등 모든 것을 출력
```
$ find /
```
* root 경로에서 "파일"만 출력
```
$ find / -type f
```
* root 경로에서 "디렉터리"만 출력
```
$ find / -type d
```
* root 경로의 "파일" 중 size 가 5M 이상인 것만 출력 (k,M,G,T,P 로 단위 구분, +- 로 이상,이하 구분)
```
$ find / -type f -size +5M
```
* root 경로의 "파일' 중 size 가 5M 이상이고 권한이 644 인 것만 출력
```
$ find / -type f -size +5M -perm 644
```
* 644 앞에 +,- 를 붙이기도 하는데 +는 포함하는 모든것을, -는 일부라도 포함하는 것을 의미한다.
* 한편 +, -가 없는 것은 완전히 일치하는 퍼미션만 찾게된다.
* root 경로의 "파일" 중 size 가 5M 이상이고 파일의 상태가 변경된지 5일 이상 된 것을 찾는다. (s,m,h,d,w 를 단위로 구분, 이는 초,분,시,일,주를 나타낸다.)
```
$ find / -type f -size +5M -mtime +5d
```

자세히 보려면 [여기를 클릭](https://macinjune.com/all-posts/mac/terminal/맥-터미널-unix-find-command로-파일-검색하기/)
<br/><br/><br/>
***

## 참고
* [[리눅스] head, tail 명령어(리눅스 파일 시작, 끝 출력 명령어)]([https://wlsvud84.tistory.com/12](https://arer.tistory.com/148))
* [Linux : Less 명령어, 사용 방법, 예제](https://jjeongil.tistory.com/1629)
* [리눅스 명령어 삼대장: find, grep, awk](https://jybaek.tistory.com/704)
