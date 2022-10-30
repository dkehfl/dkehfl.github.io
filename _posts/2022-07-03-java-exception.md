---
layout: post
title:  "Exception"
date:   2022-07-03 10:44:36 +0530
categories: Java
---
본격적으로 들어가기 전에 오류와 예외에 대해 제대로 알고 있는 것이 좋다.
## 오류? 예외?
***
오류(error)는 메모리 부족이나 운영체제의 문제 등 환경의 문제로 인해 발생하는 것이고, 예외(exception)는 개발자가 파일이 있다고 가정하고 코드를 작성했는데 파일이 없거나 잘못된 배열값을 입력하였을 때 등 개발자가 작성한 코드가 의도와 다른 상황에 마주했을 때 발생하는 것이다. 대충 말하면 오류는 컴퓨터 탓, 예외는 니 탓이다.   
<<<<<<< HEAD
부모 클래스는 둘다 Throwable이다. 자세한 건 다음을 참고하도록 하자.    

![스샷](http://drive.google.com/uc?export=view&id=1JFu2ljupPRg4Abw9GikUcaWEH6uCDJ04)
     

=======
부모 클래스는 둘다 Throwable이다. 자세한 건 다음을 참고하도록 하자.
![스샷](http://drive.google.com/uc?export=view&id=1JFu2ljupPRg4Abw9GikUcaWEH6uCDJ04)
>>>>>>> e2751a6804e42be98285a1a3a38144d2c6bc3125
## Compile-time-error 와 runtime error
***
에러는 컴파일 에러와 런타임 에러로 구분할 수 있다.   
컴파일 에러는 말 그대로 컴파일 도중에 발생하는 에러이고 런타임 에러는 컴파일 과정에서는 문제가 없었지만 실행 도중 발생한 에러를 가리킨다.

<<<<<<< HEAD
## 예외 처리
=======
## 예외 처리    
>>>>>>> e2751a6804e42be98285a1a3a38144d2c6bc3125
***
간단히 말하면 예외가 발생하였을 때를 대비하여 처신을 하는 것이다. 예외 때문에 프로그램이 안 돌아가면 꼴받으니까 . . .   
예외는 ```try```, ```catch```, ```finally```, ```throw```, ```throws``` 등의 코드를 이용하여 처리한다.   
본격적으로 들어가기 전에 간단히 정의해 보자.   
**try** : 예외가 발생하지 않을 경우 일단 실행하는 문장   
**catch** : 예외가 발생한 경우 try를 제끼고 실행할 문장   
**finally** : 예외 발생 여부에 관계없이 실행하는 문장   
**throw** : 예외를 발생시킨다.
**throws** : 예외를 메소드에서 처리하지 않고 호출되었을 때(main) 처리하겠다는 뜻   

### try - catch - finally
우선 try문 안의 코드가 실행되고, try문에서 예외가 발생했다면 try는 제끼고 catch문이 실행된다. finally문 안의 코드는 예외 여부에 상관없이 무조건 실행된다.

```java
public class Exception01 {
    String a;     // a에 아무 값도 들어가지 않은 상태
    public String getA() {
        return a;
    }
    public static void main(String[] args) {
        Exception01 test = new Exception01();

        try {     // try문 먼저 실행됨
            if (test.getA().equals("tester")) {
                System.out.println("hello");      // a가 null이므로 NPE가 뜬다
            }
        } catch(NullPointerException e) {     // NPE가 뜨면 실행
            System.out.println("null");
        }
    }
}
```
위를 실행하면 다음과 같은 결과가 나온다. 예외 처리를 해 주었기 때문에 코드가 정상적으로 실행된 것을 볼 수 있다.
```
null

Process finished with exit code 0
```   

여기에 finally를 추가해 보자.
```java
public class Exception01 {
    String a;
    public String getA() {
        return a;
    }
    public static void main(String[] args) {
        Exception01 test = new Exception01();

        try {
            if (test.getA().equals("tester")) {
                System.out.println("hello");
            }
        } catch(NullPointerException e) {
            System.out.println("null");
        }
    } finally {
            System.out.println("마침내!");      // 무조건 실행
        }
}
```
위를 실행하면 다음과 같은 결과가 나온다. finally 속 코드는 무조건 실행된다!
```
null
마침내!

Process finished with exit code 0
```
### 다중 try - catch
처음으로 실행되는 Exception 외에는 실행되지 않는다.
```java
public class Exception02 {
    public static void main(String[] args) {
        String a = null;
        int[] scores = {1,2,3};
        try {
            System.out.println(a.length());
            System.out.println(scores[3]);
        } catch(ArithmeticException e){
            System.out.println("계산 잘못됨");
        } catch (NullPointerException e) {
            System.out.println("문자열 잘못됨");
        } catch(Exception e){
            System.out.println("잘못됨");
        }
    }
}
```
위를 실행하면 다음과 같은 결과가 나온다. 세번째 catch문은 실행되지 않고 끝난 것을 알 수 있다.
```
문자열 잘못됨

Process finished with exit code 0
```
### multi catch
멀티 catch문을 이용하면 여러 종류의 예외를 한번에 처리할 수 있다. catch문을 여러 개 만드는 것보다 가성비가 좋다.   
or을 뜻하는 기호인 ```|``` 를 이용하면 된다.
```java
try {

} catch(ArrayIndexOutOfBoundsException | NullPointerException | NumberFormatException e) {
}     // 세가지 예외를 동시에 처리!

```
### throws
말 그대로 예외를 던져 버린다. 떠넘긴다는 뜻이다.   
현재 메소드에서 굳이 처리하지 않고 일단 떠넘긴 후 메인에서 호출받으면 그때 처리한다.   
어떤 예외가 발생하는지 예상하고 싶을 때, 굳이 try - catch를 쓰면서까지 예외 처리까지 할 필요가 없을 때 사용한다.
```java
public class Exception03 {
    String pw = "";     // 비밀번호를 담을 변수

    public void setPw(String pw) throws IOException {     // IOException이 발생할 것을 예상
        if (pw.length() < 10) {
            throw new IOException("비밀번호가 너무 짧습니다.");
        }
    }
}
```
<<<<<<< HEAD
비밀번호 자릿수가 10보다 짧을 경우에 예외를 발생시킨다.


### 사용자 정의 예외
말 그대로 사용자가 직접 정의하는 예외이다. checked와 unchecked 모두 만들 수 있다. 전자는 exception을 상속하고 후자는 runtimeexception을 상속하면 된다. 상속받은 부모 클래스로 생성자를 만들면 사용자 정의 예외를 이용할 수 있다.

```java
class MyCheckedException extends Exception{     // 상속

    public MyException(String message) {    // 생성자
        super(message);
    }
}

public class CheckAndUnCheck {
    public static void main(String[] args) {
        try {
            throw new MyCheckedException("커스텀한 예외입니다.");
        } catch (MyCheckedException e) {
            e.printStackTrace();
        }
    }
}
```
왜안뜨지..

=======
>>>>>>> e2751a6804e42be98285a1a3a38144d2c6bc3125






