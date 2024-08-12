# 矩阵对角线元素的和

给你一个正方形矩阵 `mat`，请你返回矩阵对角线元素的和。

请你返回在矩阵主对角线上的元素和副对角线上且不在主对角线上元素的和。

## 示例 1：
>### 输入：
>mat = [[1,2,3],
        [4,5,6],
        [7,8,9]]
>### 输出：25
>### 解释：
>对角线的和为：1 + 5 + 9 + 3 + 7 = 25

## 示例 2：
>### 输入：
>mat = [[1,1,1,1],
            [1,1,1,1],
            [1,1,1,1],
            [1,1,1,1]]
>### 输出：
>8

## 代码：

1.

    public class Solution {
        public int DiagonalSum(int[][] mat) {
            int all=0;
            int n=mat.Length;
            int sta=0;
            int end=n-1;
            for(int i=0;i<n;i++){
                all=all+mat[i][sta++]+mat[i][end--];
            }
            if(n%2==1){all=all-mat[n/2][n/2];}
            return all;
        }
    }
2.

    public class Solution {
        public int DiagonalSum(int[][] mat) {
            int n = mat.Length,sum=0;
            for(int i =0;i<n;i++)
            {
                for(int j =0;j<n;j++)
                {
                    if(i==j||i+j == n-1)
                    {
                        sum+=mat[i][j];
                    }
                }
            }
            return sum;
        }
    }
3.

    public class Solution {
        public int DiagonalSum(int[][] mat) {
            int sum=0;
            for(int i =0;i<mat.Length;i++){
                sum+=mat[i][i];
                if(i!=mat.Length-1-i){
                    sum+=mat[i][mat.Length-i-1];
                }
            }
            return sum;
        }
    }
