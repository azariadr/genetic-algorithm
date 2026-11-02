# Genetic Algorithm for Function Optimization

This repository contains an implementation of a Genetic Algorithm (GA) to optimize the values of six weights ($w_1$ through $w_6$) in order to maximize the following linear function:

$$
y = w_1x_1 + w_2x_2 + w_3x_3 + w_4x_4 + w_5x_5 + w_6x_6
$$

With constant input values:
$$
(x_1, x_2, x_3, x_4, x_5, x_6) = (3, -1, 4.5, 6, -10, -5.7)
$$

The boundary for each weight ($w$) is between -4.0 and 4.0. The theoretical maximum limit that can be achieved from this equation is 120.8.

## How It Works

This genetic algorithm mimics the process of natural evolution through the following stages:

1. **Initialization**: An initial population of 30 random solutions (chromosomes) is generated with gene values between -4.0 and 4.0.
2. **Evaluation**: The fitness value of each solution is calculated using a sum-of-products fitness function.
3. **Selection**: The best solutions are randomly selected using a fitness-based weighted method to serve as parents.
4. **Crossover**: Combines genes from parent pairs to produce new offspring (using a single-point crossover method in the middle).
5. **Mutasi**: Memberikan variasi acak kecil pada gen anak yang dihasilkan agar tidak terjebak pada solusi optimum lokal.
6. **Substitution**: Replaces the less fit old population with selected parents and newly mutated offspring.
7. **Termination**: The algorithm stops after reaching the specified number of generations (default: 100 generations).

## Code Structure

* `cal_pop_fitness`: Function to calculate population fitness.
* `select_mating_pool`: Parent selection using fitness-proportional probability.
* `crossover`: Performs gene crossover from parents.
* `mutation`: Performs gene mutation with boundary constraints.
* `run_ga`: Wrapper function to run a full cycle of the genetic algorithm.
* `run_experiment`: Runs experiments to observe the effect of GA parameters on the final results.

## Parameter Experiment Results

We conducted tests with 20 random runs to see the effect of parameter changes on the convergence rate:

### 1. Effect of Number of Mutations per Offspring (`num_mutations`)
* **`num_mutations = 1`**: Average final fitness 116.63 (~96.5% of max limit).
* **`num_mutations = 3`**: Average final fitness 116.63 (~96.5% of max limit).
* **`num_mutations = 5`**: Average final fitness 113.10 (~93.6% of max limit).

### 2. PEffect of Number of Selected Parents (`num_parents`)
* **`num_parents = 2`**: Average final fitness 112.02 (~92.7% of max limit).
* **`num_parents = 4`**: Average final fitness 117.15 (~97.0% of max limit).
* **`num_parents = 8`**: Average final fitness 119.27 (~98.7% of max limit).

## Usage

### Prerequisites
Make sure you have installed the required Python libraries:
```bash
pip install numpy matplotlib
```

### Running the Program
1. Open this notebook file (`.ipynb`) in Google Colab or Jupyter Notebook.
2. Run all cells sequentially.
3. The final results, including visualizations of the fitness progression chart and parameter comparisons, will be displayed directly at the bottom of the notebook.
