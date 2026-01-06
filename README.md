
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ELON | EMISSION MODE</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&family=Inter:wght@400;900&display=swap');
        body { background-color: #050505; color: #fff; font-family: 'Inter', sans-serif; overflow: hidden; }
        .neon-text { font-family: 'Syncopate', sans-serif; color: #39ff14; text-shadow: 0 0 20px #39ff14; }
        
        .gas-cloud {
            position: absolute; width: 400px; height: 400px;
            background: radial-gradient(circle, rgba(57,255,20,0.1) 0%, rgba(0,0,0,0) 70%);
            filter: blur(60px); animation: drift 15s infinite alternate;
        }
        @keyframes drift { from { transform: translate(-20%, -20%); } to { transform: translate(20%, 20%); } }
    </style>
</head>
<body class="flex items-center justify-center h-screen relative">

    <div class="gas-cloud"></div>

    <div class="relative z-10 text-center bg-black/40 p-8 md:p-12 rounded-[2rem] border border-white/5 backdrop-blur-2xl max-w-lg shadow-2xl">
        
        <div class="mb-8 rounded-3xl overflow-hidden border-2 border-green-500/30 group">
            <img src="https://i.imgur.com/iMPyNbV.jpg" 
                 alt="Elon Musk" 
                 class="w-full h-auto grayscale group-hover:grayscale-0 transition duration-700 scale-105 group-hover:scale-100">
        </div>

        <h1 class="text-4xl md:text-6xl font-black neon-text mb-2 italic tracking-tighter">FART</h1>
        <p class="text-gray-500 uppercase tracking-[0.4em] text-[9px] mb-8 font-bold">Standard on all 2026 Models</p>

        <div class="space-y-6">
            <div class="px-4">
                <label class="block text-[10px] uppercase tracking-widest text-gray-400 mb-2">Blast Intensity</label>
                <input type="range" class="w-full accent-green-500 bg-gray-800 rounded-lg appearance-none cursor-pointer">
            </div>

            <button onclick="playGas()" class="w-full bg-green-500 text-black py-4 rounded-2xl font-black uppercase tracking-widest hover:bg-white transition-all transform active:scale-95 shadow-[0_0_30px_rgba(57,255,20,0.3)]">
                Deploy Emissions
            </button>
        </div>
        
        <div class="mt-8 flex justify-between items-center text-[10px] text-gray-500 font-mono">
            <span>VER: 69.420.X</span>
            <span class="text-green-500 animate-pulse">● SYSTEM READY</span>
        </div>
    </div>

    <script>
        function playGas() {
            // High-quality audio trigger
            const audio = new Audio('https://www.soundjay.com/human/sounds/fart-01.mp3');
            audio.play().catch(() => {
                // Fallback if browser blocks audio
                alert("💨 PRRRRRRRRRRRRRRRRRRRRT!");
            });
        }
    </script>

</body>
</html>
