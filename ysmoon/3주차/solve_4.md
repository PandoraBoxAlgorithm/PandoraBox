✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java 
// 도둑질
/*

도둑이 어느 마을을 털 계획을 하고 있습니다. 이 마을의 모든 집들은 아래 그림과 같이 동그랗게 배치되어 있습니다.

image.png

각 집들은 서로 인접한 집들과 방범장치가 연결되어 있기 때문에 인접한 두 집을 털면 경보가 울립니다.

각 집에 있는 돈이 담긴 배열 money가 주어질 때, 도둑이 훔칠 수 있는 돈의 최댓값을 return 하도록 solution 함수를 작성하세요.

*/

// 도둑질
class Solution {
    public static int solution(int[] money) {
        int answer = 0;
        int len = money.length;
        // 처음 집 훔치고 마지막집을 훔치지 못하는 case와 , 그렇지 않은 케이스
        int[] case1 = new int[len];
        int[] case2 = new int[len];
        // case1은 Dp를 위해 0,1번 값을 모두 처음집값으로 셋팅
        case1[0] = money[0];
        case1[1] = money[0];
        //case2는 처음집을 안훔치므로 0값으로 셋팅
        case2[0] = 0;
        case2[1] = money[1];
        // DP - -2번째에 지금값을 더한것과 -1번째 집까지 훔친 경우를 비교하면서 어느집을 훔치는게 제일 큰지 합계를 저장
        for(int i=2; i<len; i++){
            case1[i] = Math.max(case1[i-2] + money[i], case1[i-1]);
            case2[i] = Math.max(case2[i-2] + money[i], case2[i-1]);
        }
        // 두 경우중 더 많이 훔치는 경우를 반환 
        //case1은 첫집을 턴경우이므로 마지막집은 접근하지않는다, len-2번째 인덱스와 비교
        answer = Math.max(case1[len-2], case2[len-1]);

        return answer;
    }
}


```
