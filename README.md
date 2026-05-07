# Chess-Game-Python

Project Description

A local two-player chess game built with Pygame. It renders a board and sprites, lets players select and move pieces with the mouse, tracks turns, and declares a winner when a king is captured.
What’s Used Inside

Python + Pygame for rendering, input, and the game loop.
Sprite sheet for chess pieces and image assets for the board and window icon located under res/ (loaded by game.py and piece.py).
A simple data model for pieces/board state stored in a nested dict inside chess.py.
Technical Overview

Entry point: main.py instantiates Game and starts the loop.
Game loop & UI flow: game.py manages window setup, menu screen, in-game rendering, and winner screen. It calls into Chess for gameplay logic and rendering.
Board representation: chess.py builds piece_location as a dict of columns (a–h) to rows (1–8), where each entry is [[piece_name, selected_flag, [x,y]]](http://vscodecontentref/3).
Move generation: chess.py computes legal moves per piece type (pawn, bishop, rook, knight, king, queen) using helper methods for diagonal/linear moves.
Input handling: utils.py provides mouse click detection and coordinates. Selection and moves are done via mouse clicks on board squares.
Rendering: piece.py handles sprite-sheet slicing and draws specific pieces by name. game.py draws the board image and UI text.
Turns: Chess.turn uses a simple dict with a single active side, randomized on reset.
Win condition: The game declares a winner when a king is captured (no check/checkmate rules).
Notes / Constraints

No AI opponent; it is a local two-player click-to-move game.
No full chess rules (e.g., check, checkmate, castling, en passant validation beyond capture move logic, promotion).
The loop runs at 5 FPS, which is intentionally slow for input but could be increased if needed.


Chess Board: 
<img width="640" height="640" alt="board" src="https://github.com/user-attachments/assets/587caf60-0a68-4a6e-8c17-213c1d8678a3" />
Chess pieces: 
<img width="500" height="167" alt="pieces" src="https://github.com/user-attachments/assets/125e3330-9993-4d0b-990f-d1525d87f6a0" />
