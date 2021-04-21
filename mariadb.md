# Mariadb 예약어 오류

## mariadb 예약어
[제타위키 보러가기](https://zetawiki.com/wiki/MySQL_%EC%98%88%EC%95%BD%EC%96%B4)

## 예약어를 Column명으로 작성하게 되면 아래와 같은 오류를 확인할 수 있다.
```
org.hibernate.tool.schema.spi.CommandAcceptanceException: Error executing DDL
```

```
Caused by: java.sql.SQLSyntaxErrorException: (conn=399) You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'limit integer' at line 1
```

```
Caused by: java.sql.SQLException: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'limit integer' at line 1
```

```
java thread: restartedMain
```

## 발생한 이유
- 학습 부족이다. 
- SQL문도 언어이기 때문에 예약어가 존재한다.
- JPA를 통해 컬럼을 생성하더라고 SQL문이 실행된다.
