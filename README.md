
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elon's Cash Geyser</title>
    <style>
        body {
            background: linear-gradient(180deg, #00a8ff, #9c88ff);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .game-container {
            position: relative;
            text-align: center;
        }

        /* The Elon Image */
        #elon {
            width: 350px;
            height: auto;
            cursor: pointer;
            position: relative;
            z-index: 5;
            transition: transform 0.05s;
            filter: drop-shadow(0 10px 20px rgba(0,0,0,0.3));
        }

        #elon:active {
            transform: scale(0.9) rotate(-5deg);
        }

        /* The Farting Money */
        .bill {
            position: absolute;
            font-size: 40px;
            pointer-events: none;
            z-index: 1;
            animation: eject 1.5s ease-out forwards;
        }

        @keyframes eject {
            0% { 
                transform: translate(0, 0) rotate(0deg); 
                opacity: 1; 
            }
            100% { 
                transform: translate(var(--x), var(--y)) rotate(720deg); 
                opacity: 0; 
            }
        }

        .ui {
            margin-top: 20px;
            z-index: 10;
        }

        button {
            background: #4cd137;
            border: none;
            padding: 20px 50px;
            font-size: 30px;
            font-weight: bold;
            color: white;
            border-radius: 15px;
            cursor: pointer;
            box-shadow: 0 8px 0 #44bd32;
            transition: all 0.1s;
        }

        button:active {
            transform: translateY(4px);
            box-shadow: 0 4px 0 #44bd32;
        }

        .stats {
            font-size: 32px;
            margin-top: 15px;
            font-weight: 900;
        }
    </style>
</head>
<body>

    <h1>ELON'S CASH GEYSER</h1>

    <div class="game-container" id="stage">
        <img src="https://i.imgur.com/8N69w0s.png" id="elon" alt="Elon" onclick="makeItRain()">
        
        <div class="ui">
            <button onclick="makeItRain()">PUSH TO FART MONEY</button>
            <div class="stats">TOTAL: $<span id="score">0</span></div>
        </div>
    </div>

    <script>
        let score = 0;

        function makeItRain() {
            // Update Score
            score += 1000000;
            document.getElementById('score').innerText = score.toLocaleString();

            // Create 10 bills per click
            for(let i = 0; i < 10; i++) {
                const bill = document.createElement('div');
                bill.innerHTML = '💵';
                bill.className = 'bill';
                
                // Position start at Elon's "backside" area
                bill.style.left = '40%';
                bill.style.top = '50%';

                // Random trajectory (shooting mostly left and down)
                const xDist = (Math.random() * -600) - 100 + 'px';
                const yDist = (Math.random() * 400) - 100 + 'px';
                
                bill.style.setProperty('--x', xDist);
                bill.style.setProperty('--y', yDist);

                document.getElementById('stage').appendChild(bill);

                // Remove bill after animation
                setTimeout(() => bill.remove(), 1500);
            }
        }
    </script>
</body>
</html>
