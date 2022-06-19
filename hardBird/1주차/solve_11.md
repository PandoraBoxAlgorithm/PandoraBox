❎ 다른사람의 풀이를 보았나요 ? </br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) </br>
✅ 문제를 한번 더 풀어보았나요 ? </br>

```c++
//JadenCase 문자열 만들기 
/*
JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다. 단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.
*/
string solution(string s) {
    string answer = "";
    for(int i=0;i<s.size();i++){
        //문자열 시작이거나 바로 앞 빈칸인 경우
        if(i==0 || s[i-1]==' '){
            //소문자만 대문자로 변환 후 정답에 추가
            if(s[i]>='a' && s[i]<='z') answer+=s[i]-32;
            else answer+=s[i];
        }
        else {
            //첫 문자가 아닌 경우 대문자를 소문자로 변환
            if(s[i]>='A' && s[i]<='Z') answer+=s[i]+32;
            else answer+=s[i];
        }
    }
    return answer;
}
```
