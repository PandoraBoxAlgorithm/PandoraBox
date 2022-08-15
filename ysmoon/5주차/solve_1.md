✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java 
//다리를 지나는 트럭
/*
N개의 마을로 이루어진 나라가 있습니다. 이 나라의 각 마을에는 1부터 N까지의 번호가 각각 하나씩 부여되어 있습니다. 각 마을은 양방향으로 통행할 수 있는 도로로 연결되어 있는데, 서로 다른 마을 간에 이동할 때는 이 도로를 지나야 합니다. 도로를 지날 때 걸리는 시간은 도로별로 다릅니다. 현재 1번 마을에 있는 음식점에서 각 마을로 음식 배달을 하려고 합니다. 각 마을로부터 음식 주문을 받으려고 하는데, N개의 마을 중에서 K 시간 이하로 배달이 가능한 마을에서만 주문을 받으려고 합니다. 다음은 N = 5, K = 3인 경우의 예시입니다.

배달_1_uxun8t.png

위 그림에서 1번 마을에 있는 음식점은 [1, 2, 4, 5] 번 마을까지는 3 이하의 시간에 배달할 수 있습니다. 그러나 3번 마을까지는 3시간 이내로 배달할 수 있는 경로가 없으므로 3번 마을에서는 주문을 받지 않습니다. 따라서 1번 마을에 있는 음식점이 배달 주문을 받을 수 있는 마을은 4개가 됩니다.
마을의 개수 N, 각 마을을 연결하는 도로의 정보 road, 음식 배달이 가능한 시간 K가 매개변수로 주어질 때, 음식 주문을 받을 수 있는 마을의 개수를 return 하도록 solution 함수를 완성해주세요.
*/

public int solution(int N, int[][] road, int K) {
        int[][] map = new int[N][N];                                        //각 정점별 최단거리 배열.
        
        for (int i = 0; i < map.length; i++) {
            for (int j = 0; j < map[0].length; j++) {
                if (i == j) {                                                //i==j일땐 0;
                    map[i][j] = 0;
                    continue;
                }
                map[i][j] = 500001;                                            //K가 500000이하 자연수이므로 
            }
        }
 
        for (int i = 0; i < road.length; i++) { // road배열 적용
            if(map[road[i][0] - 1][road[i][1] - 1] < road[i][2])  continue;   //원래 있는 길이 더 적은 길이면 무시.
            map[road[i][0] - 1][road[i][1] - 1] = road[i][2];                  //양쪽으로 연결.
            map[road[i][1] - 1][road[i][0] - 1] = road[i][2];
        }
        
        for (int k = 0; k < N; k++) {                                           //플로이드 와샬 알고리즘
            for (int i = 0; i < N; i++) {
                for (int j = 0; j < N; j++) {
                    if(i == j) continue;
                    if (map[i][j] > map[i][k] + map[k][j]) {
                        map[i][j] = map[i][k] + map[k][j];
                    }
                }
            }
        }
 
        int count = 0;
 
        for (int i = 0; i < map[0].length; i++) {
            if (map[0][i] <= K) 
                count++;
        }
        
        return count;
    }

```
