# Generating call graphs on C code

In my thesis I need to showcase calls of wfa2lib library. The purpose is to create a graph which will show all interconnections of the library. With this information we need to find parts of the library which are isolated enough and are paralelzible so we can rewrite those in CUDA C. 

## Path to Egypt 

The wfa2lib recommend using gcc as the supported compiler. We can