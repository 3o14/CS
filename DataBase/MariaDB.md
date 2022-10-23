# ._.) MariaDB에 대해 알아보자.
### MySQL 창업자의 반발로 만들어진 무료 RDBMS, MariaDB

<br/>

## 🖥 MariaDB 란?

* MariaDB사가 제작한 **MySQL 코드 기반의** 오픈소스 RDBMS(관계형 데이터베이스 관리 시스템) 소프트웨어
 
* _🖐🏻 잠깐! 여기서 __MySQL 이란?__ 란?_

    - 1995년 5월 스웨덴의 MySQL AB사에 의해 최초의 MySQL 버전 출시

    - 이후 Sun Microsystems(썬 마이크로시스템스)에서 인수함

    - 다시 2010년에 Sun Microsystems를 오라클에서 인수하면서 MySQL은 오라클 소유가 됨

    - 이후 오라클은 MySQL을 유료화함

* 이에 AB사의 핵심 창업자 중 한 명이었던 몬티 와이드니어스가 오라클의 정책에 반발

* 2009년 동료들과 나와 MySQL코드를 기반으로 개발한 오픈소스 RDBMS가 바로 MariaDB

<br/><br/>

### 📍 MariaDB의 성능

* MariaDB는 MySQL에 비해 애플리케이션 부분 속도가 약 4~5천 배 정도 빠름

* MySQL의 기능을 완벽히 구현하면서도 성능 면에서는 최고 70%의 향상을 보이고 있다고 주장함

<br/><br/>

### 📍 저장 엔진

* 마리아 DB에는 새로운 저장 엔진인 아리아(Aria)뿐만 아니라, InnoDB를 교체할 수 있는 XtraDB 저장 엔진을 포함하고 있다.

<br/><br/>

### 📍 MySQL 대체 가능

* MySQL에서 플러그인으로 제공한 스레드 풀 기능이 내장되어 있음

* 스토리지 엔진을 활용한 샤딩 기술을 제공

* 즉, MySQL의 모든 버전을 대체할 수 있는 특징들을 갖추고 있다.

<br/><br/>

## 🖥 MariaDB의 특징

<br/>

### ⌨️ 오픈소스

* MySQL도 상업적인 용도를 제외하고는 교육, 개발용인 커뮤니티 버전은 무료로 제공하고 있다.

* 커뮤니티 버전은 실제 서비스에 사용하기에는 성능이 따라주지 않는게 실상이다.

* 하지만 MariaDB는 상업용을 사용해야 더 좋은 성능을 내는 그러한 개념이 없이 모든 기능을 무료로 사용할 수 있다.

<br/>

### ⌨️ MySQL 친화적인 RDBMS

MySQL에서 Fork된 RDBMS인만큼 MySQL과 친화적이기 때문에 마이그레이션할 때도 손쉽게 진행할 수 있다. 실제로 MySQL에서 사용하고 있는 SQL문이나 명령문들을 그대로 MariaDB에서 채택하고 있는 경우가 많다.

<br/>

### ⌨️ MySQL 코드 베이스지만 MySQL과는 독립적인 RDBMS

InnoDB와 같이 MySQL RDBMS에서 어떤 플러그인 형태로 끼웠다가 빼서 쓸 수 있는 것이 아닌 그 자체로 독립적인 RDBMS라는 것을 의미한다. 또한 RDBMS에서 Fork 되었지만 이제 MySQL에서 제공하지 않는 독자적인 기능 및 구문을 제공하고 있다.

<br/><br/><br/>
*** 

## 참고
* [[DataBase] Maria DB](https://ko-ko.tistory.com/1)
* [[DB 이론] MariaDB란?](https://bio-info.tistory.com/102)
* [[MariaDB] MariaDB란 무엇일까? MariaDB 소개 (MariaDB Overview)](https://engkimbs.tistory.com/931)