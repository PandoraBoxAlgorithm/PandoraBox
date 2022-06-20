✅ 다른사람의 풀이를 보았나요 ? <br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

``` 
//다음 큰 숫자 
/*
자연수 n이 주어졌을 때, n의 다음 큰 숫자는 다음과 같이 정의 합니다.

조건 1. n의 다음 큰 숫자는 n보다 큰 자연수 입니다.
조건 2. n의 다음 큰 숫자와 n은 2진수로 변환했을 때 1의 갯수가 같습니다.
조건 3. n의 다음 큰 숫자는 조건 1, 2를 만족하는 수 중 가장 작은 수 입니다.
예를 들어서 78(1001110)의 다음 큰 숫자는 83(1010011)입니다.

자연수 n이 매개변수로 주어질 때, n의 다음 큰 숫자를 return 하는 solution 함수를 완성해주세요.
*/
class Solution {
    public int solution(int n) {
        int answer = 0;
        //BitCount 주어진 정수에서 true bit의 개수를 찾는 함수 -> bitCount
        int nBitCnt = Integer.bitCount(n);
        
        while(true) {
          int i = ++n;
			    if(Integer.bitCount(i) == nBitCnt) {
				    answer = i; break;
			    }  
		    }
        return answer;
    }
}
```
