❎ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
//숫자의표현 
/*
문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 "(최소값) (최대값)"형태의 문자열을 반환하는 함수, solution을 완성하세요.
예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고, "-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.
*/

#include <string>
#include <vector>
#include <iostream>
#include <algorithm>

using namespace std;

string solution(string s) {
    string answer = "";
    vector<int> temp ;
    string temp2 ;
    for(int i=0;i<s.length();i++) {
        if(s[i]==' ') {
            temp.push_back(atoi(temp2.c_str()));
            temp2.clear();
        }
        else {
            temp2 = temp2+s[i];
        }
    }
    temp.push_back(atoi(temp2.c_str()));
	sort(temp.begin(), temp.end(), greater<int>());
	answer += to_string(temp.back()) + " " +to_string(temp.front());
	return answer;

}
```
