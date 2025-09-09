# SPLIT THE WORK
Inside the code, I first calculated the DAXPY operation using a simple for loop, and then using a chunk-based approach. The first goal was to create two arrays, d_daxpy and d_chunk, which were technically generated in the same way (i.e., d = a * x + y). A simple equality check (d_daxpy == d_chunk) confirmed that the two arrays are indeed equal.

The second goal was to compute the sum of all elements in the array. In the first case, the sum was obtained using a single variable, a for loop, and the += operator. In the chunk-based method, each chunk computes its own partial sum, and then these partial sums are combined to produce the total sum.

However, when comparing the two total sums, they turned out to be different.
