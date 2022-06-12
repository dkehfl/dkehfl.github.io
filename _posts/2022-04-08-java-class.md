---
layout: post
title:  "Class"
date:   2022-04-08 04:03:36 +0530
categories: Java
---
## 클래스??
***
클래스란 객체를 정의해 놓은 것이다.
클래스는 객체를 생성하는데 사용한다.

### 클래스와 객체의 관계
클래스와 객체의 관계는 제품 설계도와 제품의 관계라고 할 수 있다. 클래스 하나를 생성해 두면 그 형식에 맞춰 객체를 작성하면 되므로 간편하다.   
프로그래밍 시에는 클래스를 먼저 작성한 다음 클래스로부터 객체를 생성하여 사용한다.

## 클래스의 구성 요소
***
클래스는 필드(field)와 메소드(method)로 구성되어 있다.(+ 생성자)    
이 둘을 통틀어 멤버(member)라고 한다.

```java
class Example {
    String name;
    int price;      /// 필드

    Example(String n) {
        name = n;       /// 생성자. 보통 생성자가 메소드 앞에 온다.
    }

    void setName(String name) {
        this.name = name;
    }

    void setPrice(int price) {
        this.price = price;     /// 메소드
    }
}
```

## 사용자 정의 타입
***
기본 자료형(primitive type) 외에 프로그래머가 서로 관련된 변수들을 묶어서 하나의 타입으로 새로 추가하는 것을 사용자정의 타입(user-defined type) 이라고 한다.   
자바에서는 클래스가 곧 사용자 정의 타입이다. 사용자 정의 타입은 곧 참조형(reference type) 이다. 따라서 클래스는 일종의 참조형 타입이라고 할 수 있다.





