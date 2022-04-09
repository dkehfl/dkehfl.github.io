---
layout: post
title: "variable"
date: 2022-03-06 12:03:36 +0530
---

## 변수(variable)
***

변수는 특정 값을 저장하는 메모리 공간이다.  
정수형(int), 실수형(float, double), 문자(char) 및 문자열(String) 등 여러가지 형식이 존재한다.


### 변수에 값 대입하기

```java
int a; // 자료형이 정수인 변수 a 선언
String b; //자료형이 문자열인 변수 b 선언

a = 1; // 변수 a에 1을 할당
b = "Hello" // 변수인 b에  "Hello" 할당
```

변수에 값 대입시에는 = 기호를 사용한다.  
int에 문자열을 대입하거나 String에 정수를 대입하는 경우에는 당연히 에러가 뜬다.

### 자주 쓰이는 자료형 정리

* ### 숫자

**int** : 정수

```
java
int a;
a = 2;
```

**long** : 정수. int보다 더 큰 수를 할당할 필요가 있을 때 사용한다.

```java
long b;
b = 25483589237589327589327587503275873450734895723857;
```

**float** : 실수. 자바에서는 double이 디폴트이므로 숫자 뒤에 접미사 F를 붙여야 한다.

```java
float p;
p = 3.141592F;
```

**double** : 실수. 표현할 수 있는 숫자 범위가 float보다 크다.

```java
double c;
c = 3.14;
```

* ### 연산자

**숫자연산** : '''+''', '''-''', '''*''', '''/''' 로 사칙연산을 할 수 있다.

```java
men = 12
women = 6
"men + women" = men + women
"men women" = men women
"men * women" = men * women
"men / women" = men / women
```

**증감연산** : '''++''', '''--''' 를 사용한다. 얘네를 증감연산자라고 한다.

```java
int i = 0;
int j= 10;

i++; 
j--;

System.out.println(i);
System.out.println(j);
```

순서대로 1, 9가 출력된다. 각각 1씩 증가, 감소한 것을 알 수 있다.

```java
int i = 0;
System.out.println(i++);
```

하지만 위를 실행할 경우에는 숫자가 증가하지 않고 0이 출력된다.  해당 코드가 실행되는 순간에는 변경되지 않고 실행 후에 숫자가 증가, 감소하기 때문이다. 코드가 실행되어 i가 1이 출력되도록 하기 위해서는 

```java
int i = 0;
System.out.println(++i);
```

위와 같이 입력해주면 된다.

**%.nf** : 소수점 아래 n번째 자리까지 반올림해준다. 

```java
System.out.printf("%.2f",1.1234567); // 소수점 아래 첫번째 자리까지 반올림하여 출력
```

1.12가 출력된다.

* ###  문자

**char** : 문자 한 개에 대한 자료값을 가지는 변수이다. 아스키코드나 유니코드로도 표현이 가능하다.

```java
char d;
d = 'r'
```

**String** : 한 개 이상의 문자. 문자열

```java
String e;
e = "Hello";
String a = "Thanks";
```

위가 리터럴 표기지만, 다음과 같이 표현할 수도 있다.

```java
String a = new String(Happy java);

String b = new String("a");

String c = new String("123");
```

참고로 원시 자료형(primitive)인 int, long, double, float, boolean, char 등은 리터럴 표기만 가능하다. String은 원시 자료형이 아니지만, 특별히 리터럴 표기가 가능한 경우이다.

**equals**

```java
String a = "hello";

String b = "java";

System.out.println(a.equals(b)); // 문자열 a와 b가 같은지를 True 또는 False로 출력
```

문자열의 값을 비교할 때는 ==이 아닌 equals만을 사용한다.  a는 b와 같지 않으므로 equals 메소드 호출 시 false를 리턴한다.

**indexOf** : 문자열에서 특정 문자가 시작되는 위치를 리턴한다.

```java
String a = "Hello java";

System.out.println(a.indexOf("java")); // "java" 가 실행되는 위치를 숫자로 리턴
```

문자 "java"는 문자열의 일곱 번째에서 실행되므로 6이 리턴된다. 문자열을 셀 때 0부터 시작하기 때문이다.

**replaceAll** : 문자열 중 특정 문자열을 다른 문자열로 대체한다.

```java
String a = "Hello java";

System.out.println(a.replaceAll("java","World")); // java를 World로 대체
```

java가 World로 대체된다.

**subsctring** : 문자열 중 특정 문자열을 뽑아낸다.

```java
String a = "Hello java";

System.out.println(a.substring(0,4)); // 첫번째부터 네번째 문자까지 출력
```

"Hell" 이 출력된다.


**StringBuffer** : 문자열을 추가하거나 변경 시에 사용한다.

```java
StringBuffer sb = new StringBuffer();  // StringBuffer 객체 sb 생성
sb.append("hello");
sb.append(" ");
sb.append("jump to java");
String result = sb.toString();
System.out.println(result);
```

* ### 기타

**boolean** : 참(true) 혹은 거짓(false) 의 값을 가지는 변수이다.

```java
int base = 180;
int height = 185;
boolean isTall = height > base;
```

**List** : 배열(Array)와 유사. 배열과 달리 값을 담을 수 있는 범위가 정해져 있지 않다.



**Map** : 대응 관계 표현. 딕셔너리와 유사하게 key와 value가 한 쌍을 이룬다.
