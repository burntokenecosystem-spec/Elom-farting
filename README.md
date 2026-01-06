
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EFART ELON | THE FUTURE</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@400;900&family=Space+Grotesk:wght@700&display=swap');
        
        body { 
            margin: 0;
            background: linear-gradient(45deg, #0f0c29, #302b63, #24243e, #00d2ff);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            font-family: 'Outfit', sans-serif;
            color: #fff;
            overflow-x: hidden;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .glass {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.8);
        }

        .neon-btn {
            background: linear-gradient(90deg, #ff00cc, #3333ff);
            background-size: 200%;
            transition: 0.5s;
        }
        .neon-btn:hover {
            background-position: right;
            box-shadow: 0 0 25px #ff00cc;
            transform: scale(1.02);
        }

        @keyframes shake {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            20% { transform: translate(-3px, 0px) rotate(1deg); }
            40% { transform: translate(3px, 2px) rotate(0deg); }
            60% { transform: translate(-3px, 1px) rotate(-1deg); }
            80% { transform: translate(-1px, -1px) rotate(1deg); }
            100% { transform: translate(1px, -2px) rotate(-1deg); }
        }
        .animate-shake { animation: shake 0.15s ease-in-out infinite; }

        .token-badge {
            background: linear-gradient(90deg, #39ff14, #00ffcc);
            color: #000;
            font-family: 'Space Grotesk', sans-serif;
        }
    </style>
</head>
<body class="flex flex-col items-center justify-center min-h-screen p-4">

    <div class="fixed top-0 w-full bg-gradient-to-r from-yellow-400 via-red-500 to-pink-500 text-white p-2 text-center font-black text-xs uppercase tracking-widest z-50">
        🚀 [AD] TO THE MOON! BUY $EFART TOKEN BEFORE IT PUMPS 🚀
    </div>

    <div class="fixed top-12 right-6 token-badge px-6 py-3 rounded-2xl font-black text-lg shadow-xl flex items-center gap-2 z-50">
        <span class="text-xl">💨</span> <span id="token-count">0</span> $EFART
    </div>

    <div class="glass relative z-10 w-full max-w-md p-8 rounded-[3rem] text-center">
        
        <div class="relative group">
            <div id="glow" class="absolute -inset-1 bg-gradient-to-r from-pink-600 to-purple-600 rounded-3xl blur opacity-25 group-hover:opacity-100 transition duration-1000 group-hover:duration-200"></div>
            <div class="relative bg-black rounded-2xl overflow-hidden border border-white/10">
                <img id="elon-img" src="https://i.ibb.co/WvZFVqjP/undefined-Imgur.jpg" 
                     class="w-full h-auto block transition duration-500 group-hover:scale-110">
            </div>
        </div>

        <h1 class="mt-8 text-5xl font-black tracking-tighter uppercase italic text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-emerald-400">
            FART MINER
        </h1>
        <p class="text-gray-400 text-xs font-bold tracking-[0.3em] mt-2 mb-8">ULTIMATE EMISSION ENGINE</p>

        <button onclick="mineTokens()" class="neon-btn w-full py-5 rounded-2xl font-black text-white uppercase tracking-widest shadow-2xl active:scale-95">
            RELEASE & MINE
        </button>

        <p class="mt-4 text-[10px] text-gray-500 uppercase tracking-widest">+10 Tokens
