# eq()에 대해 알아보자

docs : <https://javadoc.io/doc/org.mockito/mockito-core/latest/org/mockito/ArgumentMatchers.html>

Allow flexible verification or stubbing. See also AdditionalMatchers.
Mockito extends ArgumentMatchers so to get access to all matchers just import Mockito class statically.

유연한 인증 및 stubbing을 허용한다. AdditionalMatchers 또한 보자.
Mockito는 ArgumentMatcher를 확장시킴으로 모든 matchers에 접근하기 위해 단지 정적으로 Mockito를 import하면 된다.

```
//stubbing using anyInt() argument matcher
 when(mockedList.get(anyInt())).thenReturn("element");

 //following prints "element"
 System.out.println(mockedList.get(999));

 //you can also verify using argument matcher
 verify(mockedList).get(anyInt());
 ```

 Since Mockito any(Class) and anyInt family matchers perform a type check, thus they won't match null arguments. Instead use the isNull matcher.
 Mockito any(Class) and anyInt family matchers가 타입 체크를 실행하기 때문에 null arguments를 비교하지 않는다. 대신에 isNull을 사용한다.

```
 // stubbing using anyBoolean() argument matcher
 when(mock.dryRun(anyBoolean())).thenReturn("state");

 // below the stub won't match, and won't return "state"
 mock.dryRun(null);

 // either change the stub
 when(mock.dryRun(isNull())).thenReturn("state");
 mock.dryRun(null); // ok

 // or fix the code ;)
 when(mock.dryRun(anyBoolean())).thenReturn("state");
 mock.dryRun(true); // ok
```
Warning:
If you are using argument matchers, all arguments have to be provided by matchers. E.g: (example shows verification but the same applies to stubbing):
만약 너가 변수 matchers를 사용한다면, 모든 변수들은 matchers에 의해 제공되어야한다.
```

 verify(mock).someMethod(anyInt(), anyString(), eq("third argument"));
 //above is correct - eq() is also an argument matcher

 verify(mock).someMethod(anyInt(), anyString(), "third argument");
 //above is incorrect - exception will be thrown because third argument is given without argument matcher.
 ```
 
Matcher methods like anyObject(), eq() do not return matchers. Internally, they record a matcher on a stack and return a dummy value (usually null).    
This implementation is due to static type safety imposed by java compiler. The consequence is that you cannot use anyObject(), eq() methods outside of verified/stubbed method.   
anyObject(), eq()와 같은 Matcher 메소드는 matchers를 반환하지 않는다. 내부적으로 스택에서 기록하고 더미값을 반환한다. 
이러한 실행은 자바 컴파일러에의해 강요되는 정적 타입 안정성 때문이다. 결과는 verified/stubbed 메소드 밖에서는 anyObject(), eq() 메소드를 사용할 수 없다는 점이다.

---
# 알게된 점
- ArgumentMatchers는 any()와 같은 형태로 비교를 한다.
- argument matchers를 사용하면 matchers로 제공 되어져야한다 --> 이것 때문에 verfify()안에서는 일반변수(1L)가 아닌 eq()를 사용해야한다.

