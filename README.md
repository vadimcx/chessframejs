# Chess Board Single File Include

This repository provides a simple and lightweight chessboard component that can be easily included in your web project with minimal setup. With just one file inclusion and a few lines of code, you can have a fully functional chessboard on your website.

## Usage

### 1. Include the Component File and JavaScript File

Copy the `chessboard.js` file from the `/include` directory into your project. Then, include the file in your HTML using a script tag:
```html
<script src="path/to/chessboard.js"></script>
```

### 2. Add a Board Container

Create a div element in your HTML file with the ID and class set to "board":
```html
<div id="board" class="board"></div>
```

### Initialize the Chessboard

You're now ready to start using the chessboard component. Use the provided JavaScript functions to interact with the board.

## Functions Available

- `GAMEMODE`: A flag to toggle piece movement. When set to `false`, piece movement is deactivated. When set to `true`, piece movement is activated.

- `spawnPiece(pieceType, pieceColor, square)`: Spawns a piece of the given type ('K' for king, 'Q' for queen, etc.) and color ('white' or 'black') on the specified square (in long notation, e.g., 'd6').

- `await new Promise(r => setTimeout(r, 2000));`: Pauses execution for 2000 milliseconds, primarily for visualization purposes.

- `clear()`: Clears the board.

- `build()`: Builds the standard starting position.

- `movePiece(fromSquare, toSquare)`: Moves a piece from one square to another.

- `buildFromPosStr(posStr)`: Builds the board position from a given position string.

- `rotateBoard()`: Rotates the board.

## Example

```javascript
// Include the chessboard file
<script src="path/to/chessboard.js"></script>

// Create a board container
<div id="board" class="board"></div>

// Initialize the chessboard
<script>
  // Deactivate piece movement
  GAMEMODE = false;

  // Spawn a white king on square d6
  spawnPiece('K', 'white', 'd6');

  // Pause for visualization
  await new Promise(r => setTimeout(r, 2000));

  // Clear the board
  clear();

  // Build the standard starting position
  build();

  // Move a piece from e2 to e4
  movePiece('e2', 'e4');

  // Example position string
  const posStr = `
  r . b q k b n r 
  p p p p . p p p 
  . . n . . . . . 
  . B . . p . . . 
  . . . . P . . . 
  . . . . . N . . 
  P P P P . P P P 
  R N B Q K . . R`;
  
  // Build position from string
  buildFromPosStr(posStr);

  // Rotate the board
  rotateBoard();

  // Activate piece movement
  GAMEMODE = true;
</script>
```

## Demo

A live demo of the chessboard component can be found [here](https://kosher-code.github.io/chess-board-single-file-include/).

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
