❎ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++

//단체사진 찍기 
/*
가을을 맞아 카카오프렌즈는 단체로 소풍을 떠났다. 즐거운 시간을 보내고 마지막에 단체사진을 찍기 위해 카메라 앞에 일렬로 나란히 섰다.
그런데 각자가 원하는 배치가 모두 달라 어떤 순서로 설지 정하는데 시간이 오래 걸렸다.
네오는 프로도와 나란히 서기를 원했고, 튜브가 뿜은 불을 맞은 적이 있던 라이언은 튜브에게서 적어도 세 칸 이상 떨어져서 서기를 원했다.
사진을 찍고 나서 돌아오는 길에, 무지는 모두가 원하는 조건을 만족하면서도 다르게 서는 방법이 있지 않았을까 생각해보게 되었다.
각 프렌즈가 원하는 조건을 입력으로 받았을 때 모든 조건을 만족할 수 있도록 서는 경우의 수를 계산하는 프로그램을 작성해보자.
*/

#include <string>
#include <vector>
#include <algorithm>
#include <iostream>

using namespace std;

int solution(int n, vector<string> data) {
    int answer = 0;
    vector <char> v = { 'A','C','F','J','M','N','R','T' };
    do {
        int index1 = 0;//첫번째 문자 위치 저장
        int index2 = 0;//두번째 문자 위치 저장
        for (int i = 0; i < n; i++) { //data 문자열 비교
            for (int j = 0; j < 8; j++) {
                if (data[i][0] == v[j])index1 = j;
                else if (data[i][2] == v[j])index2 = j;
            }
            char compare = data[i][3]; // '=' or '>' or '<' 저장
            int number = data[i][4] - '0'; //간격차이     
            if (compare == '='&& abs(index1 - index2) != number + 1) break;       
            else if (compare == '>'&& abs(index1 - index2) <= number + 1) break;            
            else if (compare == '<'&& abs(index1 - index2) >= number + 1) break;            
            if (i == n - 1)answer++;
        }
    } while (next_permutation(v.begin(), v.end()));//계속해서 정렬
    return answer;
}
```
