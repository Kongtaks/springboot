# Springboot Chap4 WIL - 이탁현

## Chapter 4. 스프링 빈과 의존관계
  
### 4.1 컴포넌트 스캔과 자동 의존관계 설정


```java
@Repository
public class MemoryMemberRepository implement MemberRepository{}

```
hellowContoller -> memberService -> memberRepository
`memberService` 와 `memberRepository` 스프링컨테이너에 스프링 빈으로 등록
(싱글톤) -> 같은 스프링 빈이면 같은 인스턴스


`@Component` 애노테이션 있으면 스프링 빈 자동 등록
`@Controller`스프링 빈으로 자동등록 -> 컴포넌트 스캔 덕분

`@Component`를 포함하는 애노테이션은 스프링 빈으로 자동 등록
`@Controller`
`@Service`
`@Repository`


### 4.2 자바코드로 직접 스프링 빈 코드 등록하기

```java
  package hello.hellospring;

import hello.hellospring.repository.MemberRepository;
import hello.hellospring.repository.MemoryMemberRepository;
import hello.hellospring.service.MemberService;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class SpringConfig{

  @Bean
  public MemberService(){
    return new MemberService(MemberRepository());
  }


 @Bean
  public MemberRepository memberrepository(){
    return new MemoryMemberService();
   }
  }

  ```
  DI -> field, setter, **생성자(이게 보통 메인)** 주입으로 총 3가지.



# 소감
자바로 진행하는 과제들과 확실히 비슷해서 편하다.
매 강의에 꼭 코드를 직접 짜보자.
