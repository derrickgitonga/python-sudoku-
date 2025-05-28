# Sudoku Solver in Python

This is a simple command-line Sudoku solver written in Python using object-oriented programming. It uses a **backtracking algorithm** to fill in the empty cells and solve any valid 9x9 Sudoku puzzle.

## 🚀 Features

- Solves standard 9x9 Sudoku puzzles
- Implements an efficient backtracking algorithm
- Validates numbers by Sudoku rules (row, column, and 3x3 box)
- Nicely prints the Sudoku board before and after solving

## 🧠 How It Works

The solver follows these steps:
1. **Find an empty cell** (represented by `0`)
2. **Try placing numbers** 1 through 9
3. **Check if the number is valid** according to Sudoku rules
4. **Recursively continue** solving with the new number
5. **Backtrack** if no valid number can be placed

## 📄 File: `sudoku.py`

```python
game = SudokuGame(board)
game.print_board()
print("\nSolving the Sudoku...\n")
game.solve()
game.print_board()
