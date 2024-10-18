<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zafir's Interactive Hub</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #0a192f;
            --secondary-color: #172a45;
            --accent-color: #ffd700;
            --text-color: #333333;
            --text-bright: #e6f1ff;
            --background-color: #f0f5ff;
            --card-bg: #ffffff;
        }

        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        nav {
            background-color: var(--primary-color);
            padding: 15px 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        nav ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
            display: flex;
            justify-content: center;
        }

        nav ul li {
            margin: 0 10px;
        }

        nav ul li a {
            color: var(--text-bright);
            text-decoration: none;
            padding: 10px 15px;
            border-radius: 5px;
            transition: all 0.3s ease;
            font-weight: 500;
        }

        nav ul li a:hover, nav ul li a.active {
            background-color: var(--accent-color);
            color: var(--primary-color);
        }

        .container {
            max-width: 1000px;
            margin: 40px auto;
            padding: 20px;
        }

        .tab-content {
            display: none;
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .active {
            display: block;
            animation: fadeIn 0.5s;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        h2 {
            color: var(--primary-color);
            margin-top: 0;
            font-size: 2.5em;
            margin-bottom: 20px;
        }

        button {
            background-color: var(--accent-color);
            border: none;
            color: var(--primary-color);
            padding: 12px 24px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
            border-radius: 5px;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        button:hover {
            background-color: var(--primary-color);
            color: var(--accent-color);
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }

        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid var(--secondary-color);
            border-radius: 5px;
            background-color: var(--background-color);
            color: var(--text-color);
            font-size: 16px;
        }

        #funFactText, #dictionaryOutput, #guessResult {
            margin-top: 20px;
            padding: 20px;
            background-color: var(--background-color);
            border-radius: 5px;
            font-size: 18px;
            color: var(--text-color);
            border-left: 5px solid var(--accent-color);
        }

        .game-option {
            margin: 15px 0;
        }

        #calculator {
            width: 300px;
            background-color: var(--card-bg);
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            margin: 0 auto;
        }

        #calc-display {
            width: 100%;
            height: 60px;
            font-size: 24px;
            text-align: right;
            padding: 10px;
            margin-bottom: 20px;
            background-color: var(--background-color);
            border: 1px solid var(--secondary-color);
            border-radius: 5px;
            color: var(--text-color);
        }

        .calc-buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        .calc-button {
            padding: 15px;
            font-size: 18px;
            text-align: center;
            background-color: var(--background-color);
            color: var(--text-color);
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .calc-button:hover {
            background-color: var(--accent-color);
            color: var(--primary-color);
        }

        .calc-button.operator {
            background-color: var(--accent-color);
            color: var(--primary-color);
        }

        .calc-button.operator:hover {
            background-color: var(--primary-color);
            color: var(--accent-color);
        }

        .calc-button.equals {
            background-color: var(--primary-color);
            color: var(--accent-color);
            grid-column: span 2;
        }

        .calc-button.equals:hover {
            background-color: var(--accent-color);
            color: var(--primary-color);
        }

        #gameCanvas {
            border: 1px solid var(--primary-color);
            display: block;
            margin: 20px auto;
            background-color: var(--background-color);
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#" onclick="showTab('home')" id="nav-home">Home</a></li>
            <li><a href="#" onclick="showTab('games')" id="nav-games">Games</a></li>
            <li><a href="#" onclick="showTab('fun-fact')" id="nav-fun-fact">Fun Fact</a></li>
            <li><a href="#" onclick="showTab('dictionary')" id="nav-dictionary">Dictionary</a></li>
            <li><a href="#" onclick="showTab('calculator')" id="nav-calculator">Calculator</a></li>
        </ul>
    </nav>

    <div class="container">
        <div id="home" class="tab-content active">
            <h2>Welcome to Zafir's Interactive Hub</h2>
            <p>Explore exciting games, learn interesting facts, look up words, or use our calculator. This is your one-stop shop for fun and learning!</p>
        </div>

        <div id="games" class="tab-content">
            <h2>Games</h2>
            <div class="game-option">
                <h3>Catch the Thief</h3>
                <p>Help the police catch the thief in this exciting chase game!</p>
                <button onclick="startCatchTheThief()">Play Catch the Thief</button>
            </div>
            <div class="game-option">
                <h3>Snake Game</h3>
                <p>Guide the snake to eat food and grow, but don't hit the walls or yourself!</p>
                <button onclick="startSnakeGame()">Play Snake</button>
            </div>
            <canvas id="gameCanvas" width="400" height="400" style="display:none;"></canvas>
        </div>

        <div id="fun-fact" class="tab-content">
            <h2>Fun Fact</h2>
            <button onclick="generateFunFact()">Get New Fun Fact</button>
            <p id="funFactText"></p>
        </div>

        <div id="dictionary" class="tab-content">
            <h2>Dictionary</h2>
            <input type="text" id="wordInput" placeholder="Enter a word">
            <button onclick="lookupWord()">Look Up</button>
            <div id="dictionaryOutput"></div>
        </div>

        <div id="calculator" class="tab-content">
            <h2>Calculator</h2>
            <div id="calc-container">
                <input type="text" id="calc-display" readonly>
                <div class="calc-buttons">
                    <button class="calc-button" onclick="appendToDisplay('7')">7</button>
                    <button class="calc-button" onclick="appendToDisplay('8')">8</button>
                    <button class="calc-button" onclick="appendToDisplay('9')">9</button>
                    <button class="calc-button operator" onclick="appendToDisplay('+')">+</button>
                    <button class="calc-button" onclick="appendToDisplay('4')">4</button>
                    <button class="calc-button" onclick="appendToDisplay('5')">5</button>
                    <button class="calc-button" onclick="appendToDisplay('6')">6</button>
                    <button class="calc-button operator" onclick="appendToDisplay('-')">-</button>
                    <button class="calc-button" onclick="appendToDisplay('1')">1</button>
                    <button class="calc-button" onclick="appendToDisplay('2')">2</button>
                    <button class="calc-button" onclick="appendToDisplay('3')">3</button>
                    <button class="calc-button operator" onclick="appendToDisplay('*')">*</button>
                    <button class="calc-button" onclick="appendToDisplay('0')">0</button>
                    <button class="calc-button" onclick="appendToDisplay('.')">.</button>
                    <button class="calc-button" onclick="clearDisplay()">C</button>
                    <button class="calc-button operator" onclick="appendToDisplay('/')">/</button>
                    <button class="calc-button equals" onclick="calculate()">=</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        function showTab(tabId) {
            var tabs = document.getElementsByClassName('tab-content');
            for (var i = 0; i < tabs.length; i++) {
                tabs[i].classList.remove('active');
            }
            document.getElementById(tabId).classList.add('active');
            
            var navItems = document.querySelectorAll('nav ul li a');
            for (var i = 0; i < navItems.length; i++) {
                navItems[i].classList.remove('active');
            }
            document.getElementById('nav-' + tabId).classList.add('active');

            if (tabId === 'fun-fact') {
                generateFunFact();
            }
        }

        function generateFunFact() {
            const facts = [
                "The shortest war in history lasted 38 minutes.",
                "A group of flamingos is called a 'flamboyance'.",
                "The Great Wall of China is not visible from space with the naked eye.",
                "Honey never spoils. Archaeologists have found pots of honey in ancient Egyptian tombs that are over 3,000 years old and still perfectly edible.",
                "The longest English word without a vowel is 'rhythms'.",
                "A jiffy is an actual unit of time: 1/100th of a second.",
                "The fingerprints of koalas are virtually indistinguishable from human fingerprints.",
                "The Hawaiian alphabet only has 12 letters.",
                "A day on Venus is longer than its year.",
                "The Eiffel Tower can grow up to 6 inches taller during the summer due to the expansion of the iron in hot weather."
            ];
            
            const randomIndex = Math.floor(Math.random() * facts.length);
            document.getElementById('funFactText').textContent = facts[randomIndex];
        }

        function lookupWord() {
            var word = document.getElementById('wordInput').value;
            var output = document.getElementById('dictionaryOutput');
            output.innerHTML = "Looking up: " + word;
            
            fetch('https://api.dictionaryapi.dev/api/v2/entries/en/' + word)
                .then(response => response.json())
                .then(data => {
                    if (Array.isArray(data)) {
                        output.innerHTML = "<h3>" + word + "</h3><p>" + data[0].meanings[0].definitions[0].definition + "</p>";
                    } else {
                        output.innerHTML = "No definition found.";
                    }
                })
                .catch(error => {
                    output.innerHTML = "An error occurred.";
                    console.error('Error:', error);
                });
        }

        function appendToDisplay(value) {
            document.getElementById('calc-display').value += value;
        }

        function clearDisplay() {
            document.getElementById('calc-display').value = '';
        }

        function calculate() {
            try {
                const result = eval(document.getElementById('calc-display').value);
                document.getElementById('calc-display').value = result;
            } catch (error) {
                document.getElementById('calc-display').value = 'Error';
            }
        }

        // Catch the Thief game
        function startCatchTheThief() {
            const canvas = document.getElementById('gameCanvas');
            canvas.style.display = 'block';
            const ctx = canvas.getContext('2d');
            
            let police = { x: 200, y: 200, size: 20 };
            let thief = { x: 100, y: 100, size: 20, dx: 2, dy: 2 };
            let score = 0;

            function drawCharacter(character, color, isCircle = false) {
                ctx.fillStyle = color;
                if (isCircle) {
                    ctx.beginPath();
                    ctx.arc(character.x + character.size/2, character.y + character.size/2, character.size/2, 0, Math.PI * 2);
                    ctx.fill();
                } else {
                    ctx.fillRect(character.x, character.y, character.size, character.size);
                }
            }

            function moveThief() {
                thief.x += thief.dx;
                thief.y += thief.dy;

                if (thief.x <= 0 || thief.x + thief.size >= canvas.width) thief.dx *= -1;
                if (thief.y <= 0 || thief.y + thief.size >= canvas.height) thief.dy *= -1;
            }

            function gameLoop() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                drawCharacter(police, 'blue');
                drawCharacter(thief, 'red', true);
                moveThief();

                if (Math.hypot(police.x - thief.x, police.y - thief.y) < police.size) {
                    score++;
                    thief.x = Math.random() * (canvas.width - thief.size);
                    thief.y = Math.random() * (canvas.height - thief.size);
                }

                ctx.fillStyle = 'black';
                ctx.font = '20px Arial';
                ctx.fillText('Score: ' + score, 10, 30);

                requestAnimationFrame(gameLoop);
            }

            document.onkeydown = function(e) {
                const speed = 5;
                switch(e.key) {
                    case 'ArrowLeft': police.x -= speed; break;
                    case 'ArrowRight': police.x += speed; break;
                    case 'ArrowUp': police.y -= speed; break;
                    case 'ArrowDown': police.y += speed; break;
                }
                police.x = Math.max(0, Math.min(canvas.width - police.size, police.x));
                police.y = Math.max(0, Math.min(canvas.height - police.size, police.y));
            };

            gameLoop();
        }

        // Snake game
        function startSnakeGame() {
            const canvas = document.getElementById('gameCanvas');
            canvas.style.display = 'block';
            const ctx = canvas.getContext('2d');

            const gridSize = 20;
            let snake = [{ x: 200, y: 200 }];
            let food = { x: 300, y: 300 };
            let dx = gridSize;
            let dy = 0;
            let score = 0;

            function drawSnakePart(snakePart) {
                ctx.fillStyle = 'green';
                ctx.fillRect(snakePart.x, snakePart.y, gridSize - 2, gridSize - 2);
            }

            function drawFood() {
                ctx.fillStyle = 'red';
                ctx.fillRect(food.x, food.y, gridSize - 2, gridSize - 2);
            }

            function moveSnake() {
                const head = { x: snake[0].x + dx, y: snake[0].y + dy };
                snake.unshift(head);
                if (head.x === food.x && head.y === food.y) {
                    score++;
                    generateFood();
                } else {
                    snake.pop();
                }
            }

            function generateFood() {
                food.x = Math.floor(Math.random() * (canvas.width / gridSize)) * gridSize;
                food.y = Math.floor(Math.random() * (canvas.height / gridSize)) * gridSize;
            }

            function gameLoop() {
                ctx.clearRect(0, 0, canvas.width, canvas.height);
                moveSnake();
                if (checkCollision()) {
                    alert('Game Over! Your score: ' + score);
                    snake = [{ x: 200, y: 200 }];
                    dx = gridSize;
                    dy = 0;
                    score = 0;
                }
                drawFood();
                snake.forEach(drawSnakePart);

                ctx.fillStyle = 'black';
                ctx.font = '20px Arial';
                ctx.fillText('Score: ' + score, 10, 30);

                setTimeout(() => requestAnimationFrame(gameLoop), 100);
            }

            function checkCollision() {
                const head = snake[0];
                return (
                    head.x < 0 || head.x >= canvas.width ||
                    head.y < 0 || head.y >= canvas.height ||
                    snake.slice(1).some(part => part.x === head.x && part.y === head.y)
                );
            }

            document.onkeydown = function(e) {
                switch(e.key) {
                    case 'ArrowLeft': if (dx === 0) { dx = -gridSize; dy = 0; } break;
                    case 'ArrowRight': if (dx === 0) { dx = gridSize; dy = 0; } break;
                    case 'ArrowUp': if (dy === 0) { dx = 0; dy = -gridSize; } break;
                    case 'ArrowDown': if (dy === 0) { dx = 0; dy = gridSize; } break;
                }
            };

            gameLoop();
        }

        // Show home tab by default
        showTab('home');
    </script>
</body>
</html>
