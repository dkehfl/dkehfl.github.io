---
layout: post
title:  "Service"
date:   2022-10-30 12:44:36 +0530
categories: SpringBoot
---
## Service의 역할
Service는 비즈니스 로직을 처리하는 역할을 한다. 컨트롤러에서 받은 요청을 자세히 처리하는 건 서비스이다.

## 서비스의 사용 에시
주입 방식은 세가지가 있지만 여기선 생성자 주입 방식만을 다루려 한다. 그리고 이게 제일 효율적이다.   
우선 사칙 연산을 하는 서비스 클래스를 작성해 보자.
```java
import org.springframework.stereotype.Service;

@Service
public class CalculateService {
    public int calculate(int number1, int number2, String type) {
        if(type.equals("plus")) {
            return number1 + number2;
        }
        else if(type.equals("minus")) {
            return number1 - number2;
        }
        else if(type.equals("multiple")) {
            return number1 * number2;
        }
        else {
            return number1 / number2;
        }
    }
}
```

다음으로 지난 시간에 배운 컨트롤러 클래스에 주입해준다. 기본적인 생성자 개념만 제대로 알고 있다면 어렵지 않다. 

```java
import com.example.demo.Service.CalculateService;
import lombok.RequiredArgsConstructor;
import org.springframework.web.bind.annotation.*;

@RequiredArgsConstructor
@RequestMapping("/api")
@RestController

public class CalculateController {

    public final CalculateService calculateService; 
        // 생성자 주입

    @GetMapping("/{type}/number1/number2")
    public int calculate(@PathVariable int number1, @PathVariable int number2, @PathVariable("type") String type) {

        return calculateService.calculate(number1, number2, type);   
    }
}
```
예아