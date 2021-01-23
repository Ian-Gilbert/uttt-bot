# UTTT Bots

An API to make bot moves on Ultimate Tic Tac Toe game.

## Bot Options
This game features multiple difficulty levels of AI to play against. These are outlined below:

### Minimax (Beginner Difficulty)
The easiest bot uses the very well-known minimax algorithm to solve a standard tic tac toe board. For each move, the bot checks if the next local board has been determined. If not, it uses the minimax algorithm to decide which board to play on. Once it has the board, it again uses the minimax algorithm to choose its space on the board.

The minimax algorithm works very well for standard tic tac toe, where the entire game is solved very quickly and a simple heuristic function (reward/punishment for win, lose, draw) can be applied. This is not so easy for ultimate tic tac toe, because the high branching factor makes the algorithm take an unreasonably long time to complete. This is usually solved by using a heuristic function that attempts to estimate the value of a position without needing to reach a leaf node, however this bot bypasses the issue entirely by only performing the algorithm on isolated standard boards. As a result, it cannot make strategic descisions as to where it wants to send or avoid sending its opponent. It can also make very predictable moves, which makes it relatively easy to exploit by anticipating only a move or two in advance. This is a necessary skill in order to improve in ultimate tic tac toe, and so this is an ideal entry level bot.

### Monte Carlo Tree Search (Variable Difficulty)
The Monte Carlo Tree Search is an algorithm that efficiently searches through the game tree for the best move. Like minimax, there is no way to run through the entire tree in a reasonable amount of time, so instead it holds the current best move based on the branches checked so far, and updates it as it searches through the tree. This means that we can vary the difficulty of the bot by adjusting the time it has to find the best move. The shorter the limit, the worse a guess it will be.