✅ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
#include <string>
#include <vector>

using namespace std;

string solution(int n) {
    string answer = "";
    int arr[] = {4,1,2};
    while(n){
        answer=to_string(arr[n%3])+answer;
        if(n%3==0)
            n= n/3-1;
        else
        n/=3;

    }
    return answer;
}
```
