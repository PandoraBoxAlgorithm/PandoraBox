✅ 다른사람의 풀이를 보았나요 ?
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용)
✅ 문제를 한번 더 풀어보았나요 ?
//숫자의 표현 <br>
/*
Finn은 요즘 수학공부에 빠져 있습니다. 수학 공부를 하던 Finn은 자연수 n을 연속한 자연수들로 표현 하는 방법이 여러개라는 사실을 알게 되었습니다. 예를들어 15는 다음과 같이 4가지로 표현 할 수 있습니다.

1 + 2 + 3 + 4 + 5 = 15
4 + 5 + 6 = 15
7 + 8 = 15
15 = 15
자연수 n이 매개변수로 주어질 때, 연속된 자연수들로 n을 표현하는 방법의 수를 return하는 solution를 완성해주세요.
*/
```java
class Solution {
    public int solution(int n) {
        int answer = 0;
        for(int i=1; i<=n; i++) {
            int sum =0;
            for(int j=i; j<=n; j++) {
                sum += j;
            
                if(sum == n) {
                    answer++;
                }
                if(sum>n) break;
            }
        }
        return answer;
    }
}
```
