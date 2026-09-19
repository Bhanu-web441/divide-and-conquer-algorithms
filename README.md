# divide-and-conquer-algorithms
# Divide-and-Conquer Algorithms: Merge Sort and Quick Sort

## Project Overview

This project analyzes and implements two divide-and-conquer algorithms: 
Merge Sort and Quick Sort. The purpose of the project is to examine their 
theoretical time complexity and compare their practical performance using 
different types and sizes of datasets.

The algorithms are implemented in Python and tested using sorted, 
reverse-sorted, and randomly ordered datasets. Their execution time and 
peak memory usage are measured to compare theoretical expectations with 
observed performance.

## Algorithms Implemented

### Merge Sort

Merge Sort follows the divide-and-conquer approach by dividing an array 
into two smaller halves, recursively sorting each half, and then merging 
the sorted halves.

The recurrence relation for Merge Sort is:

T(n) = 2T(n/2) + Θ(n)

Its overall time complexity is:

- Best Case: Ω(n log n)
- Average Case: Θ(n log n)
- Worst Case: O(n log n)

Merge Sort provides predictable performance regardless of whether the 
input data is already sorted, reverse sorted, or randomly ordered.

### Quick Sort

Quick Sort divides an array around a selected pivot. Elements smaller 
than or equal to the pivot are placed on one side, while larger elements 
are placed on the other side. The resulting partitions are then sorted 
recursively.

This implementation uses the last element as the pivot.

For balanced partitions, the recurrence is:

T(n) = 2T(n/2) + Θ(n)

For highly unbalanced partitions, the recurrence becomes:

T(n) = T(n - 1) + Θ(n)

Its time complexity is:

- Best Case: Ω(n log n)
- Average Case: Θ(n log n)
- Worst Case: O(n²)

The last-element pivot demonstrates how Quick Sort can experience poor 
performance when processing already sorted or reverse-sorted data.

## Experimental Design

Both algorithms are tested on three types of datasets:

1. Sorted data
2. Reverse-sorted data
3. Random data

The experiments use multiple dataset sizes:

- 100 elements
- 500 elements
- 1,000 elements
- 2,000 elements

For each experiment, two performance metrics are recorded:

- Execution time in seconds
- Peak memory usage in kilobytes

Python's `time.perf_counter()` is used to measure execution time, while 
`tracemalloc` is used to monitor peak Python memory allocation.

## Observed Results

The experimental results demonstrate important differences between the 
two divide-and-conquer algorithms.

Merge Sort provides relatively consistent performance across sorted, 
reverse-sorted, and random datasets. This behavior corresponds with its 
Θ(n log n) theoretical time complexity.

Quick Sort performs efficiently on randomly ordered datasets. However, 
its performance decreases substantially on sorted and reverse-sorted 
datasets because the implementation selects the last element as the 
pivot. This can produce highly unbalanced partitions and cause the 
algorithm to approach its O(n²) worst-case behavior.

The experiment therefore demonstrates that theoretical complexity is 
important, but practical performance can also depend on dataset 
characteristics, pivot-selection strategy, recursion overhead, and 
memory allocation.

## Technologies Used

- Python 3
- Google Colab
- GitHub
- `time` module
- `tracemalloc` module
- `random` module

## How to Run the Project

1. Open the notebook in Google Colab or Jupyter Notebook.
2. Run the Python code cells.
3. The program automatically generates sorted, reverse-sorted, and 
   random datasets.
4. Merge Sort and Quick Sort are executed on each dataset.
5. Execution time and peak memory usage are displayed in the output.
6. Compare the results across the different algorithms and dataset types.

## Repository Contents

- `Divide_and_Conquer_Algorithms.ipynb` – Python implementation and 
  experimental testing of Merge Sort and Quick Sort.
- `README.md` – Overview and documentation for the project.

## Key Takeaway

The project demonstrates that algorithms with similar average-case 
complexities can behave very differently in practice. Merge Sort offers 
consistent Θ(n log n) performance but requires additional memory for 
merging. Quick Sort can provide efficient average-case performance with 
lower auxiliary memory requirements, but its performance is highly 
dependent on pivot selection and input arrangement.

The experimental comparison reinforces the importance of considering 
both theoretical complexity and real-world input characteristics when 
selecting an algorithm.
