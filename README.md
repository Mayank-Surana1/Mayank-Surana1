<h1 align="center">Hey 👋What's Up?</h1>

###

<div align="center">
  <img src="https://skillicons.dev/icons?i=ts" height="60" alt="typescript logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=nextjs" height="60" alt="nextjs logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=tailwind" height="60" alt="tailwindcss logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/storybook/storybook-original.svg" height="60" alt="storybook logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=graphql" height="60" alt="graphql logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=go" height="60" alt="go logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=rust" height="60" alt="rust logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=nestjs" height="60" alt="nestjs logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=py" height="60" alt="python logo"  />
  <img width="12" />
  <img src="https://skillicons.dev/icons?i=aws" height="60" alt="amazonwebservices logo"  />
</div>

###

<div align="center">
  <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="linkedin logo"  />
  <img src="https://img.shields.io/static/v1?message=Twitter&logo=twitter&label=&color=1DA1F2&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="twitter logo"  />
  <img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=7289DA&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="discord logo"  />
  <img src="https://img.shields.io/static/v1?message=Twitch&logo=twitch&label=&color=9146FF&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="twitch logo"  />
  <img src="https://img.shields.io/static/v1?message=dev.to&logo=dev.to&label=&color=0A0A0A&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="devto logo"  />
</div>

###

<div align="center">
  <img src="https://streak-stats.demolab.com?user=maurodesouza&locale=en&mode=daily&theme=dracula&hide_border=false&border_radius=5&order=3" height="150" alt="streak graph"  />
  <img src="https://raw.githubusercontent.com/maurodesouza/maurodesouza/trophy-output/trophy.svg" height="150" alt="trophy graph"  />
</div>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🐍 Dynamic Snake · moving & interactive</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            user-select: none;
        }
        body {
            background: linear-gradient(145deg, #1b2a2c 0%, #0f1a1b 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
            padding: 16px;
            margin: 0;
        }
        .game-wrapper {
            background: #203336;
            padding: 24px 24px 30px;
            border-radius: 48px 48px 32px 32px;
            box-shadow: 0 20px 30px rgba(0,0,0,0.7), inset 0 0 0 1px #4b6a6e;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        canvas {
            display: block;
            background-color: #1d2f32;
            border-radius: 28px;
            box-shadow: inset 0 0 0 2px #2f4a4e, 0 12px 18px rgba(0,0,0,0.5);
            width: 500px;
            height: 500px;
            image-rendering: crisp-edges; /* retro pixel look */
            image-rendering: pixelated;
        }
        .panel {
            margin-top: 22px;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: #c6e2e6;
            text-shadow: 0 2px 0 #0c181a;
            font-weight: 600;
            letter-spacing: 0.3px;
        }
        .score-box {
            background: #142123;
            padding: 10px 24px;
            border-radius: 40px;
            font-size: 1.5rem;
            box-shadow: inset 0 3px 6px #0b1415, 0 4px 0 #2b464a;
            color: #b3e4eb;
            display: flex;
            align-items: center;
            gap: 6px;
        }
        .score-box span {
            font-weight: 300;
            color: #d4f3f8;
            margin-right: 8px;
        }
        .controls {
            display: flex;
            gap: 18px;
            align-items: center;
        }
        button {
            background: #253f43;
            border: none;
            color: #e6f7fa;
            font-size: 1.2rem;
            font-weight: 600;
            padding: 8px 22px;
            border-radius: 40px;
            box-shadow: 0 6px 0 #0d1d1f, 0 4px 10px rgba(0,0,0,0.5);
            transition: 0.08s linear;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 4px;
            letter-spacing: 0.5px;
            border: 1px solid #4d7379;
        }
        button:active {
            transform: translateY(4px);
            box-shadow: 0 2px 0 #0d1d1f;
        }
        button:disabled {
            opacity: 0.5;
            transform: translateY(4px);
            box-shadow: 0 2px 0 #0d1d1f;
            pointer-events: none;
        }
        .hint {
            font-size: 0.95rem;
            background: #1d3134;
            padding: 6px 18px;
            border-radius: 40px;
            color: #aacfd4;
            box-shadow: inset 0 2px 5px #0d1c1e;
        }
        @media (max-width: 540px) {
            canvas { width: 340px; height: 340px; }
            .panel { flex-wrap: wrap; justify-content: center; gap: 12px; }
            .controls { flex-wrap: wrap; justify-content: center; }
        }
    </style>
</head>
<body>
<div class="game-wrapper">
    <canvas id="gameCanvas" width="500" height="500"></canvas>
    <div class="panel">
        <div class="score-box"><span>🍎</span> <span id="scoreDisplay">0</span></div>
        <div class="controls">
            <button id="restartBtn">⟳ restart</button>
            <div class="hint">⬆ ⬇ ⬅ ➡</div>
        </div>
    </div>
</div>
<script>
    (function() {
        // ---------- DYNAMIC SNAKE ----------
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const scoreSpan = document.getElementById('scoreDisplay');

        // Grid settings (20x20 -> dynamic feel with smooth moves)
        const GRID_SIZE = 20;          // 20x20 cells
        const CELL_SIZE = canvas.width / GRID_SIZE; // 25px

        // Game state
        let snake = [];                // array of {x, y}
        let food = { x: 8, y: 8 };
        let direction = 'RIGHT';       // current moving direction
        let nextDirection = 'RIGHT';
        let score = 0;
        let gameOver = false;
        let win = false;
        let gameInterval = null;
        const MOVE_INTERVAL_MS = 130;  // dynamic speed (feels lively)

        // ----- helper functions -----
        function randomInt(min, max) {
            return Math.floor(Math.random() * (max - min + 1)) + min;
        }

        // generate food at empty cell (avoid snake)
        function generateFood() {
            const totalCells = GRID_SIZE * GRID_SIZE;
            if (snake.length >= totalCells) {
                // win condition: snake fills the board
                win = true;
                gameOver = true;
                clearInterval(gameInterval);
                gameInterval = null;
                return false;
            }

            // collect free cells
            const snakeSet = new Set(snake.map(cell => `${cell.x},${cell.y}`));
            if (snakeSet.size === totalCells) {
                win = true;
                gameOver = true;
                clearInterval(gameInterval);
                gameInterval = null;
                return false;
            }

            let freeCells = [];
            for (let i = 0; i < GRID_SIZE; i++) {
                for (let j = 0; j < GRID_SIZE; j++) {
                    if (!snakeSet.has(`${i},${j}`)) {
                        freeCells.push({ x: i, y: j });
                    }
                }
            }
            if (freeCells.length === 0) {
                win = true;
                gameOver = true;
                clearInterval(gameInterval);
                gameInterval = null;
                return false;
            }
            const randIndex = Math.floor(Math.random() * freeCells.length);
            food = freeCells[randIndex];
            return true;
        }

        // reset game to initial state
        function resetGame() {
            // stop any running interval
            if (gameInterval) {
                clearInterval(gameInterval);
                gameInterval = null;
            }

            // initial snake: 4 cells horizontally
            snake = [
                { x: 8, y: 10 },
                { x: 7, y: 10 },
                { x: 6, y: 10 },
                { x: 5, y: 10 }
            ];
            direction = 'RIGHT';
            nextDirection = 'RIGHT';
            score = 0;
            gameOver = false;
            win = false;
            scoreSpan.innerText = '0';

            // generate first food (avoid snake)
            const foodPlaced = generateFood();
            if (!foodPlaced) {
                // extremely unlikely on 20x20 with 4 cells
                food = { x: 12, y: 10 };
            }
            drawCanvas();
            // start the loop again
            startGameLoop();
        }

        // ----- core move: update snake position -----
        function moveSnake() {
            if (gameOver) return false;

            // apply queued direction (no reversing)
            const opposite = {
                'UP': 'DOWN', 'DOWN': 'UP', 'LEFT': 'RIGHT', 'RIGHT': 'LEFT'
            };
            if (nextDirection && opposite[nextDirection] !== direction) {
                direction = nextDirection;
            }

            // compute new head
            const head = snake[0];
            let newHead = { ...head };
            switch (direction) {
                case 'RIGHT': newHead.x += 1; break;
                case 'LEFT':  newHead.x -= 1; break;
                case 'UP':    newHead.y -= 1; break;
                case 'DOWN':  newHead.y += 1; break;
                default: return false;
            }

            // check food consumption
            const isEating = (newHead.x === food.x && newHead.y === food.y);

            // build new snake array
            let newSnake = [newHead, ...snake];

            if (!isEating) {
                newSnake.pop(); // remove tail
            }

            // collision detection (walls & self)
            const headCollision =
                newHead.x < 0 || newHead.x >= GRID_SIZE || newHead.y < 0 || newHead.y >= GRID_SIZE;

            // self-collision: check if newHead collides with body (except first element)
            const selfCollision = (() => {
                // skip first element (newHead) 
                for (let i = 1; i < newSnake.length; i++) {
                    if (newSnake[i].x === newHead.x && newSnake[i].y === newHead.y) {
                        return true;
                    }
                }
                return false;
            })();

            if (headCollision || selfCollision) {
                gameOver = true;
                if (gameInterval) {
                    clearInterval(gameInterval);
                    gameInterval = null;
                }
                drawCanvas();
                return false;
            }

            // apply new snake
            snake = newSnake;

            // handle food eaten
            if (isEating) {
                score++;
                scoreSpan.innerText = score;
                const success = generateFood();
                if (!success) {
                    // board full → win condition
                    gameOver = true;
                    win = true;
                    if (gameInterval) {
                        clearInterval(gameInterval);
                        gameInterval = null;
                    }
                    drawCanvas();
                    return false;
                }
            }

            drawCanvas();
            return true;
        }

        // ----- rendering (dynamic & colorful) -----
        function drawCanvas() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // draw subtle grid (dynamic background)
            ctx.strokeStyle = '#2d494d';
            ctx.lineWidth = 0.6;
            for (let i = 0; i <= GRID_SIZE; i++) {
                ctx.beginPath();
                ctx.moveTo(i * CELL_SIZE, 0);
                ctx.lineTo(i * CELL_SIZE, canvas.height);
                ctx.stroke();
                ctx.beginPath();
                ctx.moveTo(0, i * CELL_SIZE);
                ctx.lineTo(canvas.width, i * CELL_SIZE);
                ctx.stroke();
            }

            // draw food (glowing apple)
            ctx.shadowColor = '#ffb07c';
            ctx.shadowBlur = 14;
            ctx.fillStyle = '#ff3b2f';
            ctx.beginPath();
            ctx.arc(
                food.x * CELL_SIZE + CELL_SIZE/2,
                food.y * CELL_SIZE + CELL_SIZE/2,
                CELL_SIZE/2 - 2,
                0, Math.PI * 2
            );
            ctx.fill();
            // highlight
            ctx.shadowBlur = 6;
            ctx.fillStyle = '#ff6b4a';
            ctx.beginPath();
            ctx.arc(
                food.x * CELL_SIZE + CELL_SIZE/2 - 3,
                food.y * CELL_SIZE + CELL_SIZE/2 - 3,
                4, 0, Math.PI * 2
            );
            ctx.fill();
            ctx.shadowBlur = 0; // reset

            // draw snake (dynamic gradient per segment)
            const len = snake.length;
            for (let i = 0; i < len; i++) {
                const seg = snake[i];
                const x = seg.x * CELL_SIZE;
                const y = seg.y * CELL_SIZE;
                const padding = i === 0 ? 1 : 2; // head slightly bigger
                const radius = 4;

                // dynamic color: head is bright, tail fades
                const intensity = 0.5 + 0.5 * (1 - i / len);
                const r = Math.floor(70 + 120 * intensity);
                const g = Math.floor(180 + 60 * intensity);
                const b = Math.floor(90 + 30 * intensity);
                ctx.fillStyle = `rgb(${r}, ${g}, ${b})`;
                ctx.shadowColor = '#a0d6d0';
                ctx.shadowBlur = i === 0 ? 16 : 5;

                // rounded rect
                const cx = x + CELL_SIZE/2;
                const cy = y + CELL_SIZE/2;
                const w = CELL_SIZE - padding * 2;
                const h = CELL_SIZE - padding * 2;
                ctx.beginPath();
                ctx.ellipse(cx, cy, w/2, h/2, 0, 0, Math.PI * 2);
                ctx.fill();

                // eyes on head
                if (i === 0) {
                    ctx.shadowBlur = 0;
                    ctx.fillStyle = '#f0faff';
                    const eyeOff = 5;
                    let ex1, ey1, ex2, ey2;
                    switch (direction) {
                        case 'RIGHT': 
                            ex1 = x + 16; ey1 = y + 6; ex2 = x + 16; ey2 = y + 14; break;
                        case 'LEFT': 
                            ex1 = x + 6; ey1 = y + 6; ex2 = x + 6; ey2 = y + 14; break;
                        case 'UP': 
                            ex1 = x + 6; ey1 = y + 6; ex2 = x + 14; ey2 = y + 6; break;
                        case 'DOWN': 
                            ex1 = x + 6; ey1 = y + 16; ex2 = x + 14; ey2 = y + 16; break;
                        default: ex1 = x+16; ey1 = y+6; ex2 = x+16; ey2 = y+14;
                    }
                    ctx.beginPath();
                    ctx.arc(ex1, ey1, 3, 0, 2*Math.PI);
                    ctx.fill();
                    ctx.beginPath();
                    ctx.arc(ex2, ey2, 3, 0, 2*Math.PI);
                    ctx.fill();
                    ctx.fillStyle = '#091618';
                    ctx.beginPath();
                    ctx.arc(ex1+1, ey1-1, 1.2, 0, 2*Math.PI);
                    ctx.fill();
                    ctx.beginPath();
                    ctx.arc(ex2+1, ey2-1, 1.2, 0, 2*Math.PI);
                    ctx.fill();
                }
            }
            ctx.shadowBlur = 0;

            // game over / win overlay
            if (gameOver) {
                ctx.fillStyle = 'rgba(0,0,0,0.5)';
                ctx.fillRect(0, 0, canvas.width, canvas.height);
                ctx.font = 'bold 26px "Segoe UI", system-ui, sans-serif';
                ctx.textAlign = 'center';
                ctx.textBaseline = 'middle';
                ctx.shadowColor = '#000000';
                ctx.shadowBlur = 16;
                if (win) {
                    ctx.fillStyle = '#d4f7b0';
                    ctx.fillText('🏆 YOU WIN!', canvas.width/2, canvas.height/2 - 20);
                } else {
                    ctx.fillStyle = '#ffbaba';
                    ctx.fillText('💀 GAME OVER', canvas.width/2, canvas.height/2 - 20);
                }
                ctx.shadowBlur = 0;
            }
        }

        // ----- game loop control -----
        function startGameLoop() {
            if (gameInterval) clearInterval(gameInterval);
            gameInterval = setInterval(() => {
                if (!gameOver) {
                    moveSnake();
                } else {
                    // if gameOver, clear interval (safety)
                    if (gameInterval) {
                        clearInterval(gameInterval);
                        gameInterval = null;
                    }
                }
            }, MOVE_INTERVAL_MS);
        }

        // ----- keyboard controls (dynamic direction) -----
        function handleKey(e) {
            const key = e.key;
            e.preventDefault();

            if (gameOver) return;

            const keyMap = {
                'ArrowUp': 'UP',
                'ArrowDown': 'DOWN',
                'ArrowLeft': 'LEFT',
                'ArrowRight': 'RIGHT'
            };
            if (key in keyMap) {
                const newDir = keyMap[key];
                const opposite = { 'UP':'DOWN', 'DOWN':'UP', 'LEFT':'RIGHT', 'RIGHT':'LEFT' };
                // prevent instant reverse
                if (direction !== opposite[newDir]) {
                    nextDirection = newDir;
                }
            }
        }

        // ----- restart -----
        document.getElementById('restartBtn').addEventListener('click', function() {
            resetGame();
        });

        // ----- initialise game -----
        function init() {
            window.addEventListener('keydown', (e) => {
                if (e.key.startsWith('Arrow')) {
                    handleKey(e);
                }
            });
            // disable page scrolling with arrows
            window.addEventListener('keyup', (e) => {
                if (e.key.startsWith('Arrow')) e.preventDefault();
            });
            resetGame(); // sets up everything + draws
        }

        init();
    })();
</script>
</body>
</html>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/maurodesouza/maurodesouza/pacman-output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/maurodesouza/maurodesouza/pacman-output/pacman-contribution-graph.svg">
  <img alt="pacman contribution graph" src="https://raw.githubusercontent.com/maurodesouza/maurodesouza/pacman-output/pacman-contribution-graph.svg">
</picture>

###
