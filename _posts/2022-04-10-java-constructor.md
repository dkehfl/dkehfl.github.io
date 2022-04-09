---
layout: post
title:  "constructor"
date:   2022-04-10 04:03:36 +0530
---

## 생성자란 무엇일까 ...
***

new 연산자를 통해서 인스턴스를 생성할 때 반드시 호출이 되고 제일 먼저 실행되는 일종의 **메소드**  
인스턴스 변수를 원하는 값으로 초기화하는 역할  
자바의 모든 클래스에 하나 이상의 생성자가 정의되어야 함(기본 생성자 제공)  
클래스명과 생성자명이 같아야 함  
리턴값이 없음 → 원래는 void를 적어야 하지만 생략함  

## 생성자 작성하기
***
### 기본생성자 정의
```java
public class Test02 {
	public Test02() { // 생성자 직접 정의
		System.out.println("생성자 호출");
	}

	public static void main(String[] args) {
			Test02 a = new Test02(); // 인스턴스 생성, 생성자 호출
	}
}
```

### 매개변수를 작성하는 경우
생성자의 괄호 안에 매개변수를 가질 수 있음

```java
public class Fruit {
	public Fruit(String fruitName, String fruitColor, int fruitPrice) {
		name = fruitName;
		color = fruitColor;
		price = fruitPrice;

		System.out.println("과일의 이름은" + name);
		System.out.println("과일의 색은" + color);
		System.out.println("과일의 가격은" + price);
	}

		public static void main(String[] args) {
			Fruit apple = new Fruit("사과","빨강",1000);
			Fruit grape = new Fruit("포도","보라",3000);
	}	
}
```

### 인스턴스의 초기화
생성자 차원에서 인스턴스를 초기화하는 방법이다.  
초기화 관련해서는 다른 포스트를 통해 다룰 생각이다. 아마도??

```



		