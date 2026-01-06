
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ELON | EMISSIONS MODE</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@700&family=Inter:wght@400;900&display=swap');
        body { background-color: #050505; color: #fff; font-family: 'Inter', sans-serif; overflow-x: hidden; }
        .neon-text { font-family: 'Syncopate', sans-serif; color: #39ff14; text-shadow: 0 0 20px #39ff14; }
        
        /* Floating Gas Animation */
        .gas-cloud {
            position: absolute; width: 400px; height: 400px;
            background: radial-gradient(circle, rgba(57,255,20,0.1) 0%, rgba(0,0,0,0) 70%);
            filter: blur(60px); animation: drift 15s infinite alternate; z-index: 0;
        }
        @keyframes drift { from { transform: translate(-20%, -20%); } to { transform: translate(20%, 20%); } }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen relative p-4">

    <div class="gas-cloud"></div>

    <div class="relative z-10 text-center bg-black/60 p-8 md:p-12 rounded-[2.5rem] border border-white/10 backdrop-blur-3xl max-w-lg shadow-2xl">
        
        <div class="mb-8 rounded-2xl overflow-hidden border-2 border-green-500/50 shadow-[0_0_25px_rgba(57,255,20,0.2)]">
            <img src="https://i.ibb.co/WvZFVqjP/undefined-Imgur.jpg" 
                 alt="Elon Musk Fart Mode" 
                 class="w-full h-auto block grayscale hover:grayscale-0 transition duration-700 cursor-crosshair">
        </div>

        <h1 class="text-5xl font-black neon-text mb-2 italic tracking-tighter">FART</h1>
        <p class="text-gray-500 uppercase tracking-[0.4em] text-[10px] mb-10 font-bold italic">Software Update: v2026.69.420</p>

        <div class="space-y-4">
            <button onclick="playGas()" class="w-full bg-green-500 text-black py-5 rounded-2xl font-black uppercase tracking-widest hover:bg-white transition-all transform active:scale-95 shadow-lg">
                Deploy "Falcon Heavy"
            </button>
            <p class="text-[10px] text-gray-600 font-mono italic">"The most entertaining outcome is the most likely."</p>
        </div>
        
        <div class="mt-8 pt-6 border-t border-white/5 flex justify-between items-center text-[9px] text-gray-500 font-bold tracking-widest uppercase">
            <span>Neuralink Sync</span>
            <span class="text-green-500 animate-pulse">● Connected</span>
        </div>
    </div>

    <script>
        function playGas() {
            // High-quality fart sound
            const audio = new Audio('https://www.soundjay.com/human/sounds/fart-01.mp3');
            audio.play().catch(() => {
                // If browser blocks sound, show the visual alert
                alert("💨 PRRRRRRRRRRT! (Emission Mode Activated)");
            });
        }
    </script>

</body>
</html>
