# Project Repository AddCompute Function using GPU Programming with Metal Shading Language
This is a repository for writing a function to perform elemental addition of two arrays using metal shading language
This code is directly taken from [this youtube tutorial](https://www.youtube.com/watch?v=VQK28rRK6OU&t=879s)

This mini project compares the time taken to perform elemental addition of two arrays between a CPU and GPU
This CPU method will involve a for-loop through each element of the arrays, while the GPU method will perform direct elemental addition by assigning threads to each element in the arrays.

## Comparing compute times between CPU and GPU method
| Array Size | CPU Method Time | GPU Method Time |
|   :---:    |      :---:      |      :---:      |
|     3      |     0.00002s    |      0.09023s   |
|     30     |     0.00003s    |      0.06043s   |
|     300    |     0.00012s    |      0.02903s   |
|     3000   |     0.00105s    |      0.05356s   |
|    30000   |     0.01129s    |      0.04184s   |
|   300000   |     0.10645s    |      0.04379s   |
|  3000000   |     1.03346s    |      0.04999s   |

We can observe two things here:
1. At small data sizes, the CPU is more efficient than the GPU in computing. This is expected, as the CPU has higher computing power per thread compared to the GPU, while the GPU has much more threads than the CPU, but each thread has low computing power.
2. As the data size increases, we see the time the GPU takes to compute decreases, while the time taken by the CPU increases. This is due to the GPU utilising all its threads to perform the computations in parallel, as opposed to the CPU performing each computation in series.