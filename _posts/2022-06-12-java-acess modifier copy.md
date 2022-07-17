---
layout: post
title:  "Acess Modifier"
date:   2022-06-12 10:01:36 +0530
categories: Java
---
## 접근 제한자
***
접근 제한자는 외부에서 특정 멤버 또는 클래스에 접근하지 못하도록 제한한다.   
접근 제한자는 클래스, 멤버변수, 메소드, 생성자에서 사용할 수 있다.

### 접근 제한자를 사용하는 이유
비밀번호와 같은 클래스 내부 데이터를 보호하기 위해서이다.   외부에서 이 데이터를 함부로 변경하지 못하도록 하기 위해서는 접근을 제한할 필요가 있다. 이를 데이터 감추기(data hiding) 라고 한다.   
또 다른 이유로는 클래스 내에서만 사용되는 임시 멤버변수나 메소드 등을 클래스 내부에 감추기 위함이다. 간단히 말해 외부에서 접근할 필요가 없는 멤버들을 감춰 복잡성을 줄이는 것이다.

## 접근 제한자의 종류
***
**private** : 같은 **클래스** 내에서만 접근 가능   
**(default)** : 같은 **패키지** 내에서만 접근 가능
**protected** : 같은 **패키지**, 다른 패키지의 **자손 클래스**에서만 접근 가능   
**public** : **모든 패키지**에서 접근 가능    
정리하면 다음과 같다.   
```
접근제한없음   같은 패키지+자손   같은 패키지   같은 클래스
  public   >    protected    > (default)  >  private
  ```
    
|**제어자**|같은 클래스|같은 패키지|자손 클래스|전체|
|:---:|:---:|:---:|:---:|:---:|
|**public**|O|O|O|O|
|**protected**|O|O|O|X|
|**(default)**|O|O|X|X|
|**private**|O|X|X|X|   
    
### 접근 제한자 활용하기
클래스 Fruit가 다음과 같이 정의되어 있으면 멤버변수에 직접 접근이 가능하다.

```java
public class Fruit (
    public String color;
    public int price;
)

Fruit apple = new Fruit();
apple.price = 1000;     /// 멤버변수에 직접 접근
```

멤버변수를 private나 protected로 제한하면 간접적인 접근만 가능하다.

```java
public class Fruit {
    private String color;
    private int price;

    public String getColor() {
        return this.color;
        }
}

Fruit apple = new Fruit();
apple.get
```