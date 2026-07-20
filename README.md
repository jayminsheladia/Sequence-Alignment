# Sequence Alignment

Implementation of global DNA sequence alignment using two algorithms:

- **Basic Dynamic Programming (DP)**
- **Memory-Efficient Divide and Conquer (Hirschberg's Algorithm)**

This project compares the two approaches in terms of alignment cost, execution time, and memory usage while producing the same optimal alignment.

---

## Overview

The goal of this project is to solve the global sequence alignment problem efficiently. Two different algorithms are implemented:

1. **Basic Dynamic Programming**
   - Uses the full dynamic programming table.
   - Straightforward implementation.
   - Higher memory consumption.

2. **Memory-Efficient Divide and Conquer**
   - Implements Hirschberg's algorithm.
   - Produces the same optimal alignment.
   - Significantly reduces memory usage by storing only the required DP rows.

The project also evaluates the practical performance of both algorithms by measuring CPU time and peak memory usage across different input sizes.

---

## Project Structure

```
Sequence-Alignment/
│
├── basic.py          # Basic Dynamic Programming implementation
├── efficient.py      # Hirschberg's memory-efficient implementation
├── basic.sh          # Runs the basic implementation
├── efficient.sh      # Runs the efficient implementation
└── Summary.pages     # Project report
```

---

## Algorithms

### 1. Basic Dynamic Programming

The standard Needleman-Wunsch algorithm constructs the complete dynamic programming table and performs traceback to recover the optimal alignment.

**Complexity**

- Time: **O(m × n)**
- Space: **O(m × n)**

---

### 2. Memory-Efficient Divide & Conquer

The second implementation uses Hirschberg's algorithm, which recursively divides the alignment problem into smaller subproblems while storing only two rows of the DP table at any time.

**Complexity**

- Time: **O(m × n)**
- Space: **O(m + n)**

---

## Scoring Scheme

### Gap Penalty

```
30
```

### Mismatch Cost Matrix

|     | A | C | G | T |
|-----|---:|---:|---:|---:|
| **A** | 0 |110|48|94|
| **C** |110|0|118|48|
| **G** |48|118|0|110|
| **T** |94|48|110|0|

---

## Input Format

The input file contains compressed sequence information.

Each sequence is generated from:

- An initial DNA string
- A list of insertion indices

The program reconstructs the complete DNA sequences before performing global alignment.

---

## Running the Project

### Basic Algorithm

```bash
./basic.sh input.txt output.txt
```

or

```bash
python3 basic.py input.txt output.txt
```

### Memory-Efficient Algorithm

```bash
./efficient.sh input.txt output.txt
```

or

```bash
python3 efficient.py input.txt output.txt
```

---

## Output

The output file contains:

- Minimum alignment cost
- First aligned sequence
- Second aligned sequence
- Execution time
- Peak memory usage

---

## Performance Comparison

The project compares both implementations on varying problem sizes.

### CPU Time

- Both algorithms have **O(m × n)** time complexity.
- The divide-and-conquer implementation consistently achieves lower runtime overhead in practice for larger inputs.

### Memory Usage

- The basic DP implementation requires **O(m × n)** memory.
- Hirschberg's algorithm reduces memory usage to **O(m + n)** while maintaining the same optimal alignment.

Experimental results included in the project report demonstrate the significant reduction in memory consumption without sacrificing correctness.

---

## Requirements

- Python 3.x

No external libraries are required for the alignment algorithms.

---

## Applications

- DNA sequence alignment
- Computational biology
- Bioinformatics
- Genome comparison
- Evolutionary analysis

---

## References

- Needleman, S. B., & Wunsch, C. D. (1970). *A General Method Applicable to the Search for Similarities in the Amino Acid Sequence of Two Proteins.*
- Hirschberg, D. S. (1975). *A Linear Space Algorithm for Computing Maximal Common Subsequences.*

---

## Authors

Course project on Sequence Alignment implementing and comparing classical Dynamic Programming and Hirschberg's memory-efficient algorithm.