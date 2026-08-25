* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Arial', sans-serif;
    background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
    color: white;
    overflow: hidden;
}

.container {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column;
}

.header {
    background: linear-gradient(90deg, #FFD700 0%, #FFA500 100%);
    padding: 15px 20px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
    z-index: 100;
}

.header h1 {
    color: #333;
    font-size: 2em;
    margin-bottom: 10px;
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
}

.info-bar {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.coins-display {
    font-size: 1.5em;
    font-weight: bold;
    color: #333;
    display: flex;
    align-items: center;
    gap: 10px;
}

.coin-icon {
    font-size: 1.8em;
}

.buttons {
    display: flex;
    gap: 15px;
}

.btn {
    padding: 10px 25px;
    font-size: 1em;
    font-weight: bold;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.start-btn {
    background: #FF6B6B;
    color: white;
}

.start-btn:hover {
    background: #FF5252;
    transform: scale(1.05);
}

.shop-btn {
    background: #4ECDC4;
    color: white;
}

.shop-btn:hover {
    background: #45B8B0;
    transform: scale(1.05);
}

.game-container {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    background: linear-gradient(180deg, #87CEEB 0%, #E0F6FF 100%);
}

.game-container.hidden {
    display: none;
}

#gameCanvas {
    border: 3px solid #333;
    background: #87CEEB;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
}

.shop-container {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    flex-direction: column;
    z-index: 200;
}

.shop-container.hidden {
    display: none;
}

.shop-header {
    background: linear-gradient(90deg, #FFD700 0%, #FFA500 100%);
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.shop-header h2 {
    color: #333;
    font-size: 2em;
}

.close-btn {
    background: #FF6B6B;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 1.2em;
    cursor: pointer;
    border-radius: 5px;
    font-weight: bold;
}

.close-btn:hover {
    background: #FF5252;
}

.shop-items {
    display: flex;
    justify-content: center;
    gap: 30px;
    padding: 40px 20px;
    flex-wrap: wrap;
}

.car-item {
    background: linear-gradient(135deg, #2c3e50 0%, #34495e 100%);
    padding: 20px;
    border-radius: 10px;
    text-align: center;
    min-width: 200px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    transition: transform 0.3s ease;
}

.car-item:hover {
    transform: translateY(-10px);
}

.car-preview {
    width: 100%;
    height: 150px;
    border-radius: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 3em;
    font-weight: bold;
    color: white;
    margin-bottom: 15px;
    box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.3);
}

.car-name {
    font-size: 1.3em;
    margin-bottom: 10px;
    color: #FFD700;
}

.car-price {
    font-size: 1.2em;
    margin-bottom: 15px;
    color: #4ECDC4;
}

.buy-btn {
    background: #27AE60;
    color: white;
    border: none;
    padding: 10px 25px;
    font-size: 1em;
    font-weight: bold;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.buy-btn:hover {
    background: #229954;
    transform: scale(1.05);
}

.buy-btn:disabled {
    background: #7f8c8d;
    cursor: not-allowed;
}

.menu-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #FFD700 0%, #FFA500 50%, #FF6B6B 100%);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 300;
}

.menu-screen.hidden {
    display: none;
}

.menu-content {
    text-align: center;
    animation: fadeIn 0.8s ease;
}

.play-btn {
    padding: 20px 60px;
    font-size: 1.8em;
    font-weight: bold;
    background: #333;
    color: #FFD700;
    border: 3px solid #FFD700;
    border-radius: 10px;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
}

.play-btn:hover {
    background: #FFD700;
    color: #333;
    transform: scale(1.1);
}

@keyframes fadeIn {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

.hidden {
    display: none !important;
}# MADHAV-CAR
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Madhav Car Game</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🚗 Madhav Car Game 🚗</h1>
            <div class="info-bar">
                <div class="coins-display">
                    <span class="coin-icon">💰</span>
                    <span id="coins">100</span>
                </div>
                <div class="buttons">
                    <button id="startBtn" class="btn start-btn">START</button>
                    <button id="shopBtn" class="btn shop-btn">SHOP</button>
                </div>
            </div>
        </div>

        <div id="gameContainer" class="game-container hidden">
            <canvas id="gameCanvas"></canvas>
        </div>

        <div id="shopContainer" class="shop-container hidden">
            <div class="shop-header">
                <h2>🛍️ Car Shop</h2>
                <button id="closeShop" class="close-btn">X</button>
            </div>
            <div class="shop-items">
                <div class="car-item">
                    <div class="car-preview" style="background: #FF6B6B;">GTA</div>
                    <p class="car-name">GTA</p>
                    <p class="car-price">200 💰</p>
                    <button class="buy-btn" data-car="gta" data-price="200">BUY</button>
                </div>
                <div class="car-item">
                    <div class="car-preview" style="background: #4ECDC4;">BMW M4</div>
                    <p class="car-name">BMW M4</p>
                    <p class="car-price">250 💰</p>
                    <button class="buy-btn" data-car="bmw" data-price="250">BUY</button>
                </div>
                <div class="car-item">
                    <div class="car-preview" style="background: #95E1D3;">M2</div>
                    <p class="car-name">BMW M2</p>
                    <p class="car-price">300 💰</p>
                    <button class="buy-btn" data-car="m2" data-price="300">BUY</button>
                </div>
            </div>
        </div>

        <div id="mainMenu" class="menu-screen">
            <div class="menu-content">
                <h1 style="color: #FFD700; font-size: 4em; margin-bottom: 20px;">🏎️ MADHAV CAR GAME 🏎️</h1>
                <p style="font-size: 1.5em; color: white; margin-bottom: 40px;">Road par coins collect karo aur apni car ko upgrade karo!</p>
                <button id="playBtn" class="play-btn">PLAY NOW</button>
            </div>
        </div>
    </div>

    <audio id="bgMusic" loop>
        <source src="data:audio/wav;base64,UklGRiYAAABXQVZFZm10IBAAAAABAAEAQB8AAAB9AAACABAAZGF0YQIAAAAAAA==" type="audio/wav">
    </audio>

    <script src="script.js"></script>
</body>
</html>
// Game Variables
let gameRunning = false;
let coins = 100;
let currentCar = 'default';
let carColors = {
    default: '#FFD700',
    gta: '#FF6B6B',
    bmw: '#4ECDC4',
    m2: '#95E1D3'
};

// Canvas Setup
const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth * 0.9;
canvas.height = window.innerHeight * 0.8;

// Game Objects
const player = {
    x: canvas.width / 2,
    y: canvas.height - 100,
    width: 40,
    height: 60,
    speed: 5,
    velocityX: 0,
    color: carColors.default
};

const gameState = {
    score: 0,
    coinsCollected: 0,
    enemies: [],
    coins: []
};

// Coin Class
class Coin {
    constructor() {
        this.x = Math.random() * (canvas.width - 20);
        this.y = -20;
        this.width = 20;
        this.height = 20;
        this.speed = 3 + Math.random() * 2;
    }

    update() {
        this.y += this.speed;
    }

    draw() {
        ctx.fillStyle = '#FFD700';
        ctx.beginPath();
        ctx.arc(this.x + this.width / 2, this.y + this.height / 2, 10, 0, Math.PI * 2);
        ctx.fill();
        ctx.fillStyle = '#FFA500';
        ctx.font = 'bold 14px Arial';
        ctx.textAlign = 'center';
        ctx.textBaseline = 'middle';
        ctx.fillText('💰', this.x + this.width / 2, this.y + this.height / 2);
    }
}

// Enemy Class (basic obstacle)
class Enemy {
    constructor() {
        this.x = Math.random() * (canvas.width - 40);
        this.y = -40;
        this.width = 40;
        this.height = 60;
        this.speed = 2 + Math.random() * 1.5;
        this.color = '#E74C3C';
    }

    update() {
        this.y += this.speed;
    }

    draw() {
        ctx.fillStyle = this.color;
        ctx.fillRect(this.x, this.y, this.width, this.height);
        ctx.fillStyle = '#000';
        ctx.fillRect(this.x + 5, this.y + 10, 10, 15);
        ctx.fillRect(this.x + 25, this.y + 10, 10, 15);
    }
}

// Background Elements
function drawBackground() {
    // Sky
    ctx.fillStyle = '#87CEEB';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // River
    ctx.fillStyle = '#4A90E2';
    ctx.fillRect(0, canvas.height - 80, canvas.width, 80);

    // Road
    ctx.fillStyle = '#333';
    ctx.fillRect(0, canvas.height - 150, canvas.width, 70);

    // Road lines
    ctx.strokeStyle = '#FFD700';
    ctx.lineWidth = 3;
    ctx.setLineDash([30, 30]);
    ctx.beginPath();
    ctx.moveTo(canvas.width / 2, canvas.height - 150);
    ctx.lineTo(canvas.width / 2, 0);
    ctx.stroke();
    ctx.setLineDash([]);

    // Trees
    drawTree(100, 150);
    drawTree(canvas.width - 150, 200);
    drawTree(canvas.width / 2 - 200, 100);
    drawTree(canvas.width / 2 + 200, 180);
}

function drawTree(x, y) {
    // Trunk
    ctx.fillStyle = '#8B4513';
    ctx.fillRect(x - 15, y, 30, 60);
    // Leaves
    ctx.fillStyle = '#228B22';
    ctx.beginPath();
    ctx.arc(x, y - 20, 40, 0, Math.PI * 2);
    ctx.fill();
}

// Draw Player Car
function drawPlayer() {
    ctx.fillStyle = player.color;
    ctx.fillRect(player.x, player.y, player.width, player.height);
    // Windows
    ctx.fillStyle = '#87CEEB';
    ctx.fillRect(player.x + 5, player.y + 10, 30, 15);
    ctx.fillRect(player.x + 5, player.y + 35, 30, 10);
    // Wheels
    ctx.fillStyle = '#000';
    ctx.fillRect(player.x + 8, player.y + player.height, 8, 8);
    ctx.fillRect(player.x + player.width - 16, player.y + player.height, 8, 8);
}

// Keyboard Controls
const keys = {};
window.addEventListener('keydown', (e) => {
    keys[e.key] = true;
});
window.addEventListener('keyup', (e) => {
    keys[e.key] = false;
});

// Update Player Position
function updatePlayer() {
    if (keys['ArrowLeft'] || keys['a']) {
        player.x = Math.max(0, player.x - player.speed);
    }
    if (keys['ArrowRight'] || keys['d']) {
        player.x = Math.min(canvas.width - player.width, player.x + player.speed);
    }
}

// Collision Detection
function checkCollision(rect1, rect2) {
    return rect1.x < rect2.x + rect2.width &&
           rect1.x + rect1.width > rect2.x &&
           rect1.y < rect2.y + rect2.height &&
           rect1.y + rect1.height > rect2.y;
}

// Game Update
function updateGame() {
    // Spawn coins
    if (Math.random() < 0.03) {
        gameState.coins.push(new Coin());
    }

    // Spawn enemies
    if (Math.random() < 0.02) {
        gameState.enemies.push(new Enemy());
    }

    // Update coins
    gameState.coins = gameState.coins.filter(coin => coin.y < canvas.height);
    gameState.coins.forEach(coin => {
        coin.update();
        if (checkCollision(player, coin)) {
            coins += Math.random() < 0.5 ? 10 : 20;
            updateCoinsDisplay();
            gameState.coinsCollected++;
            gameState.coins.splice(gameState.coins.indexOf(coin), 1);
        }
    });

    // Update enemies
    gameState.enemies = gameState.enemies.filter(enemy => enemy.y < canvas.height);
    gameState.enemies.forEach(enemy => {
        enemy.update();
        if (checkCollision(player, enemy)) {
            gameRunning = false;
            endGame();
        }
    });

    updatePlayer();
}

// Game Draw
function drawGame() {
    drawBackground();
    drawPlayer();
    gameState.coins.forEach(coin => coin.draw());
    gameState.enemies.forEach(enemy => enemy.draw());
}

// Game Loop
function gameLoop() {
    if (gameRunning) {
        updateGame();
        drawGame();
        requestAnimationFrame(gameLoop);
    }
}

// Start Game
function startGame() {
    document.getElementById('mainMenu').classList.add('hidden');
    document.getElementById('gameContainer').classList.remove('hidden');
    document.getElementById('shopContainer').classList.add('hidden');
    gameRunning = true;
    gameState.coins = [];
    gameState.enemies = [];
    gameState.coinsCollected = 0;
    player.x = canvas.width / 2;
    player.y = canvas.height - 100;
    gameLoop();
}

// End Game
function endGame() {
    gameRunning = false;
    alert(`Game Over! 🏁\nCoins Collected: ${gameState.coinsCollected}\nTotal Coins: ${coins}`);
    document.getElementById('gameContainer').classList.add('hidden');
    document.getElementById('mainMenu').classList.remove('hidden');
}

// Shop Functions
function openShop() {
    document.getElementById('shopContainer').classList.remove('hidden');
    gameRunning = false;
}

function closeShop() {
    document.getElementById('shopContainer').classList.add('hidden');
}

function buyCar(carType, price) {
    if (coins >= price) {
        coins -= price;
        currentCar = carType;
        player.color = carColors[carType];
        updateCoinsDisplay();
        alert(`You bought ${carType.toUpperCase()}! 🎉`);
    } else {
        alert(`Not enough coins! Need ${price}, Have ${coins}`);
    }
}

function updateCoinsDisplay() {
    document.getElementById('coins').textContent = coins;
}

// Event Listeners
document.getElementById('playBtn').addEventListener('click', startGame);
document.getElementById('startBtn').addEventListener('click', startGame);
document.getElementById('shopBtn').addEventListener('click', openShop);
document.getElementById('closeShop').addEventListener('click', closeShop);

document.querySelectorAll('.buy-btn').forEach(btn => {
    btn.addEventListener('click', () => {
        buyCar(btn.dataset.car, parseInt(btn.dataset.price));
    });
});

// Window Resize
window.addEventListener('resize', () => {
    canvas.width = window.innerWidth * 0.9;
    canvas.height = window.innerHeight * 0.8;
});

// Initialize
function init() {
    updateCoinsDisplay();
    console.log('🎮 Madhav Car Game Started!');
}

init();
