

# Implementacia simplexovej metody


```c
#include <stdio.h>

#define NUM_CON 3 // toto su riadky tabulky
#define NUM_VAR 4 // toto su stlpce tabulky

int find_pivot_column(double tableau[NUM_CON][NUM_VAR])
{
	int pivot_col = 1;
	for (int j = 2; j < NUM_VAR; j++)
	{

		// Tu najdi minimalny prvok
		if (tableau[NUM_CON - 1][j] < tableau[NUM_CON - 1][pivot_col])
		{
			pivot_col = j;
		}
	}
	return pivot_col;
}

int find_pivot_row(double tableau[NUM_CON][NUM_VAR], int pivot_col)
{
	int pivot_row = -1; // toto je len init pre moj var
	int min_ratio = -1; // toto je len placeholder

	for (int i = 0; i < NUM_CON; i++)
	{
		if (tableau[i][pivot_col] > 0)
		{
			double ratio = tableau[i][NUM_VAR - 1] / tableau[i][pivot_col];
			if (min_ratio == -1 || min_ratio > ratio)
			{
				min_ratio = ratio;
				pivot_row = i;
			}
		}
	}
	return pivot_row;
}

void simplex_method(double tableau[NUM_CON][NUM_VAR])
{
	while (1)
	{
		int pivot_col = find_pivot_column(tableau);
		if (pivot_col == 1)
		{ // TODO: skontroluj ci je chyba v knihe, preco 1?
			printf("Solution found \n");
			break;
		}
		int pivot_row = find_pivot_row(tableau,pivot_col);

		if (pivot_row == -1)
		{
			printf("Unbounded solution \n");
			break;
		}

		double pivot_element = tableau[pivot_row][pivot_col];

		for (int j = 0; j < NUM_VAR; j++)
		{
			tableau[pivot_row][j] /= pivot_element;
		}

		for (int i = 0; i < NUM_CON; i++)
		{
			if (i != pivot_row)
			{
				double factor = tableau[i][pivot_col];
				for (int j = 1; j < NUM_VAR; j++)
				{
					tableau[i][j] -= factor * tableau[pivot_row][j];
				}
			}
		}
	}
}

int main()
{
	double tableau[NUM_CON][NUM_VAR] = {
        {0, -1, -3, 0},    // Objective function row
        {4,  2,  1, 4},    // Constraint 1 row
        {1,  1,  2, 2}     // Constraint 2 row
    };
	simplex_method(tableau);

}

```