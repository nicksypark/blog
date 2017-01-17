---
layout: post
title: "Insertion Sort"
description: "Loop Invariants and Insertion sort"
date: 2017-01-11
tags: [sorting, algorithm]
comments: true
share: false
---

## Loop Invariants

```
In computer science, a loop invariant is a property of a program loop that is true before (and after) each iteration. It is a logical assertion, sometimes checked within the code by an assertion call. Knowing its invariant(s) is essential in understanding the effect of a loop [^1].
```

Basically, loop invariants is used to prove the correctness of loop algorithms.
In a loop, the state always changes, but a loop invariant is true for each iteration.

Three categories to satisfy to prove loop invariants:

  1) Initialization: Check if it is true prior to the initial iteration.

  2) Maintenance: Check if it is true before an iteration of the loop, it remains true before the next iteration.

  3) Termination: When the loop ends, we should get a meaningful and useful result which will help to show the correctness of the algorithm.

## Insertion sort

The insertion sort implementation in Lua.

```lua
function insertionSort(array)
  for j = 2, #array do
    local key = array[j]
    local i = j - 1
    while i > 0 and array[i] > key do
      array[i + 1] = array[i]
      i = i - 1
    end
    array[i + 1] = key
  end
  return array
end

return insertionSort
```


####  Loop Invariant in Insertion sort


```lua
function insertionSort(array)   
-- Initialization: before the initial interval, j = 2. array[1] should be sorted, and it surely is.      
  for j = 2, #array do            
    local key = array[j]
    local i = j - 1

    -- Maintenance: As loop goes, j will be incremented and array[1...j-1] is sorted.
    while i > 0 and array[i] > key do
      array[i + 1] = array[i]
      i = i - 1
    end
    array[i + 1] = key
  end

  -- Termination: the loop ends when j = length(array) + 1, and array[1...j] is sorted.
  return array
end

return insertionSort
```

#### The unit test of insertion sort with Lua Busted

```lua
local insertionSort = require('insertionSort')

describe('insertionSort', function()
  it('should sort over an empty array', function()
    assert.are.same({}, insertionSort({}))
  end)

  it('should sort over an array with a single element', function()
    assert.are.same({ 3 }, insertionSort({ 3 }))
  end)

  it('should sort over an array with several elements', function()
    assert.are.same({ 1, 2, 3 }, insertionSort({ 3, 2, 1 }))
  end)

  it('should sort over an array with same elements', function()
    assert.are.same({ 2, 2, 3, 3, 4 }, insertionSort({ 3, 2, 4, 2, 3 }))
  end)

  it('should not modify the input array', function()
    local input = { 1, 2, 3 }
    insertionSort(input)
    assert.are.same({ 1, 2, 3 }, input)
  end)
end)

```

## Reference
[^1] https://en.wikipedia.org/wiki/Loop_invariant
