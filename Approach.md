Features and Approach

1. MILP Formulation

The problem is modeled using the following decision variables:
	•	 x_{ij} : Binary variable, 1 if a tower is placed in region (i, j), 0 otherwise.
	•	 y_{ij} : Binary variable, 1 if region (i, j) is covered by at least one tower, 0 otherwise.

Constraints are defined to:
	•	Ensure all covered regions are appropriately linked to tower placements.
	•	Limit the number of towers to the available budget.

2. Implementation Details

	•	Input Data:
	•	populations.txt: A text file containing the population data for each region in the city grid.
	•	Key Function:
	•	cell_tower_coverage_problem(populations_file, T): A Python function that processes the population data and maximum tower count, formulates the optimization problem, and solves it using 		CPLEX.
	•	Optimization Engine:
	•	Utilizes CPLEX to solve the mixed-integer linear programming problem efficiently.
	•	Interactive Notebook:
	•	Developed in a Python notebook for easier step-by-step debugging and visualization.

4. Steps to Solve

	1.	Parse the population data and define the city grid dimensions ( H \times W ).
	2.	Formulate the MILP problem with the objective of maximizing coverage while respecting constraints.
	3.	Use CPLEX to compute the optimal tower placements.
	4.	Output the results, including:
	•	Tower locations ( x_{ij} ).
	•	Total population covered ( y_{ij} ).
	•	Detailed analysis of coverage efficiency and resource allocation.


