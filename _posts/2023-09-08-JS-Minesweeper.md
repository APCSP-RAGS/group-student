---
toc: false
comments: true
layout: post
title: JS Minesweeper game
description: We made the famous game, a classic for all programmers, Minsweeper!
type: hacks
courses: { compsci: {week: 3} }
---

<html>


<style>
    .container {
    text-align: center;
}

#board {
    display: grid;
    grid-template-columns: repeat(10, 30px);
    gap: 2px;
    margin: 20px auto;
}

.cell {
    width: 30px;
    height: 30px;
    background-color: #ccc;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

#restart {
    margin-top: 20px;
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}
</style>



<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minesweeper</title>
</head>
<body>
    <div class="container">
        <h1>Minesweeper</h1>
        <div id="board"></div>
        <button id="restart">Restart</button>
    </div>
</body>

<script>
    document.addEventListener("DOMContentLoaded", function () {
    const board = document.getElementById("board");
    const restartButton = document.getElementById("restart");
    const size = 10; // Adjust the size of the board as needed
    const bombCount = 20; // Adjust the number of bombs as needed
    let cells = [];
    let bombs = [];

    // Initialize the board
    function initBoard() {
        cells = [];
        bombs = [];
        board.innerHTML = "";

        // Create cells
        for (let row = 0; row < size; row++) {
            for (let col = 0; col < size; col++) {
                const cell = document.createElement("div");
                cell.classList.add("cell");
                cell.dataset.row = row;
                cell.dataset.col = col;
                cell.addEventListener("click", handleCellClick); // Add click event listener here
                cells.push(cell);
                board.appendChild(cell);
            }
        }

        // Place bombs randomly
        while (bombs.length < bombCount) {
            const randomIndex = Math.floor(Math.random() * cells.length);
            const cell = cells[randomIndex];
            if (!cell.classList.contains("bomb")) {
                cell.classList.add("bomb");
                bombs.push(cell);
            }
        }
    }

    // Handle cell click
    function handleCellClick(event) {
        const cell = event.target;
        if (cell.classList.contains("opened") || cell.classList.contains("flagged")) {
            return;
        }

        if (cell.classList.contains("bomb")) {
            // Game over
            cell.classList.add("exploded");
            revealBombs();
            gameOver();
        } else {
            const row = parseInt(cell.dataset.row);
            const col = parseInt(cell.dataset.col);
            const bombCount = countAdjacentBombs(row, col);
            cell.classList.add("opened");
            if (bombCount > 0) {
                cell.textContent = bombCount;
            } else {
                // Auto-expand if no adjacent bombs
                expandEmptyArea(row, col);
            }
            checkWin();
        }
    }

    // Count adjacent bombs
    function countAdjacentBombs(row, col) {
        let count = 0;
        for (let i = -1; i <= 1; i++) {
            for (let j = -1; j <= 1; j++) {
                const r = row + i;
                const c = col + j;
                if (r >= 0 && r < size && c >= 0 && c < size) {
                    const adjacentCell = cells.find(
                        (cell) => cell.dataset.row == r && cell.dataset.col == c
                    );
                    if (adjacentCell.classList.contains("bomb")) {
                        count++;
                    }
                }
            }
        }
        return count;
    }

    // Expand empty area
    function expandEmptyArea(row, col) {
        const queue = [{ row, col }];
        const visited = new Set();

        while (queue.length > 0) {
            const { row, col } = queue.shift();
            const cell = cells.find(
                (c) => c.dataset.row == row && c.dataset.col == col
            );
            if (!cell || visited.has(`${row}-${col}`)) {
                continue;
            }
            visited.add(`${row}-${col}`);

            const bombCount = countAdjacentBombs(row, col);
            if (bombCount === 0) {
                cell.classList.add("opened");
                for (let i = -1; i <= 1; i++) {
                    for (let j = -1; j <= 1; j++) {
                        const r = row + i;
                        const c = col + j;
                        if (r >= 0 && r < size && c >= 0 && c < size) {
                            queue.push({ row: r, col: c });
                        }
                    }
                }
            } else {
                cell.classList.add("opened");
                cell.textContent = bombCount;
            }
        }
    }

    // Reveal all bombs
    function revealBombs() {
        bombs.forEach((bomb) => {
            bomb.classList.add("revealed-bomb");
            bomb.textContent = "X";
        });
    }

    // Game over
    function gameOver() {
        cells.forEach((cell) => {
            cell.removeEventListener("click", handleCellClick);
            if (cell.classList.contains("bomb")) {
                cell.classList.add("revealed-bomb");
            }
        });
        restartButton.style.display = "block";
    }

    // Check for a win
    function checkWin() {
        const unopenedCells = cells.filter(
            (cell) => !cell.classList.contains("opened")
        );
        const unopenedBombCells = unopenedCells.filter((cell) =>
            cell.classList.contains("bomb")
        );

        if (unopenedBombCells.length === 0) {
            // All non-bomb cells opened; player wins
            unopenedCells.forEach((cell) => {
                cell.classList.add("flagged");
            });
            restartButton.style.display = "block";
        }
    }

    // Restart the game
    restartButton.addEventListener("click", initBoard);

    // Initialize the game
    initBoard();
});

</script>

</html>
