# Data Structures and Algorithms (DSA)

## 0 - Introduction

### TL;DR
This course covers essential **Data Structures & Algorithms (DSA)** topics required to excel in technical interviews.

### Why DSA Matters
- **Technical Interviews:** Candidates are expected to code efficient algorithms and discuss trade-offs.
- **Career Impact:** Strong DSA skills can significantly impact job offers and compensation.

### Who Is This For?
- **Prerequisites:** Basic knowledge of Python, Java, C++, JavaScript, or C#.
- **Ideal For:**
  - Beginners to DSA.
  - Those needing a refresher.
  - Candidates preparing for technical interviews.

---

## Data Structures
1. [Arrays](Topics/DSA/Arrays_and_Strings.md)
2. [Linked Lists](Topics/DSA/Linked_Lists.md)
3. [Stacks and Queues](Topics/DSA/Stacks_and_Queues.md)
4. [Trees](Topics/DSA/Trees.md)
5. [Graphs](Topics/DSA/Graphs.md)
6. [Hash Tables](Topics/DSA/Hashing.md)
7. [Heaps / Priority Queues](Topics/DSA/Heap_Priority_Queue.md)

---

## Algorithms
1. [Recursion](Topics/DSA/Recursion.md)
2. [Sorting](Topics/DSA/Sorting.md)
3. [Binary Search](Topics/DSA/Binary_Search.md)
4. [Backtracking](Topics/DSA/Backtracking.md)
5. [Dynamic Programming](Topics/DSA/Dynamic_Programming.md)
6. [Greedy Algorithms](Topics/DSA/Greedy_Algorithms.md)
7. [Bit Manipulation](Topics/DSA/Bit_Manipulation.md)
8. [Kadane's Algorithm](#kadanes-algorithm)

---

## Kadane's Algorithm

### Problem Statement
Given an array of integers (positive or negative), find the maximum sum of a (non-empty) **contiguous subarray**.

### Key Insights
1. **Contiguous Subarray:** The subarray must consist of consecutive elements.
2. **Handling Negatives:** If all elements are negative, the maximum sum is the least negative number.
3. **Efficiency:** The algorithm runs in **O(n)** time, making it highly efficient.

### Algorithm Steps
1. Initialize two variables:
   - `max_sum`: Tracks the maximum sum found so far.
   - `current_sum`: Tracks the sum of the current subarray.
2. Iterate through the array:
   - Update `current_sum` as the maximum of the current element or the sum of `current_sum` and the current element.
   - Update `max_sum` if `current_sum` exceeds it.
3. Return `max_sum`.

### Example
```python
def kadane(arr):
    max_sum = current_sum = arr[0]
    for num in arr[1:]:
        current_sum = max(num, current_sum + num)
        max_sum = max(max_sum, current_sum)
    return max_sum

# Example Usage
arr = [4, -1, 2, -7, 3, 4]
print(kadane(arr))  # Output: 7 (Subarray: [3, 4])
