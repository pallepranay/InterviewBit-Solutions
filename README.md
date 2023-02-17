# InterviewBit-Solutions
public class Solution {
    public int solve(int[] A, int B) {
        HashMap<Integer, Integer> freq =  new HashMap<Integer, Integer>();
        int cnt = 0;
        int xrr = 0;
        int n = A.length;
        for(int i = 0; i < n; i++){
            xrr = xrr ^ A[i];
            if(freq.get(xrr ^ B) != null)
                cnt += freq.get(xrr ^ B);
            if(xrr == B){
                cnt++;
            }
            if(freq.get(xrr) != null)
                freq.put(xrr, freq.get(xrr) + 1);
            else freq.put(xrr, 1);
        }
        return cnt;
    }
}
