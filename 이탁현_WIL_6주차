# Springboot Chap6 WIL - 이탁현

  
## Chapter 6. 스프링 DB접근 기술
  
  
### 6.1 H2 DB 설치
 개발이나 테스트 용도의 가볍고 편리한 DB, 웹 화면 제공

jdbc:h2:tcp://localhost/~/test 양식 접속
 
 sql/ddl.sql 파일 생성

 // 지난 프로젝트로 인해 설정 완료
 
### 6.2 순수 JDBC

   메모리 저장 x, insert와 select memory로 db에 저장.

   build.grandle 파일에 jdbc,h2 db관련 라이브러리 추가.

   스프링 부트 데이터베이스 연결 설정 추가 -> resource/application.properties

   jdbc repository 구현(api)  -> 현재는 직접 하지 않음.

   
   
  
### 6.3 스프링 통합 테스트

   @SpringBootTest로 테스트 시작(전에는 복잡)
   
   @Transactional -> 테스트케이스에서 이 애노테이션이 있으면 테스트 시작 전에 트랜잭션을 시작하고 테스트 완료 후 롤백.

   DB에 데이터 남지 않아서 다음 test에 이슈 x.
   
   @Autowired 만 붙여서 필드 기반으로 하면 편함. 
   
   @Autowired MemoryMemberRepository 가 아닌 MemberRepository만 작성.

  


  ### 6.4 JdbcTemplate


  ### 6.5 JPA

   기존의 반복 코드 + 기본적인 SQL
   
   객체중심으로 설계 가능, 개발 생산성 상승

   build grandle 파일에 h2와 JPA 관련 라이브러리 추가

   jdbc는 제거 가능 (이미 포함되어 있어서)

   `spring boot` 에 JPA 설정 추가 resource/application.properties

   show-sql >> JPA 생성하는 SQL 출력

   ddl-auto >> JPA는 테이블 자동 생성 o, none 은 이 기능 off.

   create를 통해 엔티티 정보 바탕으로 테이블 직접 생성.


  ### 6.6 Spring data JPA

  이를 사용하면 repository에 구현 클래스 없이 인터페이스만으로 개발 완료.
  CRUD 기능도 제공해준다.

  실무에서 관계형 DB사용 시 필수 사항.

  복잡한 동작의 Query는 `Querydsl` 라이브러리 사용.

  이를 통해 자바코드로 안전하게 작성하고 동작 쿼리도 가능.



# 소감
단순 프로젝트가 아닌 실제 업무에서도 쓰인다는 것에 대해 와닿았다.
