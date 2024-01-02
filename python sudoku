class SudokuGame:
    def __init__(self, board):
        self.board = board

    def print_board(self):
        for i in range(9):
            if i % 3 == 0 and i != 0:
                print("- - - - - - - - - - - -")
            for j in range(9):
                if j % 3 == 0 and j != 0:
                    print("| ", end="")
                if j == 8:
                    print(self.board[i][j])
                else:
                    print(str(self.board[i][j]) + " ", end="")

    def solve(self):
        empty_cell = self.find_empty_cell()
        if not empty_cell:
            return True
        else:
            row, col = empty_cell

        for num in range(1, 10):
            if self.is_valid(num, (row, col)):
                self.board[row][col] = num

                if self.solve():
                    return True

                self.board[row][col] = 0

        return False

    def find_empty_cell(self):
        for i in range(9):
            for j in range(9):
                if self.board[i][j] == 0:
                    return i, j
        return None

    def is_valid(self, num, pos):
        row, col = pos

        # Check row
        for i in range(9):
            if self.board[row][i] == num and col != i:
                return False

        # Check column
        for i in range(9):
            if self.board[i][col] == num and row != i:
                return False

        # Check 3x3 box
        box_row = row // 3
        box_col = col // 3

        for i in range(box_row * 3, box_row * 3 + 3):
            for j in range(box_col * 3, box_col * 3 + 3):
                if self.board[i][j] == num and (i, j) != pos:
                    return False

        return True


# Example usage
board = [
    [5, 3, 0, 0, 7, 0, 0, 0, 0],
    [6, 0, 0, 1, 9, 5, 0, 0, 0],
    [0, 9, 8, 0, 0, 0, 0, 6, 0],
    [8, 0, 0, 0, 6, 0, 0, 0, 3],
    [4, 0, 0, 8, 0, 3, 0, 0, 1],
    [7, 0, 0, 0, 2, 0, 0, 0, 6],
    [0, 6, 0, 0, 0, 0, 2, 8, 0],
    [0, 0, 0, 4, 1, 9, 0, 0, 5],
    [0, 0, 0, 0, 8, 0, 0, 7, 9]
]

game = SudokuGame(board)
game.print_board()
print("\nSolving the Sudoku...\n")
game.solve()
game.print_board()
