---
layout: post
title: "Type Casting"
date: 2022-03-20 12:03:36 +0530
categories: Java
---

## 형변환이란?
***

 형변환은 double을 int로 전환하는 것처럼 어떤 변수의 데이터 타입을 전환하는 것이다. 

## 자동 형변환
***

JVM(Java Virtual Machine) 의 판단에 의해 자동적으로 형변환이 이루어지는 경우이다.  
byte(1 byte) → short(2 byte) → int(4 byte) → long(8 byte) → float(4 byte) → double(8 byte) 순으로 자동 형변환이 이루어진다.

```java
int num = 1;
long num2 = num;
```

위와 같은 경우 굳이 int형인 num을 long형으로 변환한 뒤에 num2에 할당할 필요가 없다.  
num이 자동으로 long형으로 형변환되어 num2에 할당되기 때문이다.

## 명시적(강제) 형변환
***

자바 내부에서 자동으로 진행하는 형변환이 아닌 프로그래머가 강제로 진행하는 형변환이다.

### double or float to int  
int 캐스팅 방식

```java
double num1 = 10.101010;
float num2 = 10.1010;

int num3;
num3 = (int)num1; //double을 int로 형변환
num3 = (int)num2; //float를 int로 형변환
```

### int to double, float
double, float 캐스팅 방식

```java
int num1 = 10;
	
double num2 = (double)num1; //Int -> Double
float num3 = (float)num1; //Int -> Float
```

### String to int

자바 Integar 클래스의 parseInt 함수와 valueOf 함수 이용

```java
String s_num = "10";
int i_num1 = Integer.parseInt(s_num); //String -> Int 
int i_num2 = Integer.valueOf(s_num); //String -> Int
```

### String to double, float

자바 Long, Double, Float 클래스의 parseLong함수와 valueOf 함수 이용

```java
String s_num = "10";
double d_num = Double.parseLong(s_num); //String -> Double
float f_num = Float.valueOf(s_num); //String -> Float
```

### String to long, short

자바 Long, Short 클래스의 parseLong함수와 parseShort 함수 이용

```java
String s_num = "10";
long l_num = Long.parseLong(s_num); //String -> Long
short sh_num = Short.parseShort(s_num); //String -> Short
```

### int to String

자바 String 클래스의 valueOf, toString 함수 이용

```java
int i_num = 10;
String s_num;
		
s_num = String.valueOf(i_num); //int -> String
s_num = Integer.toString(i_num); //int -> String
s_num = ""+i_num; //int -> String
```

### double, float to String

자바 String 클래스의 valueOf, toString 함수 이용

```java
float f_num = 10.10;
double d_num = 10.10;
		
String s_num;

s_num = String.valueOf(f_num); //Float -> String
s_num = Float.toString(f_num); //Float -> String
		
s_num = String.valueOf(d_num); //Double -> String
s_num = Double.toString(d_num); //Double -> String 
```






