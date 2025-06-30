# Notes 

- SYCL automatically manages synchronization kernel dependencies i.e., a RAW dependency whereby the kernel writes to a memory address that another kernel writes reads from, then the other would automatically wait for the first one to finish. This differs from CUDA where this has to be done manually.  

- SYCL handles data management automatically as well i.e., unlike CUDA, no need for memcpys to and from device/host. 



