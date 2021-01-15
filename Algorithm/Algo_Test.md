# JPA  

## 정의
JPA(Java Persistence API)는 현재 ORM(Object Relational Mapping)의 기술 표준으로, 인터페이스 모음이다.  
즉, ORM을 사용하기 위한 인터페이스 집합이라고 볼 수 있다.      
ORM에 대한 자바 API 규격이며 Hibernate, OpenJPA 등이 JPA를 구현한 구현체이다. 

## 특징
1. 자바 객체와 DB 테이블 사이의 매핑 설정을 통해 SQL을 생성한다.  
JDBC의 DB 연결 방법을 이용하면, DB 변경 시 모든 쿼리를 수정해야 하고, 실행한 쿼리를 자바 객체에 설정해줘야한다.    
하지만 JPA는 자바 객체로 매핑하여 검색할 수 있고, DB 변경 시 매핑 설정만 변경하면 된다.     
-> 유지보수가 쉽다.  

2. 객체를 통해 쿼리를 작성할 수 있는 JPQL(Java Persistence Query Language)를 지원한다.  

3. JPA는 성능 향상을 위해 지연 로딩이나 즉시 로딩과 같은 몇가지 기법을 제공하여, SQL을 직접 사용하는 것과 유사한 성능을 얻을 수 있다.  
하지만 오히려 추상화 처리로 인한 성능과 상세 제어에 문제가 발생할 수 있다.
