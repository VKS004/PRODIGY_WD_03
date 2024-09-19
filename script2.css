const cells = document.querySelectorAll('[data-cell]');
const board = document.getElementById('board');
const gameStatus = document.getElementById('game-status');
const restartBtn = document.getElementById('restartBtn');

let currentPlayer = 'X';
let isGameOver = false;
const winningCombinations = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6]
];

// Initialize the game
function startGame() {
    isGameOver = false;
    currentPlayer = 'X';
    gameStatus.textContent = "Player X's turn";
    cells.forEach(cell => {
        cell.classList.remove('x', 'o');
        cell.textContent = '';
        cell.addEventListener('click', handleClick, { once: true });
    });
}

// Handle cell clicks
function handleClick(e) {
    const cell = e.target;
    const currentClass = currentPlayer === 'X' ? 'x' : 'o';

    placeMark(cell, currentClass);
    if (checkWin(currentClass)) {
        endGame(false);
    } else if (isDraw()) {
        endGame(true);
    } else {
        swapTurns();
        updateGameStatus();
    }
}

// Place the mark (X or O)
function placeMark(cell, currentClass) {
    cell.textContent = currentPlayer;
    cell.classList.add(currentClass);
}

// Swap players
function swapTurns() {
    currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
}

// Update the game status message
function updateGameStatus() {
    gameStatus.textContent = `Player ${currentPlayer}'s turn`;
}

// Check for a win
function checkWin(currentClass) {
    return winningCombinations.some(combination => {
        return combination.every(index => {
            return cells[index].classList.contains(currentClass);
        });
    });
}

// Check for a draw
function isDraw() {
    return [...cells].every(cell => {
        return cell.classList.contains('x') || cell.classList.contains('o');
    });
}

// End the game
function endGame(draw) {
    isGameOver = true;
    if (draw) {
        gameStatus.textContent = "It's a draw!";
    } else {
        gameStatus.textContent = `Player ${currentPlayer} wins!`;
    }
}

// Restart the game
restartBtn.addEventListener('click', startGame);

// Start the game initially
startGame();
