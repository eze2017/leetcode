# [2989. Class Performance](https://leetcode.cn/problems/class-performance)

[English Version](/solution/2900-2999/2989.Class%20Performance/README_EN.md)

## 题目描述

<!-- 这里写题目描述 -->

<p>Table: <code>Scores</code></p>

<pre>
+--------------+---------+
| Column Name  | Type    |
+--------------+---------+
| student_id   | int     |
| student_name | varchar |
| assignment1  | int     |
| assignment2  | int     |
| assignment3  | int     |
+--------------+---------+
student_id is column of unique values for this table.
This table contains student_id, student_name, assignment1, assignment2, and assignment3.
</pre>

<p>Write a solution to calculate the <strong>difference</strong> in the <strong>total score</strong> (sum of all <code>3</code> assignments) between the <strong>highest score</strong> obtained by students and the <strong>lowest score</strong> obtained by them.</p>

<p>Return <em>the result table in <strong>any</strong> order</em><em>.</em></p>

<p>The result format is in the following example.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> 
Scores table:
+------------+--------------+-------------+-------------+-------------+
| student_id | student_name | assignment1 | assignment2 | assignment3 |
+------------+--------------+-------------+-------------+-------------+
| 309        | Owen         | 88          | 47          | 87          |
| 321        | Claire       | 98          | 95          | 37          |     
| 338        | Julian       | 100         | 64          | 43          |  
| 423        | Peyton       | 60          | 44          | 47          |  
| 896        | David        | 32          | 37          | 50          | 
| 235        | Camila       | 31          | 53          | 69          | 
+------------+--------------+-------------+-------------+-------------+
<strong>Output</strong>
+---------------------+
| difference_in_score | 
+---------------------+
| 111                 | 
+---------------------+
<strong>Explanation</strong>
- student_id 309 has a total score of 88 + 47 + 87 = 222.
- student_id 321 has a total score of 98 + 95 + 37 = 230.
- student_id 338 has a total score of 100 + 64 + 43 = 207.
- student_id 423 has a total score of 60 + 44 + 47 = 151.
- student_id 896 has a total score of 32 + 37 + 50 = 119.
- student_id 235 has a total score of 31 + 53 + 69 = 153.
student_id 321 has the highest score of 230, while student_id 896 has the lowest score of 119. Therefore, the difference between them is 111.
</pre>

## 解法

<!-- 这里可写通用的实现逻辑 -->

**方法一：最大值最小值**

我们可以使用 `MAX` 和 `MIN` 函数来分别获取 `assignment1`、`assignment2`、`assignment3` 的和的最大值和最小值，然后相减即可。

<!-- tabs:start -->

### **SQL**

<!-- 这里可写当前语言的特殊实现逻辑 -->

```sql
# Write your MySQL query statement below
SELECT
    MAX(assignment1 + assignment2 + assignment3) - MIN(
        assignment1 + assignment2 + assignment3
    ) AS difference_in_score
FROM Scores;
```

<!-- tabs:end -->