# 1. Two Sum

#Array #HashMap

## Problem

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to* `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

## Algorithm

1. let *map* be an empty hash map
2. for *index* from 0 to |*nums*|
   1. *complement* = *target* - *nums*[*index*]
   2. if *map* contains *complement*
      1. *indices* = (*map*(*complement*), *index*)
   3. *hashmap*(*nums*[*index*]) be *index*

## Code

```python
def two_sums(nums: list[int], target: int) -> list[int]:
    hash_map = {}
    for index in range(len(nums)):
        complement = target - nums[index]
        if complement in hash_map.keys():
            return [hash_map[complement], index]
        hash_map[nums[index]] = index
```
