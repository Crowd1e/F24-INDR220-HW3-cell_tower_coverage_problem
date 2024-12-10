# F24-INDR220-HW3-cell_tower_coverage_problem
Cell Tower Coverage Problem with CPLEX

This project addresses the Cell Tower Coverage Problem using Python and CPLEX to solve a mixed integer linear programming (MILP) formulation. The objective is to help a telecom company decide the optimal placement of a limited number of cell towers to maximize signal coverage for the population in a city, given constraints on budget and tower range.

Key features of this project:
	•	Problem Overview: The city is divided into a grid, and each cell has a known population. The challenge is to select locations for towers such that the total coverage is maximized within the given constraints.
	•	MILP Formulation: The decision variables include whether a tower is built in a cell and whether a cell is covered by at least one tower. Constraints ensure coverage and respect the maximum number of towers allowed.
	•	Implementation:
	•	populations.txt contains population data for the city grid.
	•	A Python script implements the algorithm to read this data, define the optimization problem, and solve it using CPLEX.
	•	Output: The solution specifies which towers to build and provides the corresponding maximum population coverage.

This repository includes:
	1.	A Python script to solve the problem.
	2.	Population data in populations.txt.

This project is a demonstration of operations research techniques applied to real-world problems in telecommunications.
