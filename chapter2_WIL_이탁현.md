# Springboot Chap2 WIL - 이탁현

## Chapter 2. 스프링 웹 개발 기초

### 2.1 정적 컨텐츠
`static` 단어 그대로 움직이지 않고 형태가 정해진 파트!

브라우저에 보여줄 html파일을 resources/static 폴더 안에 생성한다.

```java
<!DOCTYPE HTML>
<html>
<head>
  <title>static content</title>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
</head>
<body>
정적 컨텐츠 입니다.
</body>
</html>
```

**서버 포트가 8080이므로 localhost:8080/~~.html로 주소가 나온다.**

추가적인 코딩x, 화면 그 자체만 볼 수 있다. (다른 언어에서 변수 없는 Print와 비슷)

### 1.2 MVC와 템플릿 엔진

`MVC` → `Model`+`View`+`Controller`

`Model` -> 말 그대로 앱이나 웹의 데이터를 의미 한다.

`View` -> User가 보는 화면 즉, 인터페이스! (Model의 data를 렌더링)

`Controller`-> 화면인 `View` 와 `Model`을 이어주는 역할. 

UI에서 데이터의 이벤트들을 진행시켜 준다.

```java
@Controller
public class HelloController {

	@GetMapping("hello-mvc")
	public String helloMvc(@RequestParam("name") String name, Model model) {
		model.addAttribute("name", name);
		return "hello-template";
	}
}
<html xmlns:th="http://www.thymeleaf.org">
	<body>
		<p th:text="'hello' + ${name}">hello!</p>
	</body>
</html>
```java

`@GetMapping("hello-name")` 은 `GET`방식으로 hello-name으로 호출함

`http://localhost:8080/hello-name`

`@RequestParam(value="",required="")`은 는 변수를 name이라는 key로 String 데이터를 받겠다 라는 의미

### 1.3 API



    


# 소감
강의 분량은 많지 않으나 새로운 것을 배울 때의 시간 투자는 역시 꽤 필요하다.
이전 프로젝트들 중에 프론트파트 담당자가 springboot로 진행했던 적이 있어서 코드가 친근하게 다가와서 다행이다.
