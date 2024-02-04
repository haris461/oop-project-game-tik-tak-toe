#code of tic tac toe game 
#include<iostream>
#include<windows.h>
class TicTacToe {
private:
    char board[3][3];
    char currentPlayer;

public:
    TicTacToe() : currentPlayer('X') {
        // Initialize the board with empty spaces
        for (int i = 0; i < 3; ++i) {
            for (int j = 0; j < 3; ++j) {
                board[i][j] = ' ';
            }
        }
    }

    void printBoard() {
        for (int i = 0; i < 3; ++i) {
            for (int j = 0; j < 3; ++j) {
                std::cout << board[i][j] << " | ";
            }
            std::cout << std::endl << "---------" << std::endl;
        }
    }
explain the code

Header Files:

#include<iostream>: This header file is included for input and output operations.
#include<windows.h>: This header file is specific to Windows and is used for console manipulation, including changing text colors.
Class TicTacToe:

Private Members:

char board[3][3]: A 2D array representing the Tic Tac Toe board.
char currentPlayer: A variable to keep track of the current player ('X' or 'O').
Public Methods:

Constructor TicTacToe():

Initializes the board with empty spaces.
Sets currentPlayer to 'X'.
void printBoard():

Prints the current state of the Tic Tac Toe board to the console.
void setColor(char symbol):

A helper method to set the text color based on the symbol ('X', 'O', or empty space).
void resetColor():

A helper method to reset the text color to the default


#code
bool makeMove(int row, int col) {
    if (row < 0 || row >= 3 || col < 0 || col >= 3 || board[row][col] != ' ') {
        return false; // Invalid move
    }

    board[row][col] = currentPlayer;
    currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';
    return true; // Valid move
}

#explain the function



Purpose:

This function is responsible for making a move on the Tic Tac Toe board.
It takes two parameters, row and col, representing the row and column where the current player wants to place their symbol ('X' or 'O').
Conditions:

It checks if the provided row and col are within the valid range (0 to 2) and if the specified cell on the board is empty (' ').
If any of these conditions is not met, the move is considered invalid, and the function returns false.
Updating the Board:

If the move is valid, it updates the board at the specified position with the current player's symbol.
It then toggles the currentPlayer between 'X' and 'O' for the next turn.
Return Value:

The function returns true for a valid move and false for an invalid move.



#function  code

bool checkWin() {
    // Check rows, columns, and diagonals for a win
    for (int i = 0; i < 3; ++i) {
        if (board[i][0] != ' ' && board[i][0] == board[i][1] && board[i][1] == board[i][2]) {
            return true; // Row win
        }
        if (board[0][i] != ' ' && board[0][i] == board[1][i] && board[1][i] == board[2][i]) {
            return true; // Column win
        }
    }

    if (board[0][0] != ' ' && board[0][0] == board[1][1] && board[1][1] == board[2][2]) {
        return true; // Diagonal win
    }

    if (board[0][2] != ' ' && board[0][2] == board[1][1] && board[1][1] == board[2][0]) {
        return true; // Diagonal win
    }

    return false; // No win yet
}


explaination of code

Purpose:

This function checks if there is a winning condition on the Tic Tac Toe board.
Checking Rows and Columns:

It iterates over the rows and columns of the board, checking if there is a winning sequence of 'X' or 'O'.
If any row or column has the same symbol in all three cells and is not empty, it indicates a win.
Checking Diagonals:

It checks both diagonals for a winning sequence.
Return Value:

If any of the checks result in a win, the function returns true. Otherwise, it returns false.
These two functions together handle the logic for making moves and checking for a win in the Tic Tac Toe game. The makeMove function updates the board with the player's move, and the checkWin function determines if the current move leads to a win condition.

#code of function


bool isBoardFull() {
    for (int i = 0; i < 3; ++i) {
        for (int j = 0; j < 3; ++j) {
            if (board[i][j] == ' ') {
                return false; // Board is not full
            }
        }
    }
    return true; // Board is full
}



#explaination of code


Purpose:

This function checks whether the entire Tic Tac Toe board is filled with symbols or not.
Iterating Over the Board:

It uses nested loops to iterate through each cell of the 3x3 board.
Checking for Empty Cells:

If it finds any cell that is still empty (' '), it immediately returns false, indicating that the board is not full.
Return Value:

If the function completes the loops without finding any empty cell, it returns true, indicating that the board is full.





#code of function

char getCurrentPlayer() const {
    return currentPlayer;
}


#explaination of code


Purpose:

This function simply returns the symbol of the current player ('X' or 'O).
Return Value:

The function is marked as const, indicating that it does not modify the state of the object.
It returns the currentPlayer, which is the symbol of the player whose turn it is.
These two functions provide utility in checking the state of the game. The isBoardFull function is often used to check for a draw (when the board is full but there is no winner), and the getCurrentPlayer function helps in displaying information about the current player's turn.





#output of code


![image](https://github.com/haris461/oop-project-game-tik-tak-toe/assets/158203393/71bc70c6-de46-4c2f-bbd7-ba299e6d1622)



![image](https://github.com/haris461/oop-project-game-tik-tak-toe/assets/158203393/9fc53602-af35-46f5-b041-b4d185792f9d)













