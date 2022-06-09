# H1  문서 제목

'# 또는 H1' 으로 사용
  
</br>

## H2 문서 부제목

'## 또는 H2'로 사용

</br>

### H3
#### H4
##### H5
###### H6

------

</br>

 > 블럭 구분
 > '>' 으로 당겨서 사용 가능
 >> 여러 개도 가능
 >>

-----

</br>

이 안에 다른 마크다운 포함할 수 있음.

순서 있는 목록

 1.
 2.
 3.

순서 없는 목록
 * 
 +
 -

 → 혼용 가능


코드 표기

4개 공백 or Tab으로 들여쓰기 하면 들여쓰지 않은 행 나올 때까지 코드 블록으로 변환 됨.

    이런 식으로
    가능하다
    적당히 끊으면 됨.


코드 블록

- 코드블럭코드("```") 을 이용하는 방법

```

```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```

```

```
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}

```

**깃헙**에서는 코드블럭코드("```") 시작점에 사용하는 언어를 선언하여 [문법강조(Syntax highlighting)](https://docs.github.com/en/github/writing-on-github/creating-and-highlighting-code-blocks#syntax-highlighting)이 가능하다.

```

```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```

```

```java
public class BootSpringBootApplication {
  public static void main(String[] args) {
    System.out.println("Hello, Honeymon");
  }
}
```

링크

[링크 키워드][ID]

[ID]: URL “마우스 올리면 뜨는 텍스트”

강조

 *강조할 문장 *

**강조할 문장 **

이미지 넣기

![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg “마우스 올리면 뜨는 텍스트”)

사이즈 조절은 

<img width="" height=""></img>

ex) <img src="/path/to/img.jpg" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="RubberDuck"></img><br/>

줄바꿈

문장 끝에서 띄어쓰기 3칸 이상하면 줄 바뀜
