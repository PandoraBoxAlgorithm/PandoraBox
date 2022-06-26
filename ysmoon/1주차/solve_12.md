✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>
<br>
//N개의 최소공배수 <br>
/* <br>
두 수의 최소공배수(Least Common Multiple)란 입력된 두 수의 배수 중 공통이 되는 가장 작은 숫자를 의미합니다.<br> 
예를 들어 2와 7의 최소공배수는 14가 됩니다. <br>
정의를 확장해서, n개의 수의 최소공배수는 n 개의 수들의 배수 중 공통이 되는 가장 작은 숫자가 됩니다.<br>
n개의 숫자를 담은 배열 arr이 입력되었을 때 이 수들의 최소공배수를 반환하는 함수, solution을 완성해 주세요.<br>
<br>
*/
```java
class Solution {
    public int solution(int[] arr) {
        int answer = 0;
        answer = arr[0];
        for(int i = 1;i<arr.length;i++){
            // 두 값의 최대공약수
            int gcd = gcd(answer,arr[i]);
            //두 값의 최소공배수
            answer = answer * arr[i] / gcd;
        }
        return answer;
    }
    public int gcd(int a, int b) {
        int x = Math.max(a,b);
        int y = Math.min(a,b);
        while( x%y !=0) {
		int r=x%y;
		x=y;
		y=r;
        }
        return y;
    }
}
```
