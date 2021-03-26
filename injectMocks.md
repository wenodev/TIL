# @InjectMocks

## JavaDoc
- Mark a field on which injection should be performed.
- Allows shorthand mock and spy injection.
- Minimizes repetitive mock and spy injection.
- 삽입이 수행되어야할 필드에 표시한다.
- mock과 spy 삽입의 짧은표현을 허용한다.
- mock과 spy 삽입의 중복을 최소화 한다.

## Code
Product라는 entity의 Service Test코드를 작성한다고 가정한다.

변경전코드
```java
private ProductRepository productRepository = mock(ProductRepository.class);
private ProductService productService = new ProductService(productRepository);
```

변경후 코드
```java
@Mock
private ProductRepository productRepository;
@InjectMocks
private ProductService productService;
```

## 결론
- 첫번째 방법이 명시적이라 학습하는데 좋다고 생각한다.
- 변경 후 코드를 사용하려고 하면 mock 초기화 코드를 꼭 작성해야한다.
```java
@BeforeEach
public void setUp(){
    MockitoAnnotations.initMocks(this);    
}
```
- 초기화 코드를 사용하는것보다 하나씩 주입받는 코드를 더 선호한다.
