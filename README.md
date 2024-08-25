#
**Name**: Shreyas Patil 
**Registration Number**: 21BCE11682


# Turn-based Chess-like Game with Websocket Communication

## Overview
This project implements a turn-based chess-like game designed for two players. It features a server-client architecture utilizing WebSockets for real-time communication and a web-based user interface. The game is played on a 5x5 grid, where each player controls a team of characters with unique movement patterns and abilities. The goal is to eliminate the opponent's characters, leading to victory.

## Project Structure
The project is organized into the following main components:

- **Server**: Handles game logic, WebSocket communication, and game state management.
- **WebSocket Layer**: Facilitates real-time communication between the server and clients.
- **Web Client**: Provides the user interface for players to interact with the game.

## Game Rules
### Characters and Movement
The game features three types of characters, each with distinct movement patterns:
1. **Pawn**:
   - Moves one block in any direction (Left, Right, Forward, or Backward).
   - Move commands: `L` (Left), `R` (Right), `F` (Forward), `B` (Backward).
2. **Hero1**:
   - Moves two blocks straight in any direction, eliminating opponents in its path.
   - Move commands: `L` (Left), `R` (Right), `F` (Forward), `B` (Backward).
3. **Hero2**:
   - Moves two blocks diagonally in any direction, eliminating opponents in its path.
   - Move commands: `FL` (Forward-Left), `FR` (Forward-Right), `BL` (Backward-Left), `BR` (Backward-Right).

### Game Flow
- **Initial Setup**: Players deploy their characters on their respective starting rows.
- **Turns**: Players alternate turns, making one move per turn.
- **Combat**: Characters eliminate opponents by landing on their occupied spaces.
- **Winning Condition**: The game ends when a player eliminates all of their opponent's characters.

## Technical Implementation
### Server
- Implements the core game logic and handles WebSocket communication.
- Processes moves, validates them, and updates the game state.
- Broadcasts the updated game state to all connected clients after each valid move.

### WebSocket Communication
- **Event Types**:
  - `Game Initialization`
  - `Player Move`
  - `Game State Update`
  - `Invalid Move Notification`
  - `Game Over Notification`

### Web Client
- Displays a 5x5 game board with interactive controls for players.
- Implements WebSocket communication with the server.
- Highlights valid moves for the selected character.
- Displays the current game state, move history, and the active player's turn.

## Installation and Setup
### Prerequisites
- Node.js (for server-side development)
- A modern web browser (for the web client)
