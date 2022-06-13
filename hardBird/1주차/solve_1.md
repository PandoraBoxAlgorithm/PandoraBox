✅ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
#include <string>
#include <vector>

using namespace std;

//124나라의 숫자 
/*
124 나라가 있습니다. 124 나라에서는 10진법이 아닌 다음과 같은 자신들만의 규칙으로 수를 표현합니다.

124 나라에는 자연수만 존재합니다.
124 나라에는 모든 수를 표현할 때 1, 2, 4만 사용합니다.
예를 들어서 124 나라에서 사용하는 숫자는 다음과 같이 변환됩니다.

자연수 n이 매개변수로 주어질 때, n을 124 나라에서 사용하는 숫자로 바꾼 값을 return 하도록 solution 함수를 완성해 주세요.
*/


string solution(int n) {
    string answer = "";
    int arr[] = {4,1,2}; //3을 기준으로 나눴을때 나머지가 0이면 4, 1이면 1, 2면 2이다.  
    while(n){
        answer=to_string(arr[n%3])+answer;
        if(n%3==0)
            n= n/3-1; // 3으로 나누어떨어지는 경우 -1을 해줘야 한다. result가 4의 값을 줘야하기 때문에
        else
        n/=3;

    }
    return answer;
}
```
