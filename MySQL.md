# ._.) MySQL에 대해 알아보자.
### 전세계에서 가장 널리 사용되고 있는 오픈소스 데이터베이스, MySQL

<br>

## 🖥 MySQL이란?

* 오픈 소스 관계형 데이터베이스 관리 관리시스템(RDBMS)

* MySQL AB사가 개발하여 배포/판매하고 있는 데이터베이스(DataBase)

* 표준 데이터베이스 질의 언어 `SQL(Structured Query Language)`을 사용

<br/><br/>

## 🖥 MySQL의 특징

* 매우 빠르고, 유연하며, 사용하기 쉽다.

* 다중사용자, 다중 쓰레드를 지원

* C, C++, Eiffel, 자바, 펄, PHP, Pyton 스크립트 등을 위한 응용프로그램 인터페이스(API)를 제공한다.

* 유닉스나 리눅스, Windows 운영체제 등에서 사용할 수 있다.

<br/><br/>

## 🖥 MySQL을 사용하는 이유는?

MySQL은 데이터를 저장하는 데이터베이스이다. 소규모 웹사이트에서 대기업에 이르기까지 다양한 용도로 사용할 수 있다. 또한 필요에 맞게 사용자 정의할 수 있는 많은 기능이 있다.

### ⌨️ MySQL의 일반적인 용도

* 웹사이트용 데이터 저장

* 모바일 앱용 데이터 저장

* 기업 애플리케이션용 데이터 저장

* 고객 또는 클라이언트의 데이터베이스 생성

* 의료 정보 저장

* 금융 정보 저장

<br/><br/>

## 🖥 MySQL의 장점

MySQL이 가지는 장점은 다음과 같다.
 
1. 오픈 소스 라이센스를 따르기 때문에 무료로 사용할 수 있다.
2. 다양한 운영체제에서 사용할 수 있으며, 여러 가지의 프로그래밍 언어를 지원
3. 크기가 큰 데이터 집합도 아주 빠르고 효과적으로 처리할 수 있다.
4. 널리 알려진 표준 SQL 형식을 사용
5. MySQL 응용 프로그램을 사용자의 용도에 맞게 수정할 수 있다.

<br/><br/>

## 🖥 MySQL의 단점 - 서버 한대짜리 솔루션이다.

### 용량 증대 방식

#### 1. Scale-Up : 서버에 CPU와 Memory 추가

<p align="center">
<img src="../img/Scale-up.png">
</p>

#### 2. Scale-Out : Master-Slave로 구성

<p align="center">
<img src="../img/Scale-out.png">
</p>

서버 한대로 돌리는 걸 서버숫자를 늘려서 사용한다.
근데 **mysql은 소프트웨어 자체가 두대, 혹은 그 이상의 서버에 같이 동작하지 못한다. 그냥 기본적으로 한대에만 돌아가는 소프트웨어다.**

이러한 mysql에 scale out을 할 수 있는 방법은 없을까?
 
만약 mysql 서버 한대로 읽을수 있는 데이터가 초당 100mb라고 하자. 근데 우리가 서포트해야할 읽기속도가 초당 200mb라면?
 
이런 경우에 `slave`를 만들 수 있다. mysql에 기본적으로 서버 한대가 있고(master) 마스터에 있는 데이터들이 slave로, **읽기 전용**으로 복사가 된다. 그래서 이러한 백엔드 시스템에서 데이터를 읽을 일이 있을 때는 이렇게 `slave`를 만들면 된다.
그리고 slave는 여러개를 만들 수 있기 때문에 slave중에 하나를 가져다 쓸 수 있고 slave들을 로드밸런서로 묶어서 이들 중에 살아있는것들 중 아무거나 한개와 연결하여 거기서다 쓸 수도 있다.
 
결국 mysql에서 말하는 scale out 방식은 `cluster` 형태의 `scale out` 방식이 아니라 `master slave`형태로 sql하나가 갖고 있는 내용을 다수의 서버에(slave)에 복제함으로써 다른건 몰라도 읽기는 더큰 용량을 지원해 주게 된다.

<br/><br/><br/>
***

## 참고
* [MySQL 소개](http://www.tcpschool.com/mysql/mysql_intro_intro)
* [반드시 알아야할 MySQL 특징 세 가지](https://gywn.net/2011/12/mysql-three-features/)
* [MYSQL이란 무엇입니까?](https://www.websiterating.com/ko/web-hosting/glossary/what-is-mysql/)
* [MYSQL이란?](https://server-talk.tistory.com/29)
* [MySQL 특징](https://engineer-diary.tistory.com/79)