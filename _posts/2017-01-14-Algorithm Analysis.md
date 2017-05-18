---
layout: post
title: "Algorithm analysis"
description: "Asymptotic notations"
date: 2017-01-14
tags: [algorithm]
comments: true
share: false
---

## Time Analysis
We need some sorts of measurements to determine how processing time increases as the problem size increases. The direct measurements of the execution time is not good since the execution time is heavily dependent on the performance of hardware.
Need to express the execution time as a function of input size so it is independent of machine or programming quality.

## Insertion sort example

The insertion sort implementation in Lua.
The execution time depends on the number of elements to be sorted and the input array since an already sorted sequence is easier to sort.

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
```

#### Best case: O(n)
Array is already sorted. This provides a lower bound on running time.

#### Worst case: O(n^2)
Array is sorted in reverse order. This provides an upper bound on running time.

#### Average case: O(n^2)
This is the expected time over all input variances (sizes).

## Asymptotic Analysis
We need to measure the rate of growth asymptotically and irrelevantly to the machine performance.

## Asymptotic notation:
* Big O-notation is asymptotic upper bound.
* Big Omega-notation is asymptotic lower bound.
* Theta notation is tight bounds.
* Little o-notation
* Little omega-notation

![AlgorithmAnalysis](/assets/images/AsymptoticNotation.png){:class="img-responsive"}
