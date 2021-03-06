---
layout: post
title:  "Method"
date:   2022-04-09 04:03:36 +0530
categories: Java
---
## 메소드란?
***

특정 행동을 목적으로 하는 코드의 집합이다.  
필요에 따라 호출 및 동작하며 다른 언어에서는 보통 함수(funcion) 라고 부른다.

## 메소드 이용 방법
***

### 메소드 선언
```java
public static 리턴타입(자료형 또는 void) 메소드명() {
		실행할 코드
		return; // void의 경우 필요x
	}
```

### main 메소드
프로그램의 시작점 역할을 한다.  
main 메소드가 없을 경우 다른 메소드는  별도로 동작할 수 없다.

```java
public static void main(String[] args) {
}
```

### 기타 사용 예시
메소드 사용시 코드의 반복을 줄일 수 있다.
```java
public class Method1 { 
		public static void sum() {  // 메소드 정의
				int sum = 0;
				for (int i = 0; i <= 10; i++) {
						sum += i;  // 0~10 값 출력
		}
				System.out.println(sum);

public static void main(String[] args) {
		sum();  // 메소드 호출
		sum();
	}
}
```

자료형이 리턴타입으로 오는 경우도 있다.
```java
public class Method2 {
		public static int div() {
				int a = 10, b = 5;
				int result = a / b;
				int result2 = a * b; 
				return result; // 반환반환반환 ㄲㄲㄲㄲㄲ 반환값이 int가 아니면 에러
				return result2; // 얘도 에러남 메소드는 이미 윗줄에서끝났기때문
	}

public static void main(String[] args) {
		System.out.println(div()); // 메소드 호출, 반환값 출력
	}
}
```

### 메소드 매개변수
외부로부터 입력값을 받기 위해 작성한다. 메인메소드에서 메소드를 호출하고 값을 따로 입력받고 싶을때 이용한다.  
메소드의 괄호 안에 선언한다.
```java
public class Method3 {
		public static void sum(int a) { // int a 매개변수
				int sum = 0;
				for (int i = 0; i <= a; i++) {
						sum += i;
	}

		public static void sum(int a, int b) { // int a,b 매개변수, 메소드 오버로딩?
				int sum = 0;
				for (int i = a; i <= b; i++) {
						sum += i;
	}

		public static void main(String[] args) {
				sum(5); // sum(int a)
				sum(2,5); // sum(int a, int b)
	     }
     }
    }
}
```

```java
class Song {
    String title;
    String artist;
    int year;
    String country;

    public void setTitle(String title) {
        this.title = title;
    }
    public void setArtist(String artist) {
        this.artist = artist;
    }
    public void setYear(int year) {
        this.year = year;
    }
    public void setCountry(String country) {
        this.country = country;
    }
    public void getInfo() {
    }
}

public class Singsong {
    public static void main(String[] args) {
        Song S1 = new Song();
        S1.setTitle("Dancing Queen");
        S1.setArtist("ABBA");
        S1.setYear(1978);
        S1.setCountry("Sweden");
        System.out.println(S1.year + "년," + S1.country + "국적의" + S1.artist + "가 부른" + S1.title);
    }
}
```    
### 메소드 오버로딩
같은 이름의 메소드를 여러 번 재사용할 수 있다. 메소드의 괄호 안 매개변수만 다르면 가능.     
```java
class School {
    String name;		/// 메소드에서 사용할 매개변수들을 선언해준다.
    int age;
    char gender;

    void Teacher() {	/// 메소드 1
        System.out.println("선생님입니다");
    }

    void Teacher(String name) {		/// 메소드 2. 매개변수를 다르게 만들었다.
        System.out.println("저의 이름은 " + name + "이고,");
    }

    void Teacher(int age, char gender) {		/// 메소드 3. 역시나 매개변수를 다르게 만들었다.
        System.out.println(" 나이는 " + age + "살이고, 성별은 " + gender + "자 입니다.");
    }
}

public class TeacherName {
    public static void main(String[] args) {
        School CH = new School();
        CH.Teacher();		
        CH.Teacher("Cherie");
        CH.Teacher(19, '여');
    }
}
```   

