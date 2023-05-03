Download Link: https://assignmentchef.com/product/solved-cs141-assignment-6-4x4-tic-tac-toe-game
<br>
Write a program that allows two players to play a game of tic-tac-toe on 4×4 board.

Game user interface description:

<ol>

 <li>Two players are playing a game, taking turns to make a move. Player 1 places Xs, and player 2 places Os on the 4×4 board. Player 1 wins when there are three Xs in a row on the game board (player 2 wins when there are three Os). Three Xs (or Os) can appear in a row, in a column, or diagonally across the board. A tie occurs when all of the locations on the board are full, but there is no winner.</li>

</ol>




<ol start="2">

 <li>On each turn the board is being displayed. There is a number of ways to organize better interface with the user. I would prefer to have a board that looks like this:</li>

</ol>

1         2        3         4

5 6 7 8 9 a b c d e f g




When the user wants to make a move, he/she chooses a number (kind of a Hex system), that represents the placement of X or O on the board. Below is sample interaction with a player. Player’s input appears in blue.




1 2 3 4

5 6 7 8 9 a b c d e f g Player 1, make your move =&gt; 9




1 2 3 4

5 6 7 8 X a b c d e f g




Player 2, make your move =&gt; a




1 2 3 4

5 6 7 8 X O b c d e f g




<ol start="3">

 <li>This exchange goes on until one of the players wins or there is a tie.</li>

</ol>




Create a class called TicTacToe that will be handling user input/output and the logistics of the game. The class will have the following private fields:

<ol>

 <li>board – a private two-dimensional array of size 4×4. The board will be storing characters. Initial look of the board is the following</li>

</ol>




<table width="169">

 <tbody>

  <tr>

   <td width="42">1</td>

   <td width="42">2</td>

   <td width="42">3</td>

   <td width="42">4</td>

  </tr>

  <tr>

   <td width="42">5</td>

   <td width="42">6</td>

   <td width="42">7</td>

   <td width="42">8</td>

  </tr>

  <tr>

   <td width="42">9</td>

   <td width="42">a</td>

   <td width="42">b</td>

   <td width="42">c</td>

  </tr>

  <tr>

   <td width="42">d</td>

   <td width="42">e</td>

   <td width="42">f</td>

   <td width="42">g</td>

  </tr>

 </tbody>

</table>




The numbering of the board intentionally starts with 1. Zero is avoided to prevent confusing it with O (a marker of a move).

<ol start="2">

 <li>status – stores game status. There are 2 possibilities here – either still playing or done (game came to an end, someone won)</li>

 <li>winner – stores the info about winning/losing the game. There are 3 possible states here: X won, O won, tie</li>

 <li>whoseTurn –stores who’s turn it is to play now</li>

</ol>




The methods are the following

<ol>

 <li>No-argument constructor that creates the initial setting on the board and gives initial values to all fields.</li>

 <li>Public method printBoard() – prints the current board</li>

 <li>Public method input() – provides the prompt and gathers input from the user. It must prompt the correct player, who’s turn it is now to play, display the board using the printBoard() method, and gather input from the user. Input validation must be provided:

  <ol>

   <li>User must provide a valid character that represents the cell on the board. The user must be asked to provide the character until the valid character has been entered.</li>

   <li>If the place that the user chose has been already taken (X or O already standing there), the method must notify the user and ask for another input. The method must also be taking care of changing the value of field that tracks whose turn it is to play (whoseTurn).</li>

  </ol></li>

</ol>

Do not ignore the need to convert a digit/character into a position in the 2dimentional array. This calls for another algorithm

<ol start="4">

 <li>Public method simulateInput(char player, char letter) –</li>

</ol>

The method is needed for debugging purposes. It simulates a move of a user. The first parameter specifies the player (X or O), the second parameter specifies the move (as a character).

The method must display the board using printBoard() method, and print out what player made a move and where. Data validation must be provided:

<ol>

 <li>If the character provided by parameter is invalid, an</li>

</ol>

IllegalArgumentException with the message describing the issue must be thrown.

<ol>

 <li>If the player specified by parameter is playing out of turn, the</li>

</ol>

IllegalArgumentException with the message describing the issue must be thrown.

<ol>

 <li>If the place on board specified by the parameter has been already taken (X or O already standing there), the IllegalArgumentException with the message describing the issue must be thrown.</li>

</ol>

The method must also be taking care of changing the value of field that tracks whose turn it is to play (whoseTurn).

<ol start="5">

 <li>Public method analyzeBoard() – analyzes the current board and determines if there is a winning position present or if it is a tie. If the state of the game changes, the member variable that is tracking the game state must be changing value, and the info about the winner must be recorded in the field that stores that data.</li>

 <li>Public method done() – accessor for status Method returns true if the game came to the end.</li>

 <li>Public method whoWon() – returns a character (X, O or T – for tie), a value of the winner field</li>

</ol>




Create class named TicTacToeSimulation. The class must contain main().

<ol>

 <li>Create an object of class TicTacToe</li>

 <li>Call printBoard(), simulateInput(),analyzeBoard()to simulate</li>

</ol>

the moves of two opponents. The purpose of this code is to TEST all the methods and make sure your analyzeBoard()algorithm works exactly right. Make sure to simulate the game multiple times to check on all the critical test cases.

<ol>

 <li>Use comments to explain why you chose the particular combination of moves, what part of the algorithm you are testing with the particular test case.</li>

</ol>




<ol>

 <li>Make sure to display the winner each time you think the game must come to an end.</li>

</ol>

<ol start="3">

 <li>Make sure to test input() method too. It should be a separate small test, not a part of the game simulation.</li>

</ol>




Create a class named TicTacToeGame. This class must contain main() and allow two users play the game using keyboard input.




<ol>

 <li>Create an object of class TicTacToe</li>

 <li>In a loop start playing the game, calling printBoard(), input(),analyzeBoard()until done() returns true.</li>

 <li>After that display board for the last time and announce who is the winner.</li>

</ol>





