### H-Index

``` java
import java.util.Arrays;

class Solution {
    public int solution(int[] citations) {
        int answer = 0;
        
        Arrays.sort(citations);
        
        for(int i=citations.length - 1;i>= 0;i--){
            if(citations[i] >= citations.length-i){
                answer = Math.max(answer, citations.length-i);
            }    
        }
        return answer;
    }
    
    
}
```

### [출처]
https://school.programmers.co.kr/learn/courses/30/lessons/42747?language=java#