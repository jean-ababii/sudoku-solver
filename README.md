# sudoku-solver

## Goal
This project presents a python implemented solution to solve 9x9 sudokus. 

## Quick reminder of the rules of the game
From https://sudoku.com:

"Sudoku is played on a grid of 9 x 9 spaces. Within the rows and columns are 9 “squares” (made up of 3 x 3 spaces). Each row, column and square (9 spaces each) needs to be filled out with the numbers 1-9, without repeating any numbers within the row, column or square."

Learn more here: https://sudoku.com/how-to-play/sudoku-rules-for-complete-beginners/

## How this program works

My solution is able to solve sudoku grids by considering two main objects: a grid array which represents all the positions of the grid with their value or a 0 if the correct value is unknown, and a possibilities array which represents all the remain possibilities for each position. The program removes the impossible values from the possibilities array until there is only one value left, and then fills the grid. 

This program can solve grids considering that the player doesn't need to make suppositions, and trying to guess some values. By testing on grids coming from https://www.e-sudoku.fr/, it is able to solve grids from the *easy*, *medium* and *hard* categories, but the program is not able to finish *demoniac* and *diabolic* grids.

##  Possible Improvements

- Making a friendly user interface 
- Testing the validity of the grid entered by the user
- If the program stops without solving the grid, trying to guess some values to see if it works or coming back to try the others possibilities
