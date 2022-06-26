✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java
//가장 큰 정사각형 찾기
/*
1와 0로 채워진 표(board)가 있습니다. 
표 1칸은 1 x 1 의 정사각형으로 이루어져 있습니다. 
표에서 1로 이루어진 가장 큰 정사각형을 찾아 넓이를 return 하는 solution 함수를 완성해 주세요. (단, 정사각형이란 축에 평행한 정사각형을 말합니다.)

예를 들어

1	2	3	4
0	1	1	1
1	1	1	1
1	1	1	1
0	0	1	0
가 있다면 가장 큰 정사각형은

1	2	3	4
0	1	1	1
1	1	1	1
1	1	1	1
0	0	1	0
가 되며 넓이는 9가 되므로 9를 반환해 주면 됩니다.
*/
class Solution
{
    public int solution(int [][]board)
    {
        int answer = 0;
        int[][] newBoard = new int[board.length+1][board[0].length+1];
        // 새로운 배열 생성
        for(int i=0; i<board.length; i++)
            for(int j=0; j<board[i].length; j++)
                newBoard[i+1][j+1] = board[i][j];
        
        int max = 0;
        
        // 만들 수 있는 정사각형 검사
        for(int i=1; i<newBoard.length; i++){
            for(int j=1; j<newBoard[i].length; j++){
                /* 2x2 사각형의 우측하단 꼭짓점을 기준으로 정사각형이 되는지 체크한다.
                 * 현재 값이 1인경우 좌←, 상↑, 좌상↖ 체크 
                 * ←, ↑, ↖ 값이 모두 1인경우 정사각형을 만들 수 있음
                */ 
                if(newBoard[i][j] == 1){
                    int left = newBoard[i-1][j];    // 좌측 값
                    int up = newBoard[i][j-1];      // 상단 값
                    int leftUp = newBoard[i-1][j-1];// 좌측상단(대각선) 값
                    int min = Math.min(left, Math.min(up, leftUp)); 
                    newBoard[i][j] = min+1;
                    max = Math.max(max, min+1);
                }
            }
        }
        answer = max * max;

        return answer;
    }
}
```
