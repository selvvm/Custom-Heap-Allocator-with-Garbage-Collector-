# Simple Memory Allocator with Garbage Collection

This repository contains a simple memory allocator implemented in C, featuring a basic garbage collection mechanism. The allocator manages a fixed-size heap and supports memory allocation and deallocation, as well as automatic garbage collection.

## Overview

The memory allocator consists of the following components:
- **Heap**: A fixed-size array that represents the available memory.
- **ChunkList**: A structure to manage allocated and freed memory chunks.
- **Garbage Collector**: A simple mark-and-sweep garbage collector to reclaim unused memory.

## Files

- `main.c`: The main C file that contains the implementation of the memory allocator, garbage collector, and test cases.

## Dependencies

- Standard C libraries (stdio, stdbool, string, stdint, assert)

## How to Run

1. Clone this repository:
    ```sh
    git clone https://github.com/yourusername/simple-memory-allocator.git
    cd simple-memory-allocator
    ```

2. Compile the code:
    ```sh
    gcc main.c -o memory_allocator
    ```

3. Run the executable:
    ```sh
    ./memory_allocator
    ```

## Code Structure

### MemoryChunk and ChunkList

- **MemoryChunk**: Represents a chunk of memory with a starting address and size.
- **ChunkList**: A list of memory chunks, used to manage allocated and freed memory.

### Memory Allocation Functions

- **insert_chunk**: Inserts a memory chunk into a `ChunkList`.
- **merge_chunks**: Merges adjacent free memory chunks in a `ChunkList`.
- **allocate_memory**: Allocates memory from the heap, splitting and merging chunks as necessary.
- **free_memory**: Frees allocated memory and returns it to the list of free chunks.

### Garbage Collection

- **mark_reachable_region**: Marks memory regions as reachable during garbage collection.
- **garbage_collect**: Performs mark-and-sweep garbage collection to reclaim unused memory.

### Helper Functions

- **dump_chunks**: Prints the memory chunks in a `ChunkList`.
- **find_chunk**: Finds a memory chunk in a `ChunkList`.
- **remove_chunk**: Removes a memory chunk from a `ChunkList`.

### Example Usage

The `main` function demonstrates how to allocate and free memory, as well as perform garbage collection. It includes test cases to illustrate the functionality of the memory allocator.

## Example Output

During execution, the program will output the current state of allocated and free memory chunks, as well as the result of garbage collection. Here's an example snippet of the output:

