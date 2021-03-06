# Python Fundamentals

**Overview**

The purpose of this document is demonstrate Python programming fundamentals and save time by replace the need for a live technical assessment.  I wrote a game of tic-tac-toe in Python based on a challenge in the Python Institute's basic certification course.  You will observe a wide range of Python and coding practices such as docstrings, logging, functions, basic operations, data storage formats, and logical expressions such as if/else and while statements.

## Tic-Tac-Toe Game

This is based on a Python Institute Challenge. It is written for Google Colab/Jupyter Notebook execution.  It is a monlithic program written entirely in Python and leverages standard python libraries as well as the random, sys, logging, and datetime libraries.

**Game Overview**

The classic game of tic-tac-toe.  The board is, first, printed on screen with a number representing each square from 1-9. The computer always makes the first move by entering an 'X' in the center square.  The player, then, selects an available square by indicating the  number listed on their chosen square.  An 'O' is entered in the square they select.  With the computer's remaining moves, a random square is selected from the remaining available squares.  Turns are alternated until a winner is achieved by either player obtaining 3 of their letters in-a-row.  The available ways to win are up-and-down, across, or diaganally.  When a winner is achieved a message prints on screen saying who won and that the game is over.


Here is a list of the steps used to generate the application from a functional perspective.  Each function in the application is noted and called within each step.  The step, also, contain a short description of what the function does:

**Functional programming steps:**
1. Call new_game and set the sign to X (Pc's move) and build the board.
2. Call display_board and draw a new game on screen.
3. Call draw_move and get the pc's move.  1st move is always 5.
4. Call display_board and draw pc move on screen.
5. Call make_list_of_free_fields and check if their selection is valid.
6. Call display_board and draw pc move on screen.
7. Call victory_for and check if the player or pc won the game.
8. Call enter_move and ask player for a move and update board with their selection.
        Call enter_move again and ask for a new selection if their selection is invalid.
9. Call display_board and draw player's move on screen.
10. Call make_list_of_free_fields and check if their selection is valid. 
11. Call display_board and draw the board with the player's move.
12. Call victory_for and check if the player or pc won the game.  
        If X' or O' won print winner.  The game is over.
13. If no winner, repeat steps 1-12 until game is over.

*Here is a diagram containing the order in which each function is called for the PC or Player's move:*

#### **Function Workflow:**
**Computer turn:** new_game -> display_board ->  draw_move -> display_board -> make_list_of_free_fields -> display_board -> victory_for

**Player turn:** enter_move -> display_board -> make_list_of_free_fields -> display_board -> victory_for -> draw_move

## Game Play

Here is the game play in action.  The game board and PC's first move is immediately printed.  The player enters a number for each of their chosen moves.  The PC and the player alternate moves until the game is over.  THe player wins in this short video.

<img src="tictactoe.gif" height="400" width="1200">

### Logging

Simplified logging function with a custom entry that can be placed anywhere in the application.  This method is useful for debugging, generating business-focused data, and audit trails:

![Logging1](logging1.png)


Logging configuration with a timestamp set to info.  The logged entries will be saved to a file called myapp.log:

![Logging2](logging2.png)


Example logging entires in logged file 'myapp.log':

![Logging3](logging3.png)

### Functions, Loops, Logical Expressions and Basic Operations

Function to build and draw the board on screen.  The intital board contains values from 1 through 9.  The computer's intitial move is drawn to the screen at square 5.  The function has a 'For' statement that creates the unique rows needed to draw the board and leverages arrays to populate the variable information on the board.  You can see proper use of docstrings here.

![function1](function1.png)


This function adds each unique row of the board to a variable then builds the board from these variables then prints them to the screen.  The function flips the sign  from 'X's" to "O's" which is used to signify who's turn it is.  Next, the function calls 'victor_for'.  The victor_for' is a function that determines if a player has scored 3-in-a-row. The game is ends when one player scores 3-in-a-row.  If there is no winner, then this function calls a distinct function for each player that handles each their move.  This example demonstrates basic operations, data types, and logical expressions including if/else statements.

![function2](function2.png)


Here is the output of the function:  An empty board and the first move by the PC are printed to the screen.  An "X" is placed at position 5.

![functionresult](functionresult.png)

### Space & Time Complexity - Big O

Here are 2 examples, when expressed in BigO time complexity notation (worst case scenario) are both O(n).  Their space complexity is O(1):

## Example 1
**Time Complexity:**. A set operation with a logical expression.  The set operation is O(1). The 'for' logical expression iterates through a finite list of 9 values which is a linear operation.  This operation is O(n).  Since Big O notation represents the worst case scenerio, this function has a Big O representation of O(n). 

**Space Complexity:**. The space complexity is O(1) as the set operation requires constant storage space.

![setOperationBigO](setOperationBigO.png)


## Example 2
The finite list of lookup values that represent the winning board combinations are represented as a list of tuples:

![linearlookupBigO1](linearlookupBigO1.png)

**Time Complexity:**  A while statement, that loops through the possible winning combinations, is called. If a winning combination is determined to be true (and if the sign is set to the player) the application prints that the game has ended and the player won.  If the sign that represents the PC is set then the application prints that the PC won and the game is over.  The print functions are O(1) operations as they take the same time to complete with each call.  The if and when statements are linear expressions which are, in Big O notation, O(1).  Because the worst case amongst all operations is O(1), this function will perform in O(1) Big O representation.

**Space Complexity:**. The print and variable set operations require constant space.  This function has a space complexity represented as O(1).

![linearlookupBigO2](linearlookupBigO2.png)
