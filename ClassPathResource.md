# ClassPathResource 란?

## 작성동기
- 엑셀파일을 테스트하려던 중 파일을 읽어와야하는 상황이 생겼다.
- 편히한 방법을 검색하던 중 알게되었고 정리 필요성을 느꼈다.
---
## 정의
- Resource implementation for class path resources. Uses either a given ClassLoader or a given Class for loading resources.
- 클래스 경로 리소스에 대한 리소스 구현. 자원을 로드하기 위해 주어진 ClassLoader 또는 주어진 Class를 사용한다. (구글번역)
- [docs보러가기](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/core/io/ClassPathResource.html)
---
## 예시
### 예시코드1
```java
ClassPathResource file = new ClassPathResoutce("파일명");
```
springboot에서는 resource 하위의 파일들을 불러 온다.
### 예시코드2
```java
 @Test
    void testGetFile() throws IOException {
        assertThat(file.getFilename()).isEqualTo("spring-excel-upload-product.xlsx");
    }
```
getFileName이란 메소드를 사용해서 확인할 수 있다.
