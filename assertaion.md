# Spring의 assertion

## 글 작성 이유
- Spring Security의 HttpStatusEntryPoint라는 클래스를 보더 중 "import org.springframework.util.Assert;" 이런 코드를 확인했고 궁금증이 생겼다.
- JAVA 생태계에서 알게된 assertion을 정리 할 필요성을 느꼈다.

## Assertion의 종류
1. Junit5의 Assertions
- Assertions라는 클래스가 존재한다. 주로 아래처럼 import를 하게 된다.
```java
import static org.junit.jupiter.api.Assertions.assertEquals;
```
- assertEquals, assertNotNull와 같은 형태의 메소드를 가지고 있다.
- [Junit 보러가기](https://junit.org/junit5/docs/current/user-guide/#overview)
---
2. AssertJ의 Assertion
- Assertions라는 클래스가 존재한다. 주로 아래처럼 import를 하게 된다.
```java
import static org.assertj.core.api.Assertions.assertThat;
```
- [AssertJ 보러가기] (https://assertj.github.io/doc/)
---
3. Java의 assert
- 문법
```java
// x와 y이가 같지 않다면 "not same"이라는 메세지와 함께 AssertionError 발생한다.
assert x != y :

// assertionError 예시
java.lang.AssertionError: "not same"
```
- 예제 1과 예제 2는 동일한 결과가 발생합니다.

예제1)
```java
Integer number1 = 3;
assert number1 < 1  : "1보다 큰 값이 필요합니다.";
```
예제2)
```java
Integer number2 = 3;
if (number2 > 1){
  throw new AssertionError("1보다 큰 값이 필요합니다.");
}
```
- [docs 보러가기](https://docs.oracle.com/javase/7/docs/technotes/guides/language/assert.html)
---
4. Spring의 Assert
- Assert라는 클래스가 존재하고 주로 아래처럼 import를 하게 된다.
```java
import org.springframework.util.Assert;
```
- [docs 보러가기](https://github.com/wenodev/TIL/new/master)
