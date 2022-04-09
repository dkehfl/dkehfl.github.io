---
layout: post
title: "type casting"
date: 2022-03-20 12:03:36 +0530
---

 ## 형변환이란?
 ***

 형변환은 double을 int로 전환하는 것처럼 어떤 변수의 데이터 타입을 전환하는 것이다. 

 ## 자동 형변환
 ***

 JVM(Java Virtual Machine) 의 판단에 의해 자동적으로 형변환이 이루어지는 경우이다.
 byte(1 byte) → short(2 byte) → int(4 byte) → long(8 byte) → float(4 byte) → double(8 byte) 순으로 자동 형변환이 이루어진다.

 '''
int num = 1;
long num2 = num;
 '''

 위와 같은 경우 굳이 int형인 num을 long형으로 변환한 뒤에 num2에 할당할 필요가 없다.
 num이 자동으로 long형으로 형변환되어 num2에 할당되기 때문이다.

## 명시적(강제) 형변환
***

* double or float to int
 (int) 캐스팅 방식
'''
double num1 = 10.101010;
float num2 = 10.1010;

int num3;
num3 = (int)num1; //double을 int로 형변환
num3 = (int)num2; //float를 int로 형변환
'''







