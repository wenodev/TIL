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
```
private ProductRepository productRepository = mock(ProductRepository.class);
private ProductService productService = new ProductService(productRepository);
```

변경후 코드
```
@Mock
private ProductRepository productRepository;
@InjectMocks
private ProductService productService;
```

## 결론
- 첫번째 방법이 명시적이라 학습하는데 좋다고 생각한다.
- 두가지 방법다 수련해보고 실무에서는 두번째 방법을 바로 사용하는게 좋을것같다.
