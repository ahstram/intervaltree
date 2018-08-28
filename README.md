# intervaltree

## Overview

An interval tree can be used to efficiently find a set of numeric intervals overlapping or containing another interval.

This library provides a basic implementation of an interval tree using C++ templates, allowing the insertion of arbitrary types into the tree.

## Usage

Add `#include "IntervalTree.h"` to the source files in which you will use the interval tree.

To make an IntervalTree to contain objects of class T, use:

```c++
IntervalTree<int, T>::interval_vector intervals;
T a, b, c;
intervals.push_back(IntervalTree<int, T>::interval(2, 10, a));
intervals.push_back(IntervalTree<int, T>::interval(3, 4, b));
intervals.push_back(IntervalTree<int, T>::interval(20, 100, c));
IntervalTree<int, T> tree;
tree = IntervalTree<int, T>(move(intervals));
```

Now, it's possible to query the tree and obtain a set of intervals which are contained within the start and stop coordinates.

```c++
IntervalTree<int, T>::interval_vector results;
results = tree.findContained(start, stop);
cout << "found " << results.size() << " overlapping intervals" << endl;
```

The function IntervalTree::findOverlapping provides a method to find all those intervals which are contained or partially overlap the interval (start, stop).

### Author: Erik Garrison <erik.garrison@gmail.com>

### License: MIT
