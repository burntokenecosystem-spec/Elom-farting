
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ELON | THE ART OF THE FART</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Syncopate:wght@400;700&family=Inter:wght@300;900&display=swap');
        body { font-family: 'Inter', sans-serif; background-color: #050505; color: #fff; overflow-x: hidden; }
        .glitch-text { font-family: 'Syncopate', sans-serif; color: #39ff14; text-shadow: 0 0 10px #39ff14; }
        .fart-button:hover { box-shadow: 0 0 30px #39ff14; transform: scale(1.05); }
    </style>
</head>
<body>

    <nav class="flex justify-between items-center p-8 fixed w-full z-50">
        <div class="text-xl font-black tracking-tighter">ELON<span class="text-green-500">GAS</span></div>
        <div class="space-x-6 text-[10px] tracking-[0.3em] font-bold uppercase opacity-70">
            <a href="#">Methane</a>
            <a href="#">Sonic Boom</a>
            <a href="#">Scent-Storage</a>
        </div>
    </nav>

    <main class="h-screen flex flex-col items-center justify-center relative">
        <div class="absolute inset-0 z-0">
            <img src="https://imgur.com/a/73OQ86k.jpg" 
                 alt="Elon Fart" 
                 class="w-full h-full object-cover opacity-40 grayscale hover:grayscale-0 transition duration-700">
            <div class="absolute inset-0 bg-gradient-to-t from-black via-transparent to-black"></div>
        </div>

        <div class="relative z-10 text-center">
            <h2 class="text-xs tracking-[1em] uppercase mb-4 opacity-60">Introducing</h2>
            <h1 class="text-7xl md:text-9xl font-black glitch-text mb-6">FART</h1>
            <p class="max-w-md mx-auto text-gray-400 text-sm leading-relaxed mb-8 uppercase tracking-widest">
                The world's first fully autonomous, AI-driven emission system. Integrated with Grok for maximum comedic timing.
            </p>
            
            <div class="flex flex-col items-center gap-6">
                <button onclick="playFart()" class="fart-button bg-green-500 text-black px-12 py-4 rounded-full font-black text-sm uppercase transition-all duration-300">
                    Pull My Finger
                </button>
                <p class="text-[10px] text-green-500 animate-pulse">SYSTEM STATUS: FULLY LOADED</p>
            </div>
        </div>
    </main>

    <section class="grid grid-cols-1 md:grid-cols-3 border-t border-gray-900 bg-black text-center py-16">
        <div class="p-4">
            <h4 class="text-3xl font-black">120 dB</h4>
            <p class="text-xs text-gray-500 uppercase tracking-widest">Acoustic Power</p>
        </div>
        <div class="p-4 border-x border-gray-900">
            <h4 class="text-3xl font-black">AI-SYNC</h4>
            <p class="text-xs text-gray-500 uppercase tracking-widest">Grok-Enhanced Timing</p>
        </div>
        <div class="p-4">
            <h4 class="text-3xl font-black">∞</h4>
            <p class="text-xs text-gray-500 uppercase tracking-widest">Entertainment Value</p>
        </div>
    </section>

    <script>
        function playFart() {
            // This is where the magic happens
            alert("💨 PFRRRRRRRRRT! (Emission Mode Activated)");
        }
    </script>

</body>
</html>
