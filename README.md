# sudoku-solver

## Goal
This project presents 2 python implemented solution to solve 9x9 sudokus: the first one is based on the game constraints, and the second one test each possibility recursively. 

## Quick reminder of the rules of the game
From https://sudoku.com:

"Sudoku is played on a grid of 9 x 9 spaces. Within the rows and columns are 9 “squares” (made up of 3 x 3 spaces). Each row, column and square (9 spaces each) needs to be filled out with the numbers 1-9, without repeating any numbers within the row, column or square."

Learn more here: https://sudoku.com/how-to-play/sudoku-rules-for-complete-beginners/

## How this program works

### 1st solution: Based on the game constraints

This solution is able to solve sudoku grids by considering two main objects: a grid array which represents all the positions of the grid with their value or a 0 if the correct value is unknown, and a possibilities array which represents all the remain possibilities for each position. The program removes the impossible values from the possibilities array until there is only one value left, and then fills the grid. 

This program can solve grids considering that the player doesn't need to make suppositions, and trying to guess some values. By testing on grids coming from https://www.e-sudoku.fr/, it is able to solve grids from the *easy*, *medium* and *hard* categories, but the program is not able to finish *demoniac* and *diabolic* grids.

### 2nd solution: Recursive solution

This solution was based on Computerphile's one. Everything is explained in this video: https://www.youtube.com/watch?v=G_UYXzGuqvM&ab_channel=Computerphile

This solution consists in trying to guess avalue and then going one to solve the remaining blanks. If for a blank, there is no possible solution, it means that we are in a dead end so we backtrack and try another value where we guessed. It is a recursive method. Compared to the first method, it only needs a grid. This solution is also way easier to implement than the one based on the constraints.

This program can solve any difficulty of grid since it will try all the possible combinations.

## Performance comparison

Since the second method will just try to guess, it will probably be slower than the first one. However, in the first method, the succession of the operations is probably not optimal. It's interesting to compare their runtime on the same grids:

| Grid | EASY_GRID_1 | EASY_GRID_2 | MEDIUM_GRID_1 | HARD_GRID_1 |
| --- | --- | --- | --- | --- |
| Time of constraint-based method | 0.015 | 0.037 | 0.024 | 0.022 |
| Time of recursive method | 0.037 | 0.020 | 0.098 | 0.053 |

To conclude, the recursive method seems indeed slower but somehow it performed better for the EASY_GRID_2. Therefore, more tests are necessary to conclude about a real performance difference or not.

##  Possible Improvements

- Making a friendly user interface 
- Testing the validity of the grid entered by the user
- Trying to combine both methods, so if the program gets stuck with the constraint method, try to guess, continue or backtrack...
