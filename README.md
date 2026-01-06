<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elon's Cash Geyser</title>
    <style>
        body {
            background-color: #f0f2f5;
            font-family: 'Arial', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        .container {
            text-align: center;
            position: relative;
        }

        #elon-img {
            width: 300px;
            cursor: pointer;
            transition: transform 0.1s;
        }

        #elon-img:active {
            transform: scale(0.95);
        }

        .fart-btn {
            background-color: #ff4757;
            color: white;
            border: none;
            padding: 20px 40px;
            font-size: 24px;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            margin-top: 20px;
        }

        .fart-btn:hover { background-color: #ff6b81; }

        .money {
            position: absolute;
            font-size: 30px;
            pointer-events: none;
            z-index: 10;
            animation: fly-away 1s forwards;
        }

        @keyframes fly-away {
            0% { transform: translate(0, 0) rotate(0deg); opacity: 1; }
            100% { transform: translate(var(--x), var(--y)) rotate(360deg); opacity: 0; }
        }

        .counter {
            font-size: 28px;
            margin-top: 20px;
            color: #2f3542;
        }
    </style>
</head>
<body>

    <h1>ELON'S CASH GEYSER</h1>

    <div class="container" id="game-area">
        <img src="https://via.placeholder.com/300x300?text=ELON+PIXEL+ART" id="elon-img" alt="Elon Musk">
        
        <br>
        <button class="fart-btn" onclick="fartMoney()">FARTER</button>

        <div class="counter">Total Money Farted: $<span id="total">0</span></div>
    </div>

    <script>
        let total = 0;

        function fartMoney() {
            total += 100000;
            document.getElementById('total').innerText = total.toLocaleString();

            // Create money elements
            for(let i = 0; i < 5; i++) {
                createMoney();
            }
        }

        function createMoney() {
            const money = document.createElement('div');
            money.innerText = '💸';
            money.className = 'money';
            
            // Random direction for the "fart" trajectory
            const x = (Math.random() - 0.5) * 400 + 'px';
            const y = (Math.random() - 0.2) * -400 + 'px';
            
            money.style.setProperty('--x', x);
            money.style.setProperty('--y', y);
            
            // Position it near Elon's "area"
            money.style.left = '50%';
            money.style.top = '40%';

            document.getElementById('game-area').appendChild(money);

            // Clean up the element after animation
            setTimeout(() => {
                money.remove();
            }, 1000);
        }
    </script>
</body>
</html>
