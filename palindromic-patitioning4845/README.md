<h2><a href="https://www.geeksforgeeks.org/problems/palindromic-patitioning4845/1">Palindromic Partitioning</a></h2>
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
Palindromic Partitioning
HardAccuracy: 27.82%Submissions: 172K+Points: 8

Given a string s, a partitioning of the string is a palindrome partitioning if every sub-string of the partition is a palindrome. Determine the fewest cuts needed for palindrome partitioning of the given string.

Examples:

Input: s = "geek" 
Output: 2 
Explanation: We need to make minimum 2 cuts, i.e., "g | ee | k".
Input: s = "aaaa" 
Output: 0
Explanation: The string is already a palindrome.
Input: s = "ababbbabbababa" 
Output: 3
Explanation: We need to make minimum 3 cuts, i.e., "aba | bb | babbab | aba".

Constraints:
1 ≤ |s| ≤ 103
s contain lowercase letters only

Try more examples
Expected Complexities
Company Tags
AmazonMicrosoftGoogle
Topic Tags
Related Articles
Report An Issue
If you are facing any issue on this page. Please let us know.
Output Window
Compilation Results
Custom Input
Request Queued

Ready for evaluation 

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
class Solution {
    public int palPartition(String s) {
        int n = s.length(), dp[] = new int[n + 1];
        for (int i = 0; i <= n; i++) dp[i] = i - 1;
        for (int i = 0; i < n; i++) {
            for (int l : new int[]{0, 1}) // even and odd expansion
                for (int h = i, k = i + l; h >= 0 && k < n && s.charAt(h) == s.charAt(k); h--, k++)
                    dp[k + 1] = Math.min(dp[k + 1], 1 + dp[h]);
        }
        return dp[n];
    }
}
 
Custom InputCompile & RunSubmit</h3>
<hr>
<div class="problem-statement">
<p><span style="font-size: 14pt;">Given a string <strong>s</strong>,&nbsp;a partitioning of the string is a<strong>&nbsp;palindrome partitioning&nbsp;</strong>if every sub-string of the partition is a <strong>palindrome</strong>.&nbsp;Determine the <strong>fewest cuts</strong> needed for <strong>palindrome partitioning</strong> of the given string.</span></p>
<p><span style="font-size: 14pt;"><strong>Examples:</strong></span></p>
<pre><span style="font-size: 14pt;"><strong><strong>Input:</strong></strong> s = "geek"&nbsp;<br><strong><strong>Output:</strong></strong> 2&nbsp;<br><strong><strong>Explanation: </strong></strong>We need to make minimum 2 cuts, i.e., "g | ee | k".</span></pre>
<pre><span style="font-size: 14pt;"><strong><strong>Input: </strong></strong>s = "aaaa" <br><strong><strong>Output</strong></strong>: 0<br><strong><strong>Explanation:</strong></strong> The string is already a palindrome.</span></pre>
<pre><span style="font-size: 14pt;"><strong>Input:</strong> s = "ababbbabbababa"&nbsp;</span><br><span style="font-size: 14pt;"><strong>Output: </strong>3</span><br><span style="font-size: 14pt;"><strong>Explanation:</strong> We need to make minimum 3 cuts, i.e., "aba | bb | babbab | aba".</span></pre>
<p><span style="font-size: 14pt;"><strong>Constraints:</strong><br>1 ≤ |s| ≤ 10<sup>3<br></sup><sup>s contain lowercase letters only</sup></span></p>
</div>

---
<p align="center">
  <a href="https://www.geeksforgeeks.org/problems/palindromic-patitioning4845/1">View Problem on GeeksforGeeks</a>
</p>