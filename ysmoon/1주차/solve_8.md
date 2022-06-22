✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>
<br>
//숫자의 표현 <br>
/* <br>
길이가 같은 배열 A, B 두개가 있습니다. 각 배열은 자연수로 이루어져 있습니다.<br>
배열 A, B에서 각각 한 개의 숫자를 뽑아 두 수를 곱합니다. 이러한 과정을 배열의 길이만큼 반복하며, 두 수를 곱한 값을 누적하여 더합니다. 이때 최종적으로 누적된 값이 최소가 되도록 만드는 것이 목표입니다. (단, 각 배열에서 k번째 숫자를 뽑았다면 다음에 k번째 숫자는 다시 뽑을 수 없습니다.)
<br><br>
예를 들어 A = [1, 4, 2] , B = [5, 4, 4] 라면<br>
<br><br>
A에서 첫번째 숫자인 1, B에서 첫번째 숫자인 5를 뽑아 곱하여 더합니다. (누적된 값 : 0 + 5(1x5) = 5)<br>
A에서 두번째 숫자인 4, B에서 세번째 숫자인 4를 뽑아 곱하여 더합니다. (누적된 값 : 5 + 16(4x4) = 21)<br>
A에서 세번째 숫자인 2, B에서 두번째 숫자인 4를 뽑아 곱하여 더합니다. (누적된 값 : 21 + 8(2x4) = 29)<br>
즉, 이 경우가 최소가 되므로 29를 return 합니다.<br>
<br><br>
배열 A, B가 주어질 때 최종적으로 누적된 최솟값을 return 하는 solution 함수를 완성해 주세요.<br>
<br>
*/
```java
import java.util.Arrays;
import java.util.Collections;

class Solution
{
    public int solution(int []A, int []B)
    {
        int answer = 0;

        // 1. B 배열은 내림차순 정렬.
        Integer[] bArr = new Integer[B.length];
        
        // 2. Collections.sort()를 위해 Wrapper클래스 배열에 저장.
        for(int i = 0 ; i<bArr.length;i++)
            bArr[i] = B[i];
        
        // 3. A 배열은 오름차순 정렬.
        Arrays.sort(A);
        // 4. b 배열은 내림차순 정렬.
        Arrays.sort(bArr, Collections.reverseOrder());
        
        // 5. 최솟값을 만들기 위해 배열의 길이만큼 각 배열의 값을 곱한 뒤, 더해준다.
        for(int i = 0; i < A.length; i++){
            answer += (A[i] * bArr[i]);
        }    

        return answer;
    }
}
```
