---
title: Redis数据结构之整数集合
date: 2019-07-28
tags: Redis
id: 1
---

在一个集合中只有为数不多的整数时，Redis 使用 intset 整数集合存储数据。具有如下特性：

```
typedef struct intset {
    //编码方式
    uint32_t encoding;
    //元素数目
    uint32_t length;
    //保存元素的数组
    int8_t contents[];
} intset;
```

1. 数据从小到大排序并且自动去重。
2. 数据类型实际存储在 encoding 中。
3. 当 encoding 中的数据类型不能满足时会自动进行类型升级。
    1. 重新分配空间
    2. 迁移
    3. 添加新元素
    4. 时间复杂度为 O(n)
4. 不支持降级操作。

优点：

1. 灵活，不用考虑整数集合类型，直接添加自动升级。
2. 节省空间，只在必要时进行升级。
    
升级操作是指将整数由 16 位、32 位、64 位的方式增加支持范围。


