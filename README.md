# packing-optimization

Decides which pallets to load onto a truck to carry the most value without going over its weight limit — the classic knapsack problem, solved three different ways and compared.

## What it does

Given a set of pallets (each with a weight and a profit) and a truck capacity, it selects the subset that maximises profit within the limit, using three approaches so their trade-offs can be compared:

- **Greedy** — fast, approximate.
- **Dynamic programming** — exact optimum.
- **Integer linear programming** — an exact solver written separately in Python.

It runs against several datasets and checks its answers against the known optimal solutions.

## Stack

C++ with CMake for the greedy and dynamic-programming solvers; Python with [PuLP](https://coin-or.github.io/pulp/) for the ILP solver. Datasets and expected solutions in CSV/TXT.

## How to run

```bash
mkdir build && cd build
cmake .. && make
./main                          # greedy and dynamic programming

python3 ilp_solver.py <dataset> # the ILP solver (needs: pip install pulp)
```

## What I built

Group project for the Algorithm Design course (2024/25), built through pair programming — we worked together and the commits landed on a teammate's repository, so the git history here does not split cleanly by author. My contribution is in the solver code alongside my teammates.

## What I would do differently

Add timing across the dataset sizes to show where dynamic programming overtakes the greedy approach and where the ILP solver stops being practical, and write the comparison out as a single table.
