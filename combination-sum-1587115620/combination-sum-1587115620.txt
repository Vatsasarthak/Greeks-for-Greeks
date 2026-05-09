class Solution {
    public ArrayList<ArrayList<Integer>> targetSumComb(int[] A, int B) {
        java.util.Arrays.sort(A);
        ArrayList<Integer> uniqueCandidates = new ArrayList<>();
        if (A.length > 0) {
            uniqueCandidates.add(A[0]);
            for (int i = 1; i < A.length; i++) {
                if (A[i] != A[i - 1]) uniqueCandidates.add(A[i]);
            }
        }
        ArrayList<ArrayList<Integer>> res = new ArrayList<>();
        helper(uniqueCandidates, B, new ArrayList<>(), res, 0, 0);
        return res;
    }
    static void helper(ArrayList<Integer> arr, int target, ArrayList<Integer> currentList, 
                        ArrayList<ArrayList<Integer>> res, int currentSum, int startIdx) {
        if (currentSum == target) {
            res.add(new ArrayList<>(currentList));
            return;
        }
        if (currentSum > target) return;

        for (int i = startIdx; i < arr.size(); i++) {
            currentList.add(arr.get(i));
            helper(arr, target, currentList, res, currentSum + arr.get(i), i);
            currentList.remove(currentList.size() - 1);
        }
    }
}