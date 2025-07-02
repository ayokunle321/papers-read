# Notes 

- SYCL automatically manages synchronization kernel dependencies i.e., a RAW dependency whereby the kernel writes to a memory address that another kernel writes reads from, then the other would automatically wait for the first one to finish. This differs from CUDA where this has to be done manually.  

- SYCL handles data management automatically as well i.e., unlike CUDA, no need for memcpys to and from device/host. 

- SYCL is just plain C++. It leverages modern constructs. On the other hand, OpenCL and CUDA extend C++ (this is because cause they're older and teh constructs available then did not suffice). 

- SYCL has 2 memory modes - Unified Shared Memory (user deals with data management manually i.e. malloc and free) & The buffer & accessor model (runtime deals with data management and keeps track of kernel dependencies)

- The ability to nest operations in MLIR allows host and device code to be in the same module. This enables better analysis as there is more information on kernel invocation from the host and their contexts.

- In the dialect introduced, SYCL abstractions such as id, item, nd_item, range (classes used for thread's position/scope and structured parallelism) are represnted as types. Also the accessor class is modelled as a type while accesses are operations. 