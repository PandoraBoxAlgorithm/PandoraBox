✅ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
//2*n 타일링
/*
앞뒤를 뒤집어도 똑같은 문자열을 팰린드롬(palindrome)이라고 합니다.
문자열 s가 주어질 때, s의 부분문자열(Substring)중 가장 긴 팰린드롬의 길이를 return 하는 solution 함수를 완성해 주세요.

예를들면, 문자열 s가 "abcdcba"이면 7을 return하고 "abacde"이면 3을 return합니다.
*/
#include <iostream>
#include <string>

using namespace std;
int solution(string s)
{
    int size = s.size(), mid = 0;
    
    if(size <= 1)
        return size;
    
    while(size > 1)
    {
        for(int i = 0; i <= s.size() - size; i++)
        {
            bool check = true;
            mid = size / 2;
            
            if(size % 2) // odd
            {
                for(int left = 0; left < mid; left++)
                {
                    if(s[left + i] != s[i + mid * 2 - left])
                    {
                        check = false;
                        break;
                    }
                }
            }
            else
            {
                for(int left = 0; left < mid; left++)
                {
                    if(s[left + i] != s[i + mid * 2 - 1 - left])
                    {
                        check = false;
                        break;
                    }
                }
            }    
            if(check)
                return size;
        }
        size--;
    }
}
```
