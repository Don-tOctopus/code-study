### N으로 표현

``` java
import java.util.Set;
import java.util.HashSet;

class Solution {
    public int solution(int N, int number) {
        int answer = -1;
        
        Set<Integer>[] dp = new Set[9];
        
        for(int i=1;i<9;i++){
            int repeatN = getRepeatByCount(N, i);
            dp[i] = new HashSet<>();
            dp[i].add(repeatN);
        }
        
        for(int i=2;i<9;i++){
            for(int j=1;j<= i/2 ;j++){
                union(dp[i], dp[i-j], dp[j]);
                union(dp[i], dp[j], dp[i-j]);

            }

        }
        
        for(int i=1;i<9;i++){
            if(dp[i].contains(number)){
               return i;
            }
        }
        return answer;
    }
    
    private int getRepeatByCount(int n, int count){
        return Integer.parseInt(String.valueOf(n).repeat(count));

    }
    
    private void union(Set<Integer> dp, Set<Integer> A, Set<Integer> B){

        for(int a : A){
            for(int b : B){
                dp.add(a+b);
                dp.add(a-b);
                dp.add(a*b);
                if(b != 0){
                   dp.add(a/b);
                }

            }
        }
    }
}
```

### [출처]
https://school.programmers.co.kr/learn/courses/30/lessons/42895