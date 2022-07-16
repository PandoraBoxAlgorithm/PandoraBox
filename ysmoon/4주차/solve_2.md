✅ 다른사람의 풀이를 보았나요 ? <br>
❎ STL을 검색하여서 풀었나요 ? (sort 같은 라이브러리 사용) <br>
✅ 문제를 한번 더 풀어보았나요 ? <br>

```java 
//다리를 지나는 트럭
/*
트럭 여러 대가 강을 가로지르는 일차선 다리를 정해진 순으로 건너려 합니다. 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 알아내야 합니다. 다리에는 트럭이 최대 bridge_length대 올라갈 수 있으며, 다리는 weight 이하까지의 무게를 견딜 수 있습니다. 단, 다리에 완전히 오르지 않은 트럭의 무게는 무시합니다.

예를 들어, 트럭 2대가 올라갈 수 있고 무게를 10kg까지 견디는 다리가 있습니다. 무게가 [7, 4, 5, 6]kg인 트럭이 순서대로 최단 시간 안에 다리를 건너려면 다음과 같이 건너야 합니다.

경과 시간	다리를 지난 트럭	다리를 건너는 트럭	대기 트럭
0	[]	[]	[7,4,5,6]
1~2	[]	[7]	[4,5,6]
3	[7]	[4]	[5,6]
4	[7]	[4,5]	[6]
5	[7,4]	[5]	[6]
6~7	[7,4,5]	[6]	[]
8	[7,4,5,6]	[]	[]
따라서, 모든 트럭이 다리를 지나려면 최소 8초가 걸립니다.

solution 함수의 매개변수로 다리에 올라갈 수 있는 트럭 수 bridge_length, 다리가 견딜 수 있는 무게 weight, 트럭 별 무게 truck_weights가 주어집니다. 이때 모든 트럭이 다리를 건너려면 최소 몇 초가 걸리는지 return 하도록 solution 함수를 완성하세요.
*/
import java.util.*;

class Solution {
    public int solution(int bridge_length, int weight, int[] truck_weights) {
      Queue<Integer> queue = new LinkedList<>();
		  int sum = 0;
		  int time = 0; 

		  for(int i = 0; i < truck_weights.length; i++) { 
			  int truck = truck_weights[i];

			  while(true) {
				  if(queue.isEmpty()) { // 큐에 아무것도 없는 경우
					  queue.add(truck);
					  sum += truck;
					  time++;
					  break;
				  } else if(queue.size() == bridge_length) { // 큐에 다리 길이만큼 트럭이 다 찬 경우 
					  sum -= queue.poll();
				  } else  { // 다리 길이만큼 큐가 차지않았음
					  // weight 값을 넘지 않는 선에서 새로운 트럭을 다리에 올려줌 
					  if(sum + truck <= weight) {
						  queue.add(truck);
						  sum += truck;
						  time++;
						  break;
					  } else { 
						  // 넘는다면 0을 넣어 이미 큐에 있는 트럭이 다리를 건너게 만듬 
						  queue.add(0);
						  time++;
					  }
				  }
			  }
		  }

    // 마지막 트럭에서 반복문이 끝나는데, 마지막 역시 다리 길이만큼 지나가야하기에 + 다리 길이 
		return time + bridge_length; 
    }
}
```
