
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EFART ELON | v2.0 FIXED</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@400;900&display=swap');
        body { 
            background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
            background-size: 400% 400%;
            animation: gradient 15s ease infinite;
            font-family: 'Outfit', sans-serif;
            color: white; min-height: screen;
        }
        @keyframes gradient { 0% { background-position: 0% 50%; } 50% { background-position: 100% 50%; } 100% { background-position: 0% 50%; } }
        
        .glass-panel { background: rgba(0, 0, 0, 0.7); backdrop-filter: blur(20px); border: 1px solid rgba(255,255,255,0.1); }
        
        @keyframes shake {
            0%, 100% { transform: translate(0,0); }
            25% { transform: translate(-5px, 5px); }
            50% { transform: translate(5px, -5px); }
            75% { transform: translate(-5px, -5px); }
        }
        .shaking { animation: shake 0.1s linear infinite; }
        
        /* Video Ad Overlay */
        #video-ad-container {
            display: none; position: fixed; inset: 0; z-index: 999;
            background: black; flex-direction: column; align-items: center; justify-content: center;
        }
    </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen p-4">

    <div class="fixed top-6 right-6 bg-white text-black px-8 py-3 rounded-full font-black text-xl shadow-2xl z-50">
        $EFART: <span id="token-count">0</span>
    </div>

    <div class="glass-panel p-10 rounded-[3rem] text-center max-w-sm w-full shadow-2xl">
        <div class="relative mb-6 rounded-3xl overflow-hidden border-4 border-white/20">
            <img id="elon-img" src="https://i.ibb.co/WvZFVqjP/undefined-Imgur.jpg" class="w-full h-auto">
        </div>

        <h1 class="text-4xl font-black italic mb-6 tracking-tighter">MINER v2.0</h1>

        <button onclick="handleMine()" class="w-full bg-gradient-to-r from-blue-500 to-purple-600 py-5 rounded-2xl font-black text-xl shadow-lg active:scale-90 transition-transform">
            RELEASE GAS
        </button>
    </div>

    <div id="video-ad-container">
        <p class="text-gray-400 text-xs mb-4 uppercase tracking-widest">Advertisement</p>
        <div class="w-full max-w-lg aspect-video bg-gray-900 flex items-center justify-center relative rounded-xl overflow-hidden border border-white/10">
            <p class="text-white font-bold animate-pulse">Loading High-Def Crypto Ad...</p>
            <div class="absolute bottom-0 left-0 h-1 bg-yellow-500 transition-all duration-[5000ms] w-0" id="ad-progress"></div>
        </div>
        <button id="skip-btn" disabled class="mt-8 bg-white/10 text-gray-500 px-10 py-3 rounded-lg font-bold">
            Skip Ad in <span id="timer">5</span>...
        </button>
    </div>

    <script>
        let tokens = 0;
        const countDisplay = document.getElementById('token-count');
        const elonImg = document.getElementById('elon-img');
        const adContainer = document.getElementById('video-ad-container');
        const skipBtn = document.getElementById('skip-btn');
        const timerDisplay = document.getElementById('timer');
        const adProgress = document.getElementById('ad-progress');

        function handleMine() {
            // 1. Force update tokens
            tokens += 10;
            countDisplay.innerHTML = tokens;

            // 2. Shake Elon
            elonImg.classList.add('shaking');
            setTimeout(() => elonImg.classList.remove('shaking'), 300);

            // 3. Play sound (optional, remove if annoying)
            new Audio('https://www.soundjay.com/human/sounds/fart-01.mp3').play().catch(()=>{});

            // 4. Trigger Ad every 30 tokens
            if (tokens % 30 === 0) {
                showAd();
            }
        }

        function showAd() {
            adContainer.style.display = 'flex';
            let timeLeft = 5;
            timerDisplay.innerText = timeLeft;
            skipBtn.disabled = true;
            adProgress.style.width = '0%';
            
            // Start progress bar
            setTimeout(() => { adProgress.style.width = '100%'; }, 50);

            const countdown = setInterval(() => {
                timeLeft--;
                timerDisplay.innerText = timeLeft;
                if (timeLeft <= 0) {
                    clearInterval(countdown);
                    skipBtn.disabled = false;
                    skipBtn.classList.remove('bg-white/10', 'text-gray-500');
                    skipBtn.classList.add('bg-white', 'text-black');
                    skipBtn.innerText = "SKIP AD";
                    skipBtn.onclick = () => {
                        adContainer.style.display = 'none';
                        // Reset button for next time
                        skipBtn.innerText = "Skip Ad in 5...";
                    };
                }
            }, 1000);
        }
    </script>
</body>
</html>
