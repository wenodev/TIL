# FK 생성시 발생하는 오류

## 작성 동기
- JPA를 통해 연관관계( ex) Many to One )를 추가하다보면 FK가 생성된다.
- 이 때 아래와 같은 코드를 발견했다.
```
errno: 150 "Foreign key constraint is incorrectly formed"
```

## 발생이유
- 두 테이블의 PK 칼럼의 Charset이 동일하지 않았다.

## 알게된 점
- FK를 추가할때는 두 테이블의 Charset과 두 테이블의 PK Charset이 동일해야 한다.
