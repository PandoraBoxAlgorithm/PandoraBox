✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java
//올바른 괄호
/*
괄호가 바르게 짝지어졌다는 것은 '(' 문자로 열렸으면 반드시 짝지어서 ')' 문자로 닫혀야 한다는 뜻입니다. 예를 들어

"()()" 또는 "(())()" 는 올바른 괄호입니다.
")()(" 또는 "(()(" 는 올바르지 않은 괄호입니다.
'(' 또는 ')' 로만 이루어진 문자열 s가 주어졌을 때, 문자열 s가 올바른 괄호이면 true를 return 하고, 올바르지 않은 괄호이면 false를 return 하는 solution 함수를 완성해 주세요.
*/
class Solution {
    boolean solution(String s) {
        boolean answer = true;

        int cnt = 0;
        for(int i=0; i<s.length(); i++) {
            if('(' == s.charAt(i)) {
                cnt++;
            }
            if(')' == s.charAt(i)) {
                cnt--;
            }
           
            if(cnt < 0 ) break;
        }
        if(cnt != 0 ) answer = false; //올바른 괄호이면 cnt = 0이 됨

        return answer;
    }
}
```
