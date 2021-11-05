---
title: LeetCode 第一题：两数之合
date: 2021-11-04 17:21:44
categories: Web
tags: LeetCode
---

> 有人相爱，有人夜里开车看海，有人 `Leetode` 第一题都做不出来。

给定一个整数数组 `nums` 和一个整数目标值 `target`，请你在该数组中找出 和为目标值 `target` 的那两个整数，并返回它们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

你可以按任意顺序返回答案。

使用 `map` 对象：

```JavaScript
const twoSum = function (nums, target) {
    const len = nums.length;
    const map = new Map();
    for (let i = 0; i < len; i++) {
        const needNum = target - nums[i];
        if (map.has(needNum) && i !== map.get(needNum)) {
            return [i, map.get(needNum)];
        }
        map.set(nums[i], i);
    }
}
```
