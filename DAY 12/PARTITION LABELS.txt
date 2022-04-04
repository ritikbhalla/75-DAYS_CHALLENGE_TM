class Solution {
    public List<Integer> partitionLabels(String s) {
        List<Integer> indices=new ArrayList<>();
        Map<Character, Integer> map = new HashMap<>(26);
        int maxIndex = 0, position = 0;
        
        for(int i=0; i<s.length(); i++) {
            map.put(s.charAt(i), i);
        }
        
        for(int i=0; i<s.length(); i++) {
            maxIndex = Math.max(maxIndex, map.get(s.charAt(i)));
            if(i == maxIndex) {
                indices.add(i - position + 1);
                position = i+1;
            }
        }
        
        return indices;
    }
}