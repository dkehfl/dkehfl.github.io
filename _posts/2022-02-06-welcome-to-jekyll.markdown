---
layout: post
title:  "How to use Markdown?"
description: 마크다운 문법
date:   2022-02-06 12:03:36 +0530
categories: Markdown
---
## 마크다운이란?
***

마크다운은 2004년 존 그루버와 에런 스워츠가 협업하여 개발한 마크업 언어로 HTML 등 타 마크업 언어에 비해 쉽고 간단한 것이 특징이다. github 저장소에 관한 정보를 기록하는 README 문서도 마크다운으로 작성된 것이다. 다양한 플랫폼에서 쉽고 간편하게 스타일 문서를 작성할 수 있기 때문에 널리 사용되고 있다.

## 마크다운 문법 정리
***


### 글머리

```
큰 제목
===

작은 제목
---

```

큰 제목
===
작은 제목
---


글머리의 사이즈를 좀 더 세분화할 수도 있다.

```
# Title 01
## Title 02
### Title 03
#### Title 04
##### Title 05
###### Title 06
```

# Title 01
## Title 02
### Title 03
#### Title 04
##### Title 05
###### Title 06
####### Title 07 < 여기부터는 지원하지 않는다.

### 강조 글씨체 적용

이탤릭체와 볼드체, 취소선을 적용하여 원하는 부분을 강조할 수 있다.
* 이탤릭체

```
*이탤릭체*
_이탤릭체_
```

* 볼드체

```
**볼드체**
__볼드체__
```

* 취소선

```
~~취소선~~
```

*이탤릭체*
**볼드체**
~~취소선~~

### 외부 링크

외부 링크를 인용할 때는 다음과 같이 작성한다.

```
[링크명](http://www.hyperlink.com)
[링크명](http://www.hyperlink.com "사이트 제목")
```

[송채은의 기술블로그](https://dkehfl.github.io/)

### 자동 연결

외부 링크 또는 이메일 주소를 인용할 때는 다음과 같이 작성한다.

```
외부 링크: <https://dkehfl.github.io/>
이메일 주소: <dkehfl@gmail.com>
```

외부 링크: <https://dkehfl.github.io/>
이메일 주소: <dkehfl@gmail.com>

### 블럭 인용문

각 문단의 첫 줄에 블럭인용문자 ```>``` 를 붙여서 블럭 인용문을 만들 수 있다.

```
>블럭 인용문 1
>   >블럭 인용문 2
>   >   >블럭 인용문 3
```

>블럭 인용문 1
인용문 1의 본문 . . .
>   >블럭 인용문 2
>   >   >블럭 인용문 3

### 리스트

### 순서가 있는 리스트

순서가 있는 리스트는 숫자와 점을 이용하여 정리한다. 

```
1. 일번
2. 이번
3. 삼번
```

전부 같은 숫자를 부여해도 순서가 제대로 정리된다.

```
1. 일번
1. 이번
1. 삼번
```

**어떤 번호를 부여해도 순서가 무조건 내림차순으로 정리된다.**

```
1. 일번
3. 이번
2. 삼번
```

1. 일번
3. 이번
2. 삼번

### 순서가 없는 리스트

순서가 없는 리스트는 글머리 기호 ```*```,```+```,```-``` 를 이용하여 정리한다.

```
* 일번
    + 이번
        - 삼번
* 일번
 ```

 * 일번
    + 이번
         - 삼번
* 사번

### 코드 입력하기

코드 블럭을 통해 코드를 입력하는 방법은 두 가지가 있다.
### 들여쓰기를 통해 입력하기

공백 4칸 또는 탭(Tab) 하나를 통해 들여쓰기를 하면 코드 입력이 시작되고, 들여쓰기를 하지 않을 때까지 지속된다. 이때 한줄씩 띄어 써야 코드 입력창이 적용된다.

```
본문

    코드 입력 시작
    코드 입력중 . . .

코드 입력 끝!!
```

본문

    코드 입력 시작
    코드 입력중 . . .

코드 입력 끝!!

### 코드블럭을 통해 입력하기
들여쓰기를 하지 않고 코드블럭을 통해 코드를 입력하는 방법도 두 가지가 있다. 
* ```<pre><code>{본문}</code></pre>``` 이용방식

```
<pre>
<code>
public class Hello {

	public static void main(String[] args) {
    }
}
</code>
</pre>
```

* 코드블럭코드 (```) 이용방식
코드블럭 옆에 c, java 등 프로그램을 지정할 수 있다.

<pre>
<code>
``` java
public class Hello {

	public static void main(String[] args) {
    }
}
```
</code>
</pre>

```
public class Hello {

	public static void main(String[] args) {
    }
}
```

### 줄바꿈
줄의 마지막 부분에서 스페이스바를 두번 누르거나 ```<br/>``` 을 입력한다.  
문단을 바꾸기 위해서는 엔터를 두번 누르면 된다.


### 수평선

아래 줄은 모두 수평선을 만든다. 문서를 출력할 때 페이지 나누기 용도로 많이 사용한다고 한다.

```
***
**********
- - - 
--------------------
```

***
**********
- - - 
--------------------

### 이미지 첨부

```
![이미지 이름](이미지 주소)
![이미지 이름](이미지 주소)(이동하려는 링크 주소) /// 이미지에 링크 걸기
```

github에 다운로드.jpeg라는 이미지를 업로드 후 위와 같이 입력하면

![곰돌이](http://drive.google.com/uc?export=view&id=1xBaVOMtm8u-PG0fx31pcfhu8bOeQYuup)

사진이 첨부된다.

### 테이블

```|``` 와 ```-``` 3개 이상을 이용하여 테이블을 만들 수 있다.

```
|**name**|ddsaf|test|
|:---:|:---:|:---:|
|java|mark|HTML|
|J|M|H|
|A|A|T|
```

|**name**|ddsaf|test|
|:---:|:---:|:---:|
|java|mark|HTML|
|J|M|H|
|A|A|T|


### 참고
[github](https://gist.github.com/ihoneymon/652be052a0727ad59601)
[velog](https://velog.io/@hotmosit/Markdown-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%B2%A8%EB%B6%80-%EB%B0%8F-%EC%A1%B0%EC%A0%95)
[wikipedia](https://ko.wikipedia.org/wiki/%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4)

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
