Ultimate TTT Game

Jesus Jimenez CS2336.002

Things done

The program succesfully creates a board which contains 9 smaller boards which each contain 9 boxes. The boxes are initialized with a dash '-'
that can be modified with marks X or O by the players. The players uses polimorphism since the HumanPlayer class and the ComputerPlayer class
are an extension of the APlayer abstract class. The program also succesfully checks when a box is full, when a small board is full, and when
the big board is full. With this informatio, the program can notify the player with error messages when they attempt to make a move in a full
box, board, or when there is a draw. The program also checks for valid input from the user, which should be a number 1-4 to choose a game mode,
and a number from 0-8 when choosing a board or a box. The program succesfully finds out when a player wins a board and keep the data for later
to check if a player wins the game. It also allows to keep making moves in available boards that have been won by a player without modifying
the status of that board. Finally, the game succesfully prints the board after each move, makes the moves indicated by the AI or a human, and
can find when someone wins the game or is a draw.

Program Details

	DriverUltimateTTT

~ main method
This class contains the main method which initialize the game by calling the stat ethod from the Game class

	Game

This class uses a Scanner object to get input from the user. It has several attributes which include an array of size 2 for player1 and player2,
an array of strings which contains the marks for each player, a bigBoard object, a variable for the size of the game which is 9 beacuse the game
has 9 small boards, a variable gameScoreToWin initialized with a 3 to find when a player wins, a currentPlayerIndex to keep track of the player
that is making a move, a boardNum variable to keep track of the board number choosen by a player, a boxNum variable to keep track of a box number
choosen by a player.
~Game method
This method initializes the game by setting the players and the big board
~setBoard
This method sets the BigBoard
~setPlayers
This method set the default players, which are two AI players
~setPlayers(APlayer, APlayer) 
This method set specific players. It assigns player1 and two to a location in the players array
~start
This method starts the game. First it displays the welcome message. Then it asks the user to select a game mode between 4 game modes (human vs human,
Human vs AI, AI vs Human, AI vs AI). After that the empty board is printed and the program asks the player 1 to choose any board to make a move. Then,
with a do while loop, the program will iterate to switch players, make moves and print the board until a player wins or there is a draw. Inside the loop,
the program will check if there is a winner using the corresponding method, then it will check if there is a tie, then it will switch players. At this
point with the help of a if statement, the program will check if the small board selected is full. If it is full, the program will ask for an input to
choose any available board to make the next move. The program will check if the input is valid. After that, or if the board is not full, the program will
ask for a box number to make the next move. The program will check for vald input. Then, if all the input is correct, the program will make the move
desired by the player and will assign the next board with the same number as the previous box number move. Finally the program will print the board
including the new move, and it will iterate again.
~switchPlayer
This method switch the player by comparing its indexes. index 0 is player1 so if the program detects the index, it switches to index 1 which is
player2, and viceversa.
~checkTie
This method displays a draw message and ends the program if it is detected that the big board is full.
~checkWinner
This method checks if tere is a winner in the game. With the help of the loop, it checks if a row or column is taken by player1 or player2. After
te loop, the program checks the diagonals. The program ends if is found that someone wins.
~welcome
this metod displays the welcome mesage and a sample board.
~gameMode
This method checks the mode of the ame using a switch statement. 1 for Human vs Human, 2 for Human vs AI, 3 for AI vs Human, and 4 for AI vs AI.

	BigBoard

This class contains an array of 9 boards and an array of status, which keeps track of the status of each board.
~BigBoard
This method sets the board by calling the methos that creates a board.
~init
This method creates 9 boards and put them in the boards array.
~print
This method prints the board. It uses a while loop to print each of the 81 boxes that makes the board. With the help of if statements, the program
prints the box dividers, and board dividers in the correct position.
~bBoardFull
This method checks if the big board is full by checking if all the small boards are full.
~getMark
This method gets the mark from a box from a small board.
~getStatus
This method get the status of a small board.

	Board

This class contains an aray of 9 boards, a variable boardNum which is the number of a specifi board, and a scoreToWin number = 3, which is used to check
for a winner of the board.
~Board
This method sets the board by setting the board number and using the nint method to generate a board object witch 9 boxes.
~makeMove
This method makes a move in a specific box.
~sBoardFull
This method checks if the board is full by checking that all the boxes of the board are available.
~getMark
This method gets the mark of a specific box.
~boardWinner
This method checks if a player wins the board and returns the status of the board. With the help of a loop, the program checks if 3 consecutive rows or
columns are market by player1 or player2. After the loop, the program checks the diagonals.

	Box

The box has a boxNum as an attribute which is the number of the box. Ith also has a placeHolder which is the mark. The box is initialized with a dash as a mark.
~Box
This method sets a box by setting the box number.
~getPlaceHolder
This method returns the value of the place holder of the box.
~setPlaceHolder
This method sets the value of the place holder with a mark of a player if the box is available.
~isAvailable
This method checks if the box is available by checking that the mark of the box is a dash.

	APlayer

This is an abstrac class. It has name and mark as attributes.
~APlayer
This method can be used to set a player.
~getName
It gets the name of the box.
~setName
It sets the name of the box.
~getMark
It gets the mark of the box.
~setMark
It sets the mark of the box.
This class also has abstrac methods which are:
~selectBoardValue
To select a board.
~selectBoxValue
To select a box.

	ComputerPlayer

This class extends APlayer.
~ComputerPlayer
It sets a ComputerPlayer with a name and mark.
~randomNum
It generates a random number 0 - 8.
~selectBoardValue
It overrides the method and returns an random number 0 - 8.
~selectBoxdValue
It overrides the method and returns an random number 0 - 8.

	HumanPlayer

This class extends APlayer
It uses a Scanner object to get input from the user.
~HumanPlayer
This method sets a HumanPlayer with a name and mark.
~selectBoardVale
override
This method is used to get a board value from the user. The method uses a loop to check for valid data.
~selectBoxdVale
override
This method is used to get a box value from the user. The method uses a loop to check for valid data.

	Mark

This enumerator set the marks for each player, which are X and O, and also set the dashes - or the boxes.


Things not done

There are a few things that this project does not include. The first thig is that the AI is not smart. The AI will choose a random number
between 0 and 8 to make moves when choosing a board or a box. This is explains why when the AI is playing and the board is getting full
many error messages appear saying that the board or box chosen is not available.
Another thing that was not implemented in the code was a display message to show the status of the small boards to the players. The status
of each board is only used in the code for checking if there is a winner, but is not used to display and let the user know if a small board
has already been won by a player.
One more thing to be aware of is that the method boardWinner in the Board Class is hardcoded. That means that the Mark enumerator was
not used to check for boxes market X or O.