---
layout: post
title:  "Controller의 활용"
date:   2022-10-23 12:44:36 +0530
categories: SpringBoot
---
## Controller의 활용
어노테이션을 통해 다양한 형태로 컨트롤러를 작성할 수가 있다.
```java
@RequestMapping("/api")
@RestController

public class NewController {

    @GetMapping("/member")
    public String memberName() {
        return "회원리스트입니다";
    }

    @GetMapping("/member/{userId}")
    public String memberInfo(@PathVariable("userId") int userId) {
        return userId + " 의 정보입니다.";
    }

    @GetMapping("/calculate")
    public int calculateMethod(@RequestParam int number1, int number2) {
        return number1 + number2;
    }

    @GetMapping("/{type}/calculate")
    public String calculateType(@RequestParam int number1, @RequestParam int number2, @PathVariable("type") String type) {
        return number1 + "와 " + number2 + "의 " + "type은 " + type + "입니다.";
    }
}
```
