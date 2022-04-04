# ._.) DNS는 무엇일까?
### 이번에는 DNS (Domain Name System)에 대한 개념과 사용하는 이유, 구성 요소, 동작 원리에 대해서  알아보자.

## 🖥 DNS?
* Domain Name System
* 문자열이 탈을 쓴 ___IP주소___ ( [TCP/IP](https://github.com/3o14/CS/blob/main/%08internet.md#-tcpip) )
* 예) naver.com, google.com

### _🖐🏻 잠깐! 여기서 IP란? - IP(Internet Protocol)_
* 사람은 우편을 보낼 때, ___주소___ 로 발신자와 수신자를 표시한다.
* 마찬가지로 컴퓨터는 데이터를 주고 받을 때, ___IP주소___ 를 이용한다.
* 즉, IP주소는 인터넷상에서 데이터를 주고 받기 위한 통신 규약(약속)이다.
<br/><br/>

## 🖥 DNS를 사용하는 이유는?
### ._.) 너무 많아
#### IP주소는 `0.0.0.0` 부터 `255.255.255.255` 까지 2의 32제곱으로 대략 42억개이다.
### ._.) 이렇게 불편하면 아무도 안쓸듯
#### 복잡하고 긴 숫자를 일일이 외워서 사용하기에는 너무 불편함
### ._.) 해결 방안!
#### 따라서 `naver.com`이나 `google.com` 등 문자로 이루어진 지금의 도메인 주소를 사용한다.
### _즉, 사람이 기억하기 쉽도록 IP 주소를 도메인 주소로 변환하는 시스템이 바로 DNS인 것이다._

（未完了）








***
## 참고
* [IT_세상 만사 - DNS(Domain Name System) 개념 및 동작원리](https://ja-gamma.tistory.com/entry/DNS%EA%B0%9C%EB%85%90%EB%8F%99%EC%9E%91%EC%9B%90%EB%A6%AC)
* [goban.log - DNS와 작동원리](https://velog.io/@goban/DNS%EC%99%80-%EC%9E%91%EB%8F%99%EC%9B%90%EB%A6%AC)
* [인터넷-네트워크 유틸 - IP주소란? IP주소의 개념과 이해](https://c0mp.tistory.com/927)
