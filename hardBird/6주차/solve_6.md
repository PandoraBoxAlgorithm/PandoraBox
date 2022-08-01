❎ 다른사람의 풀이를 보았나요 ? </br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
❎ 문제를 한번 더 풀어보았나요 ? </br>

```c++

//배달
/*
N개의 마을로 이루어진 나라가 있습니다. 이 나라의 각 마을에는 1부터 N까지의 번호가 각각 하나씩 부여되어 있습니다. 각 마을은 양방향으로 통행할 수 있는 도로로 연결되어 있는데, 
서로 다른 마을 간에 이동할 때는 이 도로를 지나야 합니다. 
도로를 지날 때 걸리는 시간은 도로별로 다릅니다. 현재 1번 마을에 있는 음식점에서 각 마을로 음식 배달을 하려고 합니다. 각 마을로부터 음식 주문을 받으려고 하는데, N개의 마을 중에서 K 시간 이하로 배달이 가능한 마을에서만 주문을 받으려고 합니다. 다음은 N = 5, K = 3인 경우의 예시입니다.

위 그림에서 1번 마을에 있는 음식점은 [1, 2, 4, 5] 번 마을까지는 3 이하의 시간에 배달할 수 있습니다. 
그러나 3번 마을까지는 3시간 이내로 배달할 수 있는 경로가 없으므로 3번 마을에서는 주문을 받지 않습니다. 따라서 1번 마을에 있는 음식점이 배달 주문을 받을 수 있는 마을은 4개가 됩니다.
마을의 개수 N, 각 마을을 연결하는 도로의 정보 road, 음식 배달이 가능한 시간 K가 매개변수로 주어질 때, 음식 주문을 받을 수 있는 마을의 개수를 return 하도록 solution 함수를 완성해주세요.
*/
#include <iostream>
#include <vector>
#include <string.h>
#include <algorithm>
using namespace std;

int graph[51][51];
int INF = 10001;

int solution(int N, vector<vector<int> > road, int K) {
    int answer = 0;
    for(int i=0; i<road.size(); i++) {
        graph[road[i][0]][road[i][1]] = graph[road[i][1]][road[i][0]] = min(graph[road[i][0]][road[i][1]], road[i][2]);
    }
    for(int k=1; k<=N; k++) {
        for(int i=1; i<=N; i++) {
            for(int j=1; j<=N; j++) {
                graph[i][j] = min(graph[i][j], graph[i][k] + graph[k][j]);
            }
        }
    }
    for(int i=1; i<=N; i++) graph[i][i] = 0;
    for(int i=1; i<=N; i++) {
        if(graph[1][i] <= K) answer++;
    }
    return answer;
}
```


