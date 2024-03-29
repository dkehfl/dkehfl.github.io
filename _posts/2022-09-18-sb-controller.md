---
layout: post
title:  "Controller"
date:   2022-09-18 12:44:36 +0530
categories: SpringBoot
---
## MVC 패턴과 Controller

컨트롤러라 하면 MVC 패턴 중 C를 가리킨다. View로 부터 사용자의 요청을 가장 먼저 받는 역할을 한다.
![mvc](http://drive.google.com/uc?export=view&id=1Q6Z3-0w5n9vTJjOd6bnboMHwk3jW8IU9)

## Controller의 사용 예시

컨트롤러를 활용하여 요청을 받는 메소드를 만들어 보자.

먼저 api로 매핑해 준다. 이렇게 하면 웹 주소를 입력할 때 ```/api```를 먼저 입력해 주면 된다.   
그 다음으로 RestController를 불러 준다.   
Slf4j는 로그 작성을 위해 불러왔다. 뒤를 참고하자.

```java
@Slf4j
@RequestMapping("/api")
@RestController
```


다음으로 TestController 클래스를 작성하자. TestController 클래스 안에 매핑할 내용들을 각각 메소드와 함께 작성해 주면 된다.    
다음으로는 test를 매핑해 준다. 이렇게 하면 ```localhost:8080/api/test``` 이런 식으로 입력하면 창이 뜬다. GetMapping 외에도 여러 목적의 http 매핑 종류가 총 6개 존재한다. 나머지는 다음에 포스팅할 생각이다.    
그 밑에는 TestMethod 메소드에 창에서 띄울 내용을 작성해 준다.

```java
@Slf4j
@RequestMapping("/api")
@RestController

public class TestController {

    @GetMapping("/test")
    public String testMethod() {
        return "hello world";
    }
}
```

웹상에서는 다음과 같이 보여진다.
![test1진짜](http://drive.google.com/uc?export=view&id=1_mwpG25NDXhFu-usouOb-IEqJDC4lqv-)


이번에는 다른 형태의 내용을 띄워 보자.   
내용은 위와 비슷한데 여기서는 int값을 띄운다. 변수 number에 원하는 숫자를 입력해 주면 된다. ```localhost:8080/api/test2?number=(원하는 숫자)``` 요렇게 입력하자.
```java
@Slf4j
@RequestMapping("/api")
@RestController

public class TestController {

    @GetMapping("/test2")
    public int test2Method(@RequestParam int number) {
        return number + 10;
    }
}
```
웹상에서는 다음과 같이 보여진다.
![test1_](http://drive.google.com/uc?export=view&id=1w8UJxnTjliS-f_sYnqF6S7lUX9sFSghi)


아래처럼 작성할 수도 있다. ```localhost:8080/api/test3/(원하는 문자)``` 요렇게 입력하자.

```java
@Slf4j
@RequestMapping("/api")
@RestController

public class TestController {

    @GetMapping("/test3")
    public String test3(@PathVariable("name") String name) {
        log.info("test3 controller 실행");
        return "안녕하세요 저는" + name + "입니다";
    }
}
```
웹상에서는 다음과 같이 보여진다.
![test3](http://drive.google.com/uc?export=view&id=1Mf8Ssan8B02Y0BzNOpL9ylNdlEOgf8Ht)