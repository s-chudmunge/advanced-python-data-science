# Scalable Data Engineering with Dask

## Project Overview: Out-of-Core Processing for 10M+ Rows

This project demonstrates the power of Dask for processing datasets that are too large to fit into a single machine's RAM. We compare the performance and memory efficiency of Dask against pandas for common data engineering tasks like filtering, grouping, and merging.

**Dataset:** A synthetic dataset consisting of 10 million rows, representing transaction logs with timestamps, user IDs, and transaction amounts.

### Scalability Findings
- **Memory Consumption:** Pandas loaded the entire dataset into memory, consuming approximately 1.5GB of RAM. Dask, using lazy evaluation and task graphs, maintained a significantly lower memory footprint during processing.
- **Execution Speed:** While pandas can be faster for small datasets due to overhead, Dask outperformed pandas when the dataset approached the limits of physical memory, preventing "Out of Memory" (OOM) errors.
- **Task Parallelism:** Dask's task scheduler automatically parallelized operations across all available CPU cores, leading to a 3-4x speedup in computation-heavy tasks like complex groupbys.

### Performance Benchmark Table

| Operation | Pandas (Time) | Dask (Time) | Notes |
| :--- | :--- | :--- | :--- |
| Loading Data | 15.2s | 0.8s (Lazy) | Dask only reads metadata. |
| Filtering | 2.1s | 0.4s | Dask parallelizes filtering. |
| GroupBy & Agg | 5.4s | 1.2s | Significant improvement in Dask. |
| Memory Usage | 1.5GB | ~200MB (Peak) | Dask processes in chunks. |

## Implementation Details
The accompanying Jupyter notebook (`dask_scalability.ipynb`) provides a full end-to-end implementation including:
1. **Synthetic Data Generation:** Creating a 10M+ row dataset in CSV format.
2. **Pandas Benchmark:** Measuring execution time and memory for various operations.
3. **Dask Implementation:** Rewriting the same operations using Dask DataFrames.
4. **Performance Comparison:** Visualizing the differences in speed and memory usage.
