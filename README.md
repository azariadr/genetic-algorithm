# Genetic Algorithm for Function Optimization

This code implements a genetic algorithm to find the optimal values of six weights (w1 to w6) that maximize the following equation:
y = w1x1 + w2x2 + w3x3 + w4x4 + w5x5 + w6x6
where (x1, x2, x3, x4, x5, x6) = (3, -1, 4.5, 6, -10, -5.7)

## How it Works

The genetic algorithm works by simulating the natural evolution process. Here are the steps involved:

1. **Initialization:** An initial population of random solutions is created.
2. **Evaluation:** Each solution is evaluated using a fitness function.
3. **Selection:** The best solutions (with the highest fitness) are selected as parents for the next generation.
4. **Crossover:** The parents are combined to produce new offspring.
5. **Mutation:** The new offspring undergo random mutations to introduce variation.
6. **Evaluation:** The new offspring are evaluated using the fitness function.
7. **Replacement:** The old population is replaced with the new population consisting of the newly generated offspring.
8. **Termination:** The algorithm is stopped when a termination condition is met (e.g., the maximum number of generations is reached).

## Usage

1. Make sure you have the NumPy and Matplotlib libraries installed.
2. Run the code in Google Colab or Jupyter Notebook.
3. The code will display the best solution and its fitness.
4. The code will also display a plot of the best fitness over iterations.

## Parameters

You can change the parameters of the genetic algorithm such as the population size, the number of parents, and the mutation rate. These parameters can be found at the top of the code.
