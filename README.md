
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Snake Game</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #2c3e50;
            color: white;
            font-family: Arial, sans-serif;
        }
        canvas {
            border: 5px solid #ecf0f1;
            box-shadow: 0 0 20px rgba(0,0,0,0.5);
            background-color: #000;
        }
        h1 { margin-bottom: 10px; }
        .score { font-size: 24px; margin-bottom: 10px; }
    </style>
</head>
<body>

    <h1>Snake Game</h1>
    <div class="score">Score: <span id="scoreVal">0</span></div>
    <canvas id="gameCanvas" width="400" height="400"></canvas>

    <script>
        const canvas = document.getElementById("gameCanvas");
        const ctx = canvas.getContext("2d");
        const scoreElement = document.getElementById("scoreVal");

        const gridSize = 20;
        const tileCount = canvas.width / gridSize;

        let score = 0;
        let dx = 0;
        let dy = 0;
        let snake = [{x: 10, y: 10}];
        let food = {x: 5, y: 5};

        // Main game loop
        function draw() {
            updateSnake();
            if (checkGameOver()) return resetGame();
            
            drawBackground();
            drawFood();
            drawSnake();
            
            setTimeout(draw, 100);
        }

        function drawBackground() {
            ctx.fillStyle = "black";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
        }

        function drawSnake() {
            ctx.fillStyle = "lime";
            snake.forEach(part => ctx.fillRect(part.x * gridSize, part.y * gridSize, gridSize - 2, gridSize - 2));
        }

        function drawFood() {
            ctx.fillStyle = "red";
            ctx.fillRect(food.x * gridSize, food.y * gridSize, gridSize - 2, gridSize - 2);
        }

        function updateSnake() {
            const head = {x: snake[0].x + dx, y: snake[0].y + dy};
            snake.unshift(head);

            // Check if snake ate food
            if (head.x === food.x && head.y === food.y) {
                score++;
                scoreElement.innerHTML = score;
                spawnFood();
            } else {
                snake.pop();
            }
        }

        function spawnFood() {
            food.x = Math.floor(Math.
