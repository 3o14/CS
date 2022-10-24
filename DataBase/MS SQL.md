# ._.) MS SQL에 대해 알아보자.
### 지금은 잘 사용하지 않는 마이크로소프트사의 RDBMS, MS SQL

<br/>

## 🖥 MS SQL이란?

* Microsoft SQL Server의 약어

* MS사에서 1989년에 최초로 발표하면서 세상에 나온 DBMS

* MSSQL은 다른 RDBMS처럼 표준 SQL 언어인 ANSI SQL을 지원

* 자체적으로 구현한 T-SQL도 지원하고 있다.

* MSSQL를 사용하기 위한 인터페이스 프로그램으로 SSMS(SQL Server Management Studio)가 있다.

<br/><br/>

## 🖥 MS SQL의 입지

우리가 많이 사용하는 DBMS를 보면 Oracle, MySQL, MSSQL이 있는데요.

오라클의 경우 은행권등 커다란 빅 사이트에 주로 사용되며

MySQL은 웹서버용 DB나 개인용 DB로 많이들 사용하고

MSSQL은 그 중간적 입장으로 중소형 업체들이 회사 업무용 DB로 이용하는데

요새는 점점 입지가 줄어드는것 같습니다.

<br/>

물론 이것은 MS 개발자인 저의 생각이긴 하지만

이는 점점 자바나 PHP등의 개발 언어에 비해 MS 개발언어의 인기가 하락하기 때문인 듯 한데요.

<br/>

서버와 언어, DB 의 상관관계를 보자면

"유닉스,리눅스" <=> "자바,jsp,PHP" <=> "Oracle,MySQL"

"윈도우서버" <=> "C#,asp.net" <=> "MS SQL"

이러한 구조인데 유지비용, 안정성, 언어의 개방성, 개발툴 등에 의해

점점 MS 진영의 메리트가 떨어지고 있기 때문인것 같습니다.
<br/><br/>

## 🖥 MS SQL의 장점

<br/>

### ⌨️ 모든 버전의 Windows OS에서 매우 잘 작동

* Microsoft에서 개발 한 Microsoft SQL Server를 포함하여 실행되는 모든 제품은 Windows OS에서 잘 작동한다. 

* Windows XP, Windows Vista, Windows 7, Windows 8 및 Windows 10부터 Microsoft SQL Server를 설치할 수 있으며 매우 잘 실행될 수 있다.

<br/>

### ⌨️ 데이터 클러스터링 가능

* 데이터 클러스터링은 그룹화의 한 형태이다. 여러 군집으로 데이터.

* Microsoft SQL Server는 데이터 클러스터링 측면에서 이점이 있으므로 프로그래머나 개발자에게 부가가치가 된다.

* 이 데이터 클러스터링을 사용하면 데이터베이스 관리 작업을 더욱 쉽게 수행 할 수 있다.

<br/>

### ⌨️ 중앙 집중식 데이터베이스 제어

* 데이터베이스 관리는 중앙에서 수행된다. 

* 이는 데이터베이스 처리 및 구현시 통신 누락 또는 오류 발생을 최소화한다. 

* 데이터베이스는 제어 센터로 하나의 컴퓨터만 사용하기 때문이다.

<br/>

### ⌨️ 데이터베이스 백업 가능

* Microsoft SQL Server에서도 구현 프로세스 중 중단이 발생하는 경우 예방 조치로서 데이터베이스 백업 기능을 제공

* 또한 데이터베이스 백업 기능은 나중에 비슷한 시스템을 구축 할 경우에도 재사용이 가능하다.

<br/>

### ⌨️ 데이터 복구 및 복원 기능

* Microsoft SQL Server에는 데이터 복구 및 복원 기능이 있다.

* 데이터베이스에서 손상된 데이터 부분이 있다면 복구 및 복원을 수행 할 수 있다.

<br/><br/>

## 🖥 MS SQL의 단점

<br/>

### ⌨️ Windows OS에서만 사용할 수 있다

### ⌨️ 가격이 비싸다

### ⌨️ 제한된 프로그래밍 언어

### ⌨️ 대규모 데이터베이스에는 적합하지 않다

<br/><br/><br/>
***

## 참고
* [Microsoft SQL Server 이해 : 기능, 강점 및 약점](https://altitudetvm.com/ko/komputer/1459-pengertian-microsoft-sql-server-fungsi-kelebihan-dan-kekurangannya.html)
* [[SQL / MSSQL] MSSQL이란?](https://data-is-power.tistory.com/132)
* [[MSSQL] MSSQL이란?](https://nowonbun.tistory.com/141)
* [[MS SQL 강좌] 1. MSSQL DBMS 를 알아보자](https://m.blog.naver.com/chsmanager/140210135913)