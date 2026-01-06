
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ELON | ACTION MODE</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&family=Inter:wght@400;900&display=swap');
        body { background-color: #050505; color: #fff; font-family: 'Inter', sans-serif; overflow: hidden; }
        .neon-text { font-family: 'Syncopate', sans-serif; color: #39ff14; text-shadow: 0 0 20px #39ff14; }

        /* The "Struggle" Shake Animation */
        @keyframes shake {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            10% { transform: translate(-1px, -2px) rotate(-1deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            30% { transform: translate(3px, 2px) rotate(0deg); }
            40% { transform: translate(1px, -1px) rotate(1deg); }
            50% { transform: translate(-1px, 2px) rotate(-1deg); }
            60% { transform: translate(-3px, 1px) rotate(0deg); }
            70% { transform: translate(3px, 1px) rotate(-1deg); }
            80% { transform: translate(-1px, -1px) rotate(1deg); }
            90% { transform: translate(1px, 2px) rotate(0deg); }
            100% { transform: translate(1px, -2px) rotate(-1deg); }
        }

        .animate-shake {
            animation: shake 0.2s;
            animation-iteration-count: 3; /* Shakes 3 times fast */
        }

        /* Gas Cloud Burst */
        #gas-burst {
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(57,255,20,0.6) 0%, rgba(0,0,0,0) 70%);
            opacity: 0;
            transition: opacity 0.1s;
            pointer-events: none;
            z-index: 5;
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen relative p-4">

    <div class="relative z-10 text-center bg-black/60 p-8 md:p-12 rounded-[2.5rem] border border-white/10 backdrop-blur-3xl max-w-lg shadow-2xl">
        
        <div class="relative mb-8 rounded-2xl overflow-hidden border-2 border-green-500/50 shadow-[0_0_25px_rgba(57,255,20,0.2)]">
            <div id="gas-burst"></div> <img id="elon-img" src="https://i.ibb.co/WvZFVqjP/undefined-Imgur.jpg" 
                 alt="Elon Musk Action" 
                 class="w-full h-auto block grayscale hover:grayscale-0 transition duration-700">
        </div>

        <h1 class="text-4xl font-black neon-text mb-2 italic">ACTIVATE</h1>
        <p class="text-gray-500 uppercase tracking-[0.4em] text-[10px] mb-10 font-bold">Bio-Weapon Defense Mode</p>

        <button onclick="deployEmissions()" class="w-full bg-green-500 text-black py-5 rounded-2xl font-black uppercase tracking-widest hover:bg-white transition-all transform active:scale-90 shadow-lg">
            Deploy Blast
        </button>
    </div>

    <script>
        function deployEmissions() {
            const img = document.getElementById('elon-img');
            const burst = document.getElementById('gas-burst');
            
            // 1. Trigger the Shake
            img.classList.remove('animate-shake');
            void img.offsetWidth; // Reset animation
            img.classList.add('animate-shake');

            // 2. Trigger the Flash of Gas
            burst.style.opacity = '1';
            setTimeout(() => { burst.style.opacity = '0'; }, 300);

            // 3. Play Sound
            const audio = new Audio('https://www.soundjay.com/human/sounds/fart-01.mp3');
            audio.play().catch(() => {
                console.log("Audio blocked by browser.");
            });
        }
    </script>

</body>
</html>
