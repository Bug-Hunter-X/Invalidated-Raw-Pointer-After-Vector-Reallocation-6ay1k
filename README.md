# Invalidated Raw Pointer After Vector Reallocation
This repository demonstrates a common error in C++: using a raw pointer to access elements of a `std::vector` after the vector's size has been changed.  Accessing the pointer after resizing the vector leads to undefined behavior because the vector might be reallocated to a different memory location.

The `bug.cpp` file shows the erroneous code, while `bugSolution.cpp` presents a corrected version using iterators or accessing elements directly using `[]` operator.

## How to Reproduce
1. Compile `bug.cpp` using a C++ compiler (like g++).
2. Run the executable.  Observe that after reallocating the vector the second loop might print garbage values or crash the program.
3. Compile and run `bugSolution.cpp` to see how to avoid this error.

This example highlights the importance of understanding how `std::vector` manages memory and the potential dangers of using raw pointers with dynamic data structures.