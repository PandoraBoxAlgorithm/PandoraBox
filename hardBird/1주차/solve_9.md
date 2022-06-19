❎ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
//피보나치수 
/*
피보나치 수는 F(0) = 0, F(1) = 1일 때, 1 이상의 n에 대하여 F(n) = F(n-1) + F(n-2) 가 적용되는 수 입니다.

예를들어

F(2) = F(0) + F(1) = 0 + 1 = 1
F(3) = F(1) + F(2) = 1 + 1 = 2
F(4) = F(2) + F(3) = 1 + 2 = 3
F(5) = F(3) + F(4) = 2 + 3 = 5
와 같이 이어집니다.

2 이상의 n이 입력되었을 때, n번째 피보나치 수를 1234567으로 나눈 나머지를 리턴하는 함수, solution을 완성해 주세요.
*/
#include <string>
#include <vector>

using namespace std;

int solution(int n) {
    int answer = 0;
    int F[100001];
    F[0] = 0; F[1] = 1;
    
    for(int i=2; i<=n; i++){
        F[i] = (F[i-1] + F[i-2] )  % 1234567;
    }
    answer = F[n];
    return answer;
}
```
