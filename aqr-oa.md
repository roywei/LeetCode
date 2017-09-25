AQR OA



```java
class Solution {
    public double power(int p, int q){
        if(q == 0)
            return 1.0;
        if(q < 0)
            return 1.0/power(p, q*-1);
        return (q%2 == 0)? power(p*p, q/2) : p*power(p*p, q/2);
    }
    
    public int[] sortIntegers(int[] n){
       if(n==null || n.length<1){
               return n;
       }
       int[] records = new int[10];
       for(int num : n){
               records[num-1]++;
       }
                
       int i = 0;
       int j = 0;
       while(i < n.length){
           while(records[j] > 0){
               n[i] = j+1;
               records[j]--;
               i++;
           }
           j++;
        }
                
        return n;
       }
    
    public String sortSegments(String s){
          if(s==null || s.isEmpty()){
                return s;
          }
                
          char[] array = s.toCharArray();
          StringBuilder resultBuilder = new StringBuilder();
          int index = 0;
          boolean numberFlag = (array[index]<='9'&& array[index]>='0');
          boolean preFlag = numberFlag;
          PriorityQueue<Character> tempQueue = new PriorityQueue<Character>(1, new Comparator<Character>(){
                         public int compare(Character o1, Character o2) {
                                                              return o1.compareTo(o2);
                         }
          });
          while(index<array.length){
                     numberFlag = (array[index]<='9'&& array[index]>='0');
                     if(numberFlag == preFlag){
                               tempQueue.add(array[index]);
                               index++;
                     }else{
                               StringBuilder tempBuilder = new StringBuilder();
                               while(!tempQueue.isEmpty()){
                                               tempBuilder.append(tempQueue.remove());
                     }
                     resultBuilder.append(tempBuilder.toString());
                     preFlag = numberFlag;
           }
     }
                
     while(!tempQueue.isEmpty()){
            resultBuilder.append(tempQueue.remove());
     }
     return resultBuilder.toString();
    }
    public static void main(String[] args) {
        System.out.println("Hello World!");
        Solution sol = new Solution();
        //System.out.println(sol.power(3,0));
        //System.out.println(java.util.Arrays.toString(sol.sortIntegers(new int[] {1,4,3,3,2,2,2,10})));
        System.out.println(sol.sortSegments("HJGHJKJNBV"));
    }
}
```



