✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>
<br>
//피보나치 수 <br>
/* <br>
피보나치 수는 F(0) = 0, F(1) = 1일 때, 1 이상의 n에 대하여 F(n) = F(n-1) + F(n-2) 가 적용되는 수 입니다.<br>
<br><br>
예를들어<br>
<br><br>
F(2) = F(0) + F(1) = 0 + 1 = 1 <br>
F(3) = F(1) + F(2) = 1 + 1 = 2 <br>
F(4) = F(2) + F(3) = 1 + 2 = 3 <br>
F(5) = F(3) + F(4) = 2 + 3 = 5 <br>
와 같이 이어집니다.<br><br>

2 이상의 n이 입력되었을 때, n번째 피보나치 수를 1234567으로 나눈 나머지를 리턴하는 함수, solution을 완성해 주세요. <br>
<br>
*/
```java
class Solution {
    public int solution(int n) {
        int[] answer = new int[n+1];

        for(int i=0; i<=n; i++) {
            if(i == 0) answer[0] = 0;
            else if(i == 1) answer[1] = 1;
            else answer[i] = (answer[i-1] + answer[i-2])%1234567;        
            
        }
        return answer[n];
    }
}
```
