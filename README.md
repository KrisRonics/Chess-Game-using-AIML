# Chess-Game-using-AIML
Chess Game Summary
Introduction
This document summarizes the implementation of a chess game using Python, focusing on the logic and engine integration using AI and Machine Learninfg
Libraries Used
- **Python Chess**: A chess library for handling chess board states, moves, and rules.
- **Stockfish**: An open-source chess engine that provides strong AI capabilities for evaluating positions and suggesting moves.
Setting Up the Chess Board
To set up the chess board, we use the `chess` library, which allows us to create a new board and manipulate it. The board is represented in Forsyth-Edwards Notation (FEN) and supports legal move generation, validation, and checking the game state.
Example Code for Board Setup

import chess

# Initialize a new chess board
board = chess.Board()

# Display the initial board
print(board)

Integrating the Stockfish Engine
The Stockfish engine is integrated to provide AI capabilities for the chess game. The engine can be invoked to analyze positions and suggest optimal moves.
Example Code for Engine Integration

import chess.engine

# Path to the Stockfish executable
engine = chess.engine.SimpleEngine.popen_uci("path/to/stockfish")

# Example: get the best move from the current position
result = engine.play(board, chess.engine.Limit(time=2.0))
print("Best move:", result.move)

# Quit the engine after use
engine.quit()

Chess Logic and Move Handling
The chess logic includes functions for making moves, checking for legal moves, and determining the game's status (e.g., check, checkmate, stalemate). The `chess` library handles most of these functionalities.
Example Code for Move Handling

# Making a move on the board
move = chess.Move.from_uci("e2e4")  # Example move: Pawn to e4
if move in board.legal_moves:
    board.push(move)  # Make the move

# Display the updated board
print(board)

Conclusion
This summary outlines the key components of a chess game implemented in Python, focusing on the logic and integration of the Stockfish chess engine. By leveraging the `chess` library and Stockfish, a robust chess game can be created that provides AI-assisted gameplay.
