
# 1. Two Sum

#Array #HashMap

Given an array of integers `nums` and an integer `target`, return *indices of the two numbers such that they add up to* `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

## Algorithm

1. let *m* be an empty hash map
2. for *index* from 0 to |*nums*|
   1. *complement* = *target* - *nums*[*index*]
   2. if *m* contains *complement*
      1. *indices* = (*m*(*complement*), *index*)
   3. let *m*(*nums*[*index*]) be *index*

## Code

### Julia

```julia
function two_sum(nums, target)
    m = Dict()
    for (index, num) in enumerate(nums)
        complement = target - num
        complement in keys(m) && (return [m[complement], index])
        m[num] = index
    end
end
```

### Python

```python
def two_sum(nums: list[int], target: int) -> list[int]:
    m = {}
    for index in range(len(nums)):
        complement = target - nums[index]
        if complement in m.keys():
            return [m[complement], index]
        hash_map[nums[index]] = index
```
