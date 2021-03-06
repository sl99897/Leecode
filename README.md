### 记录Leetcode刷的题目
Python版本、Java版本（尚未完成）

## 滑动窗口
解题模板：<br>
windowSize=看求最大还是最小，根据不同的题目设置个初始值<br>
left,right=0<br>
while (right<len(待滑动的列表/字符串)):<br> 
&emsp;&emsp;对当前right位置的元素进行操作<br>
&emsp;&emsp;while(满足了缩小窗口的条件):<br>
&emsp;&emsp;&emsp;&emsp;缩小窗口(更新left的值)<br>
&emsp;&emsp;扩大窗口(更新right的值)<br>
<br>
[209.长度最小的子数组(Python版本)](https://github.com/IPostYellow/Leecode/blob/master/%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3/python/209%E9%95%BF%E5%BA%A6%E6%9C%80%E5%B0%8F%E7%9A%84%E5%AD%90%E6%95%B0%E7%BB%84.py)<br>
思路：创建一个滑动窗口和窗口尺寸，right指针不断向右移，并记录下窗口内的值的总和，如果大于等于给定的值，则判断窗口大小是否比上一次的小，如果小则更新最小窗口大小，并且不断移动left指针缩小窗口，直到窗口内总和小于给定的值为止，每移动一次left指针，再判断一次窗口内总和是否大于等于给定的值而且窗口大小是否比当前最小窗口大小小，如果是则更新最小窗口大小，否则就继续。直到right指针移动过最右边为止。消耗时间44ms,消耗内存15.2MB。对应的模板中的例子就是：<br>
windowSize=给定的数组长度+1<br>
当前窗口内的值总和=0<br>
left,right=0<br>
while (right<len(待滑动的列表/字符串)):<br> 
&emsp;&emsp;将当前的值加入到窗口总和去<br>
&emsp;&emsp;while(当前的窗口内的值总和大于等于给定的阈值s):<br>
&emsp;&emsp;&emsp;&emsp;缩小窗口(更新left的值)<br>
&emsp;&emsp;扩大窗口(更新right的值)<br>
[424.替换后的最长重复字符(python版本)](https://github.com/IPostYellow/Leecode/blob/master/%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3/python/424%E6%9B%BF%E6%8D%A2%E5%90%8E%E7%9A%84%E6%9C%80%E9%95%BF%E9%87%8D%E5%A4%8D%E5%AD%97%E7%AC%A6.py)<br>
思路：将窗口内的字母用哈希表记录下来，判断当前窗口的长度与哈希表中最多的字母数的差是否小于给定的k值，如果小于k值说明窗口还可以继续，否则说明需要移动窗口了，将窗口的左边界移动。消耗时间144ms,消耗内存13.4MB。对应的模板中的例子就是：<br>
窗口内字母哈希表初始化<br>
最大窗口=0<br>
窗口内相同字母最多的个数=0<br>
left,right=0<br>
while (right<len(待滑动的列表/字符串)):<br> 
&emsp;&emsp;将当前的字母记录到哈希表中去，并更新窗口内相同字母最多的个数<br>
&emsp;&emsp;while(当前窗口的长度与哈希表中最多的字母数的差大于给定的k值):<br>
&emsp;&emsp;&emsp;&emsp;将哈希表中left指向的字母个数减1，缩小窗口(更新left的值)<br>
&emsp;&emsp;判断当前窗口大小和历史最大窗口，看看是否要更新最大窗口大小<br>
&emsp;&emsp;扩大窗口(更新right的值)<br>
