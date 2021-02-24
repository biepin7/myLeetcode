[TOC]

# C++

## vector
### reverse 翻转vector 的元素

```
reverse(nums.begin(),nums.end());
reverse(nums.begin(),nums.begin()+k);
reverse(nums.begin()+k,nums.end());
```

## sort


## string

### 大小 
size 和 length 都可以

### 判断是否为数字/字母
``` 
isalnum();
```

### 把字符转换成小写字母
```
tolower()
```

## priority_queue 优先队列
普通的队列是一种先进先出的数据结构，元素在队列尾追加，而从队列头删除。

在优先队列中，元素被赋予优先级。当访问元素时，具有最高优先级的元素最先删除。优先队列具有最高级先出 （first in, largest out）的行为特征。
```
#include<queue>

priority_queue<Type, Container, Functional>

top 访问队头元素
empty 队列是否为空
size 返回队列内元素个数
push 插入元素到队尾 (并排序)
emplace 原地构造一个元素并插入队列
pop 弹出队头元素
swap 交换内容

```



# 经典片段
## 