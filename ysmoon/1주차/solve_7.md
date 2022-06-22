✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>
<br>
//숫자의 표현 <br>
/* <br>
문자열 s에는 공백으로 구분된 숫자들이 저장되어 있습니다. <br>
str에 나타나는 숫자 중 최소값과 최대값을 찾아 이를 "(최소값) (최대값)"형태의 문자열을 반환하는 함수, solution을 완성하세요.<br>
예를들어 s가 "1 2 3 4"라면 "1 4"를 리턴하고, "-1 -2 -3 -4"라면 "-4 -1"을 리턴하면 됩니다.
<br>
*/
```java
class Solution {
    public String solution(String s) {
        String answer = "";
        String[] arr = s.split(" ");
        int min = 0;
        int max = 0;

        min = max = Integer.parseInt(arr[0]);
        for(int i=1; i<arr.length; i++) {
            int n = Integer.parseInt(arr[i]);

            if(min>n) {
                min = n;
            }

            if(max<n) {
                max = n;
            }

        }
        answer = "" + min + " " + max;
        return answer;
    }
}
```
