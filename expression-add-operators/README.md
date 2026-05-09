<h2><a href="https://www.geeksforgeeks.org/problems/expression-add-operators/1">Expression Add Operators</a></h2>
<h3>Difficulty: Courses
Tutorials
Practice
Jobs

Back to Explore Page

Ask A Doubt
My Doubts
FREQUENTLY ASKED QUESTIONS
Give me a hint
Dry Run the Example with approach
Identify the Boundary cases to consider
Problem
Editorial
Submissions
Comments
Expression Add Operators
HardAccuracy: 61.49%Submissions: 32K+Points: 8Average Time: 40m

Given a string s that contains only digits (0-9) and an integer target, return all possible strings by inserting the binary operator ' + ', ' - ', and/or ' * ' between the digits of s such that the resultant expression evaluates to the target value.

Note:

Operands in the returned expressions should not contain leading zeros. For example, 2 + 03 is not allowed whereas 20 + 3 is fine.
It is allowed to not insert any of the operators.
Driver code will print the final list of strings in lexicographically smallest order.

Examples:

Input: s = "124", target = 9
Output: ["1+2*4"]
Explanation: The valid expression that evaluate to 9 is 1 + 2 * 4
Input: s = "125", target = 7
Output: ["1*2+5", "12-5"]
Explanation: The two valid expressions that evaluate to 7 are 1 * 2 + 5 and 12 - 5.
Input: s = "12", target = 12
Output: ["12"] 
Explanation: s itself matches the target. No other expressions are possible.
Input: s = "987612", target = 200
Output: []
Explanation: There are no expressions that can be created from "987612" to evaluate to 200.

Constraints:
1 ≤ s.size() ≤ 9
s consists of only digits (0-9).
-231 ≤ target ≤ 231-1

Try more examples
Expected Complexities
Topic Tags
Related Articles
Report An Issue
If you are facing any issue on this page. Please let us know.
Output Window
Compilation Results
Custom Input
Y.O.G.I. (AI Bot)
Problem Solved Successfully

Suggest Feedback

Test Cases Passed
1120 / 1120
Attempts : Correct / Total
2 / 2
Accuracy :
100%
Time Taken
1.95
You get marks only for the first correct submission if you solve the problem without viewing the full solution.

Solve Next

All Palindromic Partitions
Find the String
Better String
Java (21)
Start Timer
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
class Solution {
    int count = 0;
    public ArrayList<String> findExpr(String s, int target) {
        // code here
        int idx = s.length()-1;
        ArrayList<String> list = new ArrayList<>();
        
        findExpr2(s,list,idx,target);
        
        return list;
    }
    private void findExpr2(String s, ArrayList<String> list, int idx, int target){
        if(idx <= 0){
            if(solve(s,target)){
                list.add(s);
            }
            return;
        }
        findExpr2(s,list,idx-1,target);
        
        StringBuilder sb = new StringBuilder(s);
        if(idx >= 0 && idx < s.length()) sb.insert(idx,'*');
        findExpr2(sb.toString(),list,idx-1,target);
        
        sb = new StringBuilder(s);
        if(idx >= 0 && idx < s.length()) sb.insert(idx,'-');
        findExpr2(sb.toString(),list,idx-1,target);
        
        sb = new StringBuilder(s);
        if(idx >= 0 && idx < s.length()) sb.insert(idx,'+');
        findExpr2(sb.toString(),list,idx-1,target);
    }
    private boolean solve(String s, int tar){
        int n = s.length();
        ArrayList<Long> list = new ArrayList<>();
        ArrayList<Character> list2 = new ArrayList<>();
        ArrayList<Long> list3 = new ArrayList<>();
        ArrayList<Character> list4 = new ArrayList<>();
        HashSet<Integer> hs = new HashSet<>();
 
Custom InputCompile & RunSubmit</h3>
<hr>
<div class="problem-statement">
<p><span style="font-size: 18px;">Given a string <strong>s</strong> that contains only digits (0-9) and an integer <strong>target</strong>, return <strong>all possible</strong> strings by inserting the binary operator <strong>' + '</strong>, <strong>' - '</strong>, and/or <strong>' * '</strong> between the digits of <strong>s</strong> such that the resultant expression evaluates to the <strong>target</strong> value.</span></p>
<p><span style="font-size: 18px;"><strong>Note:</strong></span></p>
<ol>
<li><span style="font-size: 18px;"><strong> </strong>Operands in the returned expressions&nbsp;should not contain leading zeros. For example, 2 + 03 is not allowed whereas 20 + 3 is fine. </span></li>
<li><span style="font-size: 18px;">It is allowed to not insert any of the operators.</span></li>
<li><span style="font-size: 18px;"><span style="font-size: 18px;">Driver code will print the final list of strings in lexicographically smallest order.</span></span></li>
</ol>
<p><span style="font-size: 18px;"><strong>Examples:</strong></span></p>
<pre style="--darkreader-inline-bgcolor: #222426; --darkreader-inline-bgimage: initial; --darkreader-inline-border-bottom: #3e4446; --darkreader-inline-border-left: #3e4446; --darkreader-inline-border-right: #3e4446; --darkreader-inline-border-top: #3e4446; background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><span style="font-size: 18px;"><strong>Input: </strong>s = "124", target = 9<br><strong>Output:&nbsp;</strong>["1+2*4"]<br><strong>Explanation:</strong> The valid expression that evaluate to 9 is 1 + 2 * 4</span></pre>
<pre style="--darkreader-inline-bgcolor: #222426; --darkreader-inline-bgimage: initial; --darkreader-inline-border-bottom: #3e4446; --darkreader-inline-border-left: #3e4446; --darkreader-inline-border-right: #3e4446; --darkreader-inline-border-top: #3e4446; background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><span style="font-size: 18px;"><strong>Input:&nbsp;</strong>s = "125", target = 7<br><strong>Output:&nbsp;</strong>["1*2+5", "12-5"]<br><strong>Explanation:</strong> The two valid expressions that evaluate to 7 are 1 * 2 + 5 and 12 - 5.</span></pre>
<pre style="--darkreader-inline-bgcolor: #222426; --darkreader-inline-bgimage: initial; --darkreader-inline-border-bottom: #3e4446; --darkreader-inline-border-left: #3e4446; --darkreader-inline-border-right: #3e4446; --darkreader-inline-border-top: #3e4446; background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><span style="font-size: 18px;"><strong>Input: </strong>s = "12", target = 12<br><strong>Output:</strong> ["12"]&nbsp;<br><strong>Explanation:</strong> s itself matches the target. No other expressions are possible.</span></pre>
<pre style="--darkreader-inline-bgcolor: #222426; --darkreader-inline-bgimage: initial; --darkreader-inline-border-bottom: #3e4446; --darkreader-inline-border-left: #3e4446; --darkreader-inline-border-right: #3e4446; --darkreader-inline-border-top: #3e4446; background: #eeeeee; border: 1px solid #cccccc; padding: 5px 10px;"><span style="font-size: 18px;"><strong>Input: </strong>s = "987612", target = 200<br><strong>Output:</strong> []<br><strong>Explanation:</strong> There are no expressions that can be created from "987612" to evaluate to 200.</span></pre>
<p><span style="font-size: 18px;"><strong>Constraints:</strong><br>1 ≤ s.size() ≤ 9<br>s consists of only<strong> </strong>digits (0-9).<br>-2<sup>31&nbsp;</sup>≤&nbsp;target&nbsp;≤&nbsp;2<sup>31</sup>-1</span></p>
</div>

---
<p align="center">
  <a href="https://www.geeksforgeeks.org/problems/expression-add-operators/1">View Problem on GeeksforGeeks</a>
</p>