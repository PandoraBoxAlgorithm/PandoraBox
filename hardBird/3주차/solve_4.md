✅ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++

//도둑질
/*
도둑이 어느 마을을 털 계획을 하고 있습니다. 이 마을의 모든 집들은 아래 그림과 같이 동그랗게 배치되어 있습니다.

각 집들은 서로 인접한 집들과 방범장치가 연결되어 있기 때문에 인접한 두 집을 털면 경보가 울립니다.

각 집에 있는 돈이 담긴 배열 money가 주어질 때, 도둑이 훔칠 수 있는 돈의 최댓값을 return 하도록 solution 함수를 작성하세요.
*/
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

int D1[1000001] ; //첫번째집 털기 
int D2[1000001] ; //두번째집 털기
int solution(vector<int> money) {
    int answer = 0;
    int mSize = money.size();
    
    D1[0] = money[0]; 
    D1[1] = max(money[1],money[0]);
    
    D2[0] = 0;
    D2[1] = money[1];
    
    for(int i=2; i< mSize-1;i++) D1[i] = max(D1[i-2] + money[i], D1[i-1]);
    for(int i=2; i< mSize;i++) D2[i] = max(D2[i-2] + money[i], D2[i-1]);

    answer = max(D1[mSize-2], D2[mSize-1]);
    return answer;
}
```
