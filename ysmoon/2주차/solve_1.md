✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java 
//2 x n 타일링 
/*
가로 길이가 2이고 세로의 길이가 1인 직사각형모양의 타일이 있습니다.
이 직사각형 타일을 이용하여 세로의 길이가 2이고 가로의 길이가 n인 바닥을 가득 채우려고 합니다.
타일을 채울 때는 다음과 같이 2가지 방법이 있습니다.

타일을 가로로 배치 하는 경우
타일을 세로로 배치 하는 경우
예를들어서 n이 7인 직사각형은 다음과 같이 채울 수 있습니다.

![image](https://user-images.githubusercontent.com/51254596/175820131-cf238a8c-252c-4394-aa3d-de4b619f180a.png)


직사각형의 가로의 길이 n이 매개변수로 주어질 때, 이 직사각형을 채우는 방법의 수를 return 하는 solution 함수를 완성해주세요.
*/

class Solution {
    public int solution(int n) {
        int answer = 0;
        int[] arr = new int[n];
        arr[0] = 1;
        arr[1] = 2;
        
        for (int i = 2; i < n; i++) {
            int num = arr[i - 1] + arr[i - 2];
            arr[i] = num % 1000000007;
        }
        
        return arr[n-1];
    }
}
```
