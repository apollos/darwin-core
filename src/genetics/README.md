# Implement the genetic algorithm for model generation:

## Mutation:
### 1. ALTER-LEARNING-RATE (sampling details below).
### 2. IDENTITY (effectively means “keep training”).
### 3. RESET-WEIGHTS (sampled as in He et al. (2015), for example).
### 4. INSERT-CONVOLUTION (inserts a convolution at a random location in the “convolutional backbone”,  The inserted convolution has 3  3 filters, strides of 1 or 2 at random, number of channels same as input. May apply batch-normalization and ReLU activation or none at random).
### 5. REMOVE-CONVOLUTION.
### 6. ALTER-STRIDE (only powers of 2 are allowed).
### 7. ALTER-NUMBER-OF-CHANNELS (of random conv.).
### 8. FILTER-SIZE (horizontal or vertical at random, on random convolution, odd values only).
### 9. INSERT-ONE-TO-ONE (inserts a one-to-one/identity connection, analogous to insert-convolution mutation).
### 10. ADD-SKIP (identity between random layers).
### 11. REMOVE-SKIP (removes random skip).

## Heredity:
### 1. Different sub-layer merge

## Exchange:
### 1. Define as one of operation of mutation?

## Initialize
### 1. We shall not start from scratch for search