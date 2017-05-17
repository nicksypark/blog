---
layout: post
title: "Quick Sort"
description: "Quick sort"
date: 2017-04-16
tags: [sorting, algorithm]
comments: true
share: false
---

## Quick sort

1. The best practical choice for sorting
2. Efficient in storage
3. Another Divide-and-conquer based algorithm

![QuickSort](/assets/images/DivideAndConquerParadigm.png){:class="img-responsive"}

#### Quick Sort Example

![QuickSort](/assets/images/QuickSortEx1.png){:class="img-responsive"}
![QuickSort](/assets/images/QuickSortEx2.png){:class="img-responsive"}
![QuickSort](/assets/images/QuickSortEx3.png){:class="img-responsive"}
![QuickSort](/assets/images/QuickSortEx4.png){:class="img-responsive"}

#### Quick Sort Pseudo code

![QuickSort](/assets/images/QuickSort_Pseudo1.png){:class="img-responsive"}
![QuickSort](/assets/images/QuickSort_Pseudo2.png){:class="img-responsive"}

#### Recurrence equation for Quick Sort (Worst case)

Based on the assumption that each element in the input array is distinct, the location of pivot and the formation of inputs is affecting the performance of quick sort. The worst case input for quick sort is an array sorted in either increasing or decreasing order when the pivot is always the first or the last element. In this case, the pivot happens to be the smallest or biggest element and the pivot becomes the first or the last element splitting the array into zero and the rest.

![QuickSort](/assets/images/QuickSort_WorstCase.png){:class="img-responsive"}


Solving this recurrence equation with recursion Tree:

![QuickSort](/assets/images/QuickSort_WorstCaseRecursionTree.png){:class="img-responsive"}


#### Recurrence equation for Quick Sort (Best case)

![QuickSort](/assets/images/QuickSort_BestCase.png){:class="img-responsive"}


#### Average case

The average case input would be any randomly generated arrays and the pivot is at the random position every step.


#### How to avoid the worst case

- Slow if input is ordered
- Fast otherwise

Answer: Partition around a random pivot element.
Question: Does it always guarantee O(nlgn)? What if the random pivot always happen to be the smallest or biggest?

We want to guarantee to find the median all the time, but it has to run in linear time.
We can use SELECT algorithm which runs in linear time.

![QuickSort](/assets/images/SelectAlgorithm1.png){:class="img-responsive"}
![QuickSort](/assets/images/SelectAlgorithm2.png){:class="img-responsive"}
![QuickSort](/assets/images/SelectPseudoCode.png){:class="img-responsive"}
