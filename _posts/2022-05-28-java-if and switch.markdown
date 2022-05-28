---
layout: post
title:  "if / switch"
description: if문과 switch문
date:   2022-05-28 22:47:36 +0530
categories: Java
---
## 조건문 if
***
if문은 가장 기본적인 조건문이다. 조건식과 괄호로 이루어져 있으며    
'만약 조건식이 참이라면 괄호{} 안의 문장을 수행한다' 라는 의미이다.   
다음 예시를 통해 확인해보자.

```java
if (age >= 15) {    /// 만약 age가 15 이상이면
    System.out.println("입장 가능합니다");  /// "입장 가능합니다" 를 출력한다.
}
```
나이가 15세 이상일 경우 "입장 가능합니다" 를 출력하는 조건문이 완성되었다.   

```java
public class Theater {
    public static void main(String[] args) {
        int age = 17;   /// age가 17

        if (age >= 15) {   
            System.out.println("입장 가능합니다");  
        }
    }
}
```
age가 15 이상이므로 "입장 가능합니다" 가 출력될 것이다.   

### if - else if - else
if a - else if b - else 는 '만약 a라면 - 아니면 b라면 -  모두 아니라면' 이라고 이해하면 된다.   
예시를 통해 이해하는 것이 가장 빠를 것이다.
```java
public class School {
    public static void main(String[] args) {
        int score = 88; /// score이 88
        char grade = ' ';   /// 변수 grade를 공백으로 초기화

        if(score >= 90) {   /// score이 90 이상이면 grade는 A
            grade = 'A';
        } else if(score >= 80) {    /// score이 80 이상이면 grade는 B
            grade 'B'
        } else if(score >= 70) {    /// score이 70 이상이면 grade는 C
            grade = 'C'
        } else {
            grade = 'D' /// 나머지의 경우 grade는 D
        }
        System.out.println("학점" + grade); score에 따른 grade가 출력
    }
}   
```    
## switch문
***
if문의 경우의 수가 많아질수록 조건문을 여러 개 써야 하기 때문에 코드가 복잡해진다.  
이럴 때 switch문을 이용하면 훨씬 보기 편할 뿐 아니라 처리 속도도 빠르게 할 수 있다.   
switch문은 조건식을 먼저 계산한 다음 그 결과와 일치하는 case문을 찾는 형식이다. 
```java
public class Week {
    public static void main(String[] args) {
        String day = "Sunday"   

        switch(day) { 
            case "Monday":  /// 조건식의 결과가 평일일 경우
            case "Tuesday":
            case "Wednesday":
            case "Thursday":
            case "Friday":
            System.out.println("오늘은 주중입니다");    /// "오늘은 주중입니다"를 출력한다.
            break;      /// 반드시 case의 끝부분에 break를 작성해야 한다.

            case "Saturday":    /// 조건식의 결과가 주말일 경우
            case "Sunday":
            System.out.println("오늘은 주말입니다!!");  /// "오늘은 주말입니다" 를 출력한다.
            break;
            
            default:    /// 조건식의 결과와 일치하는 case문이 없을 경우
            System.out.println("잘못 입력했습니다");    /// "잘못 입력했습니다" 를 출력한다.
        }
    }
}
```
   
### switch문의 제약 조건
switch문의 조건식의 결과는 정수 또는 문자열이어야 한다.   
case문의 값은 정수 상수(final ~), 문자열만 가능하며, 같은 값의 case문이 여러 개여서는 안 된다.   
다음을 보며 이해해 보자.
```java
public class Example {
    public static void main(String[] args) {
        int num;
        int result;
        final int ONE = 1;

        switch(result) {
            case '1':   /// 가능
            case ONE:   /// 가능(상수)
            case "YES": /// 가능(문자열)
            case num:   /// 불가능(변수)
            case 1.0:   /// 불가능(실수)
        }
    }
}
