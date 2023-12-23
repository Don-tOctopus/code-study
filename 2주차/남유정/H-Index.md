### H-Index
``` java
import java.util.Arrays;

class Solution {
    public int solution(int[] citations) {
        int answer = -1;

        Arrays.sort(citations);
        
        for(int i = 0; i < citations.length; i++){
            int smaller = Math.min(citations[i], citations.length-i);
            
            if(smaller > answer)
                answer = smaller;
            else
                break;
        }
        
        return answer;
    }
}
```


### [출처]
https://school.programmers.co.kr/learn/courses/30/lessons/42747