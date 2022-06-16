❎ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
//다음큰 숫자 
/*
자연수 n이 주어졌을 때, n의 다음 큰 숫자는 다음과 같이 정의 합니다.

조건 1. n의 다음 큰 숫자는 n보다 큰 자연수 입니다.
조건 2. n의 다음 큰 숫자와 n은 2진수로 변환했을 때 1의 갯수가 같습니다.
조건 3. n의 다음 큰 숫자는 조건 1, 2를 만족하는 수 중 가장 작은 수 입니다.
예를 들어서 78(1001110)의 다음 큰 숫자는 83(1010011)입니다.

자연수 n이 매개변수로 주어질 때, n의 다음 큰 숫자를 return 하는 solution 함수를 완성해주세요.
*/

#include <string>
#include <vector>
#include <iostream>

using namespace std;

// 정수 n을 이진수로 변환
string getBinary(int n)
{
    string ret="";
    while(n>0){
        int remain = n%2;
        n/=2;
        ret = to_string(remain)+ret;
    }
    return ret;
}

// 이진수에서 1의 개수를 세기
int countOne(string &s){
    int ret=0;
    for(int i=0;i<s.length();i++){
        if(s[i]=='1')
            ret++;
    }
    return ret;
}

int solution(int n) {
    int answer = 0;
    string start = getBinary(n);
    int one = countOne(start);

    for(int i=n+1;;i++){
        string binary = getBinary(i);
        if(one==countOne(binary)){
            answer=i;
            break;
        }
    }    

    return answer;
}
```
