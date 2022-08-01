❎ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
#include <string>
#include <vector>
#include <algorithm>

using namespace std;

int gcd(int x, int y) { return x % y == 0 ? y : gcd(y, x % y); }
int lcm(int x, int y) { return x * y / gcd(x, y); }
int solution(vector<int> arr) {
    int answer = arr[0];
    for (int i = 1; i < arr.size(); i++)
        answer = lcm(answer, arr[i]);
    return answer;
}
```
