# py-sudoku
Module with methods to read, solve and write 9x9 sudokus.

Given a sudoku 9x9 board, where the zeros `0` indicate an empty cell that has to be solved:
```
407901008
003000000
010070300
500026030
032000085
004000009
070304900
006000070
340002000
```

The `read_sudokus` method can read a set of boards from a text file and transform them into a list of sudoku `Board` objects:
```
sudokus = read_sudokus(".\\sudokus\\sudokus-expert.txt")
for sudoku in sudokus:
    print(f'Non-empty cells: {81 - sudoku.count_empty_cells()'})
    sudoku.print_board()
```

You can generate variations of a given sudoku using different techniques: mirroring the board (vertically and horizontally), rotating it, randomly changing the numbers (cipher) or swaping rows and columns within a block:
```
sudoku.vertical_mirroring()
sudoku.horizontal_mirroring()
sudoku.rotate()
sudoku.cipher()
sudoku.swap_rows(0, 2)
sudoku.swap_columns(7, 8)
```

Then, you can write the modified board and its solution into a text file:
```
write_sudoku_with_solution(board=sudoku, filename: "s-1.txt")
```

Also, you can solve a board and print it directly, without writing an output file:
```
sudoku.solve()
sudoku.print_board()
```