✅ 다른사람의 풀이를 보았나요 ? <br>
✅ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>
<br>
//JadenCase 문자열 만들기 <br>
/* <br>
JadenCase란 모든 단어의 첫 문자가 대문자이고, 그 외의 알파벳은 소문자인 문자열입니다.<br>
단, 첫 문자가 알파벳이 아닐 때에는 이어지는 알파벳은 소문자로 쓰면 됩니다. (첫 번째 입출력 예 참고)<br>
문자열 s가 주어졌을 때, s를 JadenCase로 바꾼 문자열을 리턴하는 함수, solution을 완성해주세요.<br>
<br>
*/
```java
class Solution {
    public String solution(String s) {
        StringBuilder answer = new StringBuilder();

        String firstStr = s.charAt(0) + "";
        answer.append(firstStr.toUpperCase()); // 첫 글자는 무조건 대문자

        for (int i = 1; i < s.length(); i++) {
            String str = s.charAt(i) + "";
            if (str.equals(" ")) { // 공백
                answer.append(" ");
            } else if (s.charAt(i - 1) == ' ') { // 전 문자열이 공백이면
                answer.append(str.toUpperCase()); // 대문자
            } else {
                answer.append(str.toLowerCase()); // 소문자
            }
        }
        return answer.toString();
    }
}
```
