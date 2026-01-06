
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Musk Innovation Button</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #0b0e14; /* Dark space-like theme */
            color: white;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        .container {
            text-align: center;
            background: #161b22;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            border: 1px solid #30363d;
        }

        h1 {
            margin-bottom: 20px;
            font-size: 24px;
            background: linear-gradient(45deg, #1d9bf0, #00ba7c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .image-wrapper {
            margin-bottom: 20px;
        }

        img {
            width: 250px;
            height: 250px;
            border-radius: 15px;
            object-fit: cover;
            border: 3px solid #30363d;
        }

        #fart-button {
            padding: 15px 30px;
            font-size: 20px;
            font-weight: bold;
            color: white;
            background: linear-gradient(45deg, #1d9bf0, #00ba7c);
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: transform 0.1s, filter 0.2s;
        }

        #fart-button:hover {
            filter: brightness(1.1);
        }

        #fart-button:active {
            transform: scale(0.95);
        }

        .counter {
            margin-top: 15px;
            font-size: 18px;
            color: #8b949e;
        }

        /* Shake animation for when he "farts" */
        @keyframes shake {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            40% { transform: translate(3px, 2px) rotate(-1deg); }
            60% { transform: translate(-1px, -1px) rotate(1deg); }
            80% { transform: translate(-3px, 1px) rotate(0deg); }
            100% { transform: translate(1px, -2px) rotate(-1deg); }
        }

        .shake-effect {
            animation: shake 0.3s;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>X-TREME INNOVATION</h1>
        
        <div class="image-wrapper">
            <img id="elon-img" src="https://r.jina.ai/i/9e0066d091e94875883bc20d37e6097e" alt="Elon Musk Cartoon">
        </div>

        <button id="fart-button">Press for Innovation</button>

        <div class="counter">
            Total Innovations: <span id="count">0</span>
        </div>
    </div>

    <audio id="fart-sound" src="fart.mp3"></audio>

    <script>
        const button = document.getElementById('fart-button');
        const sound = document.getElementById('fart-sound');
        const img = document.getElementById('elon-img');
        const countDisplay = document.getElementById('count');
        
        let count = 0;

        button.addEventListener('click', () => {
            // 1. Play Sound
            sound.currentTime = 0; 
            sound.play();

            // 2. Update Counter
            count++;
            countDisplay.innerText = count;

            // 3. Shake Image
            img.classList.add('shake-effect');
            setTimeout(() => {
                img.classList.remove('shake-effect');
            }, 300);
        });
    </script>

</body>
</html>
