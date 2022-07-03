✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java 
//가장 긴 팰린드롬
/*
앞뒤를 뒤집어도 똑같은 문자열을 팰린드롬(palindrome)이라고 합니다.
문자열 s가 주어질 때, s의 부분문자열(Substring)중 가장 긴 팰린드롬의 길이를 return 하는 solution 함수를 완성해 주세요.

예를들면, 문자열 s가 "abcdcba"이면 7을 return하고 "abacde"이면 3을 return합니다.
*/

class Solution
{
    public int solution(String s)
    {
        char[] chr = s.toCharArray();
         
        for (int i = s.length(); i > 1; i--) { // 가장 긴 문자열부터
            for (int j = 0; j + i <= s.length(); j++) {
                boolean chk = true;
                for (int k = 0; k < i/2; k++) {
                    if (chr[j + k] != chr[j + i  - k - 1]) {
                        chk = false;
                        break;
                    }
                }
                
                if (chk) return i;
            }
        }
        
        return 1;
    }
}
```
