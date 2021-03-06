# isBlank()와 isEmpty()

데이터를 받아올때 공백인지 null인지 확인해야 할 때가 있다.
공백일때 주로 isEmpty()를 사용했었는데 isBlank에 대해 알게되어 정리를 하게 되었다.

목표
- 각 메소드 동작하는 원리에 대해 이해한다.
- 언제 어떤 메소드를 사용해야 하는지 이해한다.

# 1. isBlank()
## 정의
### 스트링이 비어있거나 오직 공백이 존재할때만 true이고 그렇지 않으면 false이다.
https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html#isBlank()
```
public boolean isBlank()
Returns true if the string is empty or contains only white space codepoints, otherwise false.
Returns:
true if the string is empty or contains only white space codepoints, otherwise false
Since:
11
See Also:
Character.isWhitespace(int)
```

여기서 공백(white space)이란
###  
https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Character.html#isWhitespace(int)
```
public static boolean isWhitespace​(int codePoint)
Determines if the specified character (Unicode code point) is white space according to Java. A character is a Java whitespace character if and only if it satisfies one of the following criteria:
It is a Unicode space character (SPACE_SEPARATOR, LINE_SEPARATOR, or PARAGRAPH_SEPARATOR) but is not also a non-breaking space ('\u00A0', '\u2007', '\u202F').
It is '\t', U+0009 HORIZONTAL TABULATION.
It is '\n', U+000A LINE FEED.
It is '\u000B', U+000B VERTICAL TABULATION.
It is '\f', U+000C FORM FEED.
It is '\r', U+000D CARRIAGE RETURN.
It is '\u001C', U+001C FILE SEPARATOR.
It is '\u001D', U+001D GROUP SEPARATOR.
It is '\u001E', U+001E RECORD SEPARATOR.
It is '\u001F', U+001F UNIT SEPARATOR.
Parameters:
codePoint - the character (Unicode code point) to be tested.
Returns:
true if the character is a Java whitespace character; false otherwise.
Since:
1.5
See Also:
isSpaceChar(int)
```

