建议：我只是粗略的翻译了一下，为了更好的理解，建议看英文。如果有一些单词不明白的可以参考这个文档。
如果看到这个和你看到 codility.com 上的题目不一样时，以codility为准

Zero-indexed arrays A and B consisting of N non-negative integers are given.
Together, they represent N real numbers, denoted as C[0], ..., C[N−1]. Elements
of A represent the integer parts and the corresponding elements of B (divided
by 1,000,000) represent the fractional parts of the elements of C. More
formally, A[I] and B[I] represent C[I] = A[I] + B[I] / 1,000,000.

从0开始索引的数组 A 和 B 是由 N 个正整数组成。将2者计算后获得数组C，表示为
C[0], ..., C[N-1]。Elements of A represent the integer parts and the
corresponding elements of B (divided by 1,000,000) represent the fractional
parts of the elements of C. 例如, A[I] 和 B[I] 计算出来的 C[I] = A[I] + B[I] /
1,000,000.

For example, consider the following arrays A and B:

例如，看下面的数组 A 和 数组 B：

  A[0] = 0  B[0] = 500,000
  
  A[1] = 1  B[1] = 500,000
  
  A[2] = 2  B[2] = 0
  
  A[3] = 2  B[3] = 0
  
  A[4] = 3  B[4] = 0
  
  A[5] = 5    B[5] = 20,000

They represent the following real numbers:

计算成下面的实数:

  C[0] = 0.5
  
  C[1] = 1.5
  
  C[2] = 2.0
  
  C[3] = 2.0
  
  C[4] = 3.0
  
  C[5] = 5.02

A pair of indices (P, Q) is multiplicative if 0 ≤ P < Q < N and C[P] * C[Q] ≥ C[P] + C[Q].

The above arrays yield the following multiplicative pairs:
上面的数组返回一下的索引结果：

     (1, 4), because 1.5 * 3.0 = 4.5 ≥ 4.5 = 1.5 + 3.0,
     (1, 5), because 1.5 * 5.02 = 7.53 ≥ 6.52 = 1.5 + 5.02,
     (2, 3), because 2.0 * 2.0 = 4.0 ≥ 4.0 = 2.0 + 2.0,
     (2, 4) and (3, 4), because 2.0 * 3.0 = 6.0 ≥ 5.0 = 2.0 + 3.0.
     (2, 5) and (3, 5), because 2.0 * 5.02 = 10.04 ≥ 7.02 = 2.0 + 5.02.
     (4, 5), because 3.0 * 5.02 = 15.06 ≥ 8.02 = 3.0 + 5.02.


写一个函数:
class Solution { public int solution(int[] A, int[] B); }
注意：这里根据实际语言看到的函数，这里以java举例

that, given zero-indexed arrays A and B, each containing N non-negative
integers, returns the number of multiplicative pairs of indices.
这个函数用 以0为索引的数组 A 和 B 作参数，每一个数组包含 N 个正整数，返回找到的
multiplicative pairs of indices 的数量。

If the number of multiplicative pairs is greater than 1,000,000,000, the
function should return 1,000,000,000.
当 multiplicative pairs of indices 的数量超过 1,000,000,000, 函数反回
1,000,000,000

For example, given:
例如，给出这样的：

  A[0] = 0    B[0] = 500,000
  A[1] = 1    B[1] = 500,000
  A[2] = 2    B[2] = 0
  A[3] = 2    B[3] = 0
  A[4] = 3    B[4] = 0
  A[5] = 5    B[5] = 20,000

the function should return 8, as explained above.
函数应该返回8

Assume that:
假设如下：

    N is an integer within the range [0..100,000];
    N 是一个integer在 0..100,000 的范围内
    each element of array A is an integer within the range [0..1,000];
    数组A的每个元素是一个integer，范围在 0..1,000
    each element of array B is an integer within the range [0..999,999];
    数组A的每个元素是一个integer，范围在 0..999,999
    real numbers created from arrays are sorted in non-decreasing order.
    创建的实数数组的排序为 non-descreasing

Complexity:
    expected worst-case time complexity is O(N);
    expected worst-case space complexity is O(1), beyond input storage (not
    counting the storage required for input arguments).

Elements of input arrays can be modified.
