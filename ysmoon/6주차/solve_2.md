❎ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java 
//N개의 최소공배수
/*
두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다. 
예를 들어 2와 7의 최소공배수는 14가 됩니다. 정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다. 
n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요.

-- 최소공배수 공식 : 두 수의 곱 / 최대공약수
*/
class Solution {
    public int solution(int[] arr) {
        int answer = 0;
        answer = arr[0];
        for(int i = 1;i<arr.length;i++){
            int gcd = gcd(answer,arr[i]);
            answer = answer * arr[i] / gcd;
        }
        return answer;
    }
    public int gcd(int a, int b) {
        if(b == 0) return a;
        return gcd(b, a % b);
    }
}
```
