Features and Approach

1.	MILP Formulation:
The problem is modeled with decision variables:
	•	 x_{ij} : 1 if a tower is placed in region (i, j), 0 otherwise.
	•	 y_{ij} : 1 if region (i, j) is covered by at least one tower, 0 otherwise.
Constraints are defined to ensure that coverage is valid and the number of towers does not exceed the budget.
2.	Implementation Details:
	•	Input Data:
	•	populations.txt: Contains the population for each cell in the city grid.
	•	Key Function: A Python function cell_tower_coverage_problem(populations_file, T) implements the optimization logic, taking the population data and maximum tower count as inputs.
	•	Optimization Engine: The solution leverages CPLEX, a powerful solver for linear and mixed-integer programming problems.
	•	Interactive Notebook: The solution was developed in a Python notebook environment, enabling step-by-step debugging and visualization during development.
3.	Steps to Solve:
	•	Read the population data and define the city grid dimensions ( H * W ).
	•	Formulate the MILP problem with objectives and constraints based on the data.
	•	Use CPLEX to solve the problem and identify the optimal tower placements.
	•	Return the decision variables and the total population covered.
The output includes:
	•	Locations of the towers ( x_{ij} ).
	•	Total population covered ( y_{ij} ).
	•	Detailed results showcasing coverage efficiency and resource allocation.


 A Matrix Implementation:
	•	Splited into three different sub-categories.
   	1. Main A matrix
      • We have to split the x and y variables due to the index formula " i*W + j ".
      • By using " for di, dj in [(0, 0), (-1, 0), (1, 0), (0, -1), (0, 1)] ", we find every neighbour that location has.
      • By using the formula " i*W + j ", we can find what column it represents from x{ij} form.
        • In this problem we have W,H = 6,4, so let's say we are trying to find what column x_2_3 belongs to. Since indexing starts from 0, we have to use the formula as i = 1, W = 4, j = 2.
          • From this equation, column index is equal to 1*6+2 = 8. 
            • What this shows as that, as in A matrix, it goes like: x11(0th col), x12(1st col), x13(2nd col), x14(3rd col), x15(4th col), x16(5th col), x21(6th col), x22(7th col), x23(8th col).
            • We append every neighbour's row, col, data index
    2. Right-side of the matrix A (-y{ij} part)
      • It goes diagonally -1 until the end.
    3. Last row of the matrix A
      • We sum up every x variable
      • <= T
