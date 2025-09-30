<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Header Animation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background-color: #0f172a;
            color: #ffffff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            overflow-x: hidden;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            padding: 20px;
        }
        
        h1 {
            text-align: center;
            margin-bottom: 40px;
            color: #22d3ee;
            font-weight: 600;
        }
        
        .animation-options {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }
        
        .option-btn {
            background: rgba(34, 211, 238, 0.1);
            border: 1px solid #22d3ee;
            color: #22d3ee;
            padding: 10px 20px;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 500;
        }
        
        .option-btn:hover {
            background: rgba(34, 211, 238, 0.2);
            transform: translateY(-2px);
        }
        
        .option-btn.active {
            background: #22d3ee;
            color: #0f172a;
        }
        
        .header-container {
            position: relative;
            width: 100%;
            height: 250px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            margin-bottom: 40px;
        }
        
        /* Base header styles */
        .github-header {
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            overflow: hidden;
        }
        
        .name {
            font-size: 2.5rem;
            font-weight: 700;
            text-align: center;
            z-index: 10;
            position: relative;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
        }
        
        .name span {
            color: #22d3ee;
        }
        
        /* Animation 1: Particle Background */
        .particle {
            position: absolute;
            background: #22d3ee;
            border-radius: 50%;
            opacity: 0.7;
        }
        
        /* Animation 2: Gradient Waves */
        .wave {
            position: absolute;
            bottom: 0;
            left: 0;
            width: 200%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(34, 211, 238, 0.2), transparent);
            transform-origin: bottom;
        }
        
        /* Animation 3: Floating Shapes */
        .shape {
            position: absolute;
            border-radius: 50%;
            background: rgba(34, 211, 238, 0.1);
            border: 1px solid rgba(34, 211, 238, 0.3);
        }
        
        /* Animation 4: Neon Glow */
        .neon-glow {
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle, rgba(34, 211, 238, 0.2) 0%, transparent 70%);
            filter: blur(20px);
            opacity: 0;
        }
        
        /* Animation 5: Matrix Rain */
        .matrix-char {
            position: absolute;
            color: #22d3ee;
            font-family: monospace;
            font-size: 18px;
            opacity: 0;
        }
        
        .code-block {
            background: #1e293b;
            border-radius: 10px;
            padding: 20px;
            margin-top: 30px;
            overflow-x: auto;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .code-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .code-title {
            font-weight: 600;
            color: #22d3ee;
        }
        
        .copy-btn {
            background: rgba(34, 211, 238, 0.1);
            border: 1px solid #22d3ee;
            color: #22d3ee;
            padding: 5px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .copy-btn:hover {
            background: rgba(34, 211, 238, 0.2);
        }
        
        pre {
            color: #e2e8f0;
            font-family: 'Courier New', Courier, monospace;
            line-height: 1.5;
        }
        
        .token.comment {
            color: #64748b;
        }
        
        .token.property {
            color: #22d3ee;
        }
        
        .token.value {
            color: #f472b6;
        }
        
        .token.selector {
            color: #34d399;
        }
        
        .token.punctuation {
            color: #e2e8f0;
        }
        
        @media (max-width: 768px) {
            .name {
                font-size: 1.8rem;
            }
            
            .animation-options {
                gap: 10px;
            }
            
            .option-btn {
                padding: 8px 16px;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>GitHub Profile Header Animation</h1>
        
        <div class="animation-options">
            <button class="option-btn active" data-animation="particles">Particles</button>
            <button class="option-btn" data-animation="waves">Gradient Waves</button>
            <button class="option-btn" data-animation="shapes">Floating Shapes</button>
            <button class="option-btn" data-animation="neon">Neon Glow</button>
            <button class="option-btn" data-animation="matrix">Matrix Rain</button>
        </div>
        
        <div class="header-container">
            <div class="github-header" id="header">
                <h1 class="name">Hi 👋, I'm <span>Madhawa Diyanath Swarnakantha</span></h1>
            </div>
        </div>
        
        <div class="code-block">
            <div class="code-header">
                <div class="code-title">HTML & CSS Code</div>
                <button class="copy-btn" id="copyBtn">Copy Code</button>
            </div>
            <pre><code id="codeSnippet">&lt;div align="center"&gt;
  &lt;!-- Your selected animation will be rendered here --&gt;
&lt;/div&gt;</code></pre>
        </div>
    </div>

    <script>
        // Animation selection
        const optionBtns = document.querySelectorAll('.option-btn');
        const header = document.getElementById('header');
        const codeSnippet = document.getElementById('codeSnippet');
        const copyBtn = document.getElementById('copyBtn');
        
        let currentAnimation = 'particles';
        let animationInterval;
        
        // Set active button
        optionBtns.forEach(btn => {
            btn.addEventListener('click', () => {
                optionBtns.forEach(b => b.classList.remove('active'));
                btn.classList.add('active');
                currentAnimation = btn.getAttribute('data-animation');
                clearAnimation();
                initAnimation();
                updateCodeSnippet();
            });
        });
        
        // Clear existing animation
        function clearAnimation() {
            // Remove all animation elements
            const elementsToRemove = document.querySelectorAll('.particle, .wave, .shape, .neon-glow, .matrix-char');
            elementsToRemove.forEach(el => el.remove());
            
            // Clear any intervals
            if (animationInterval) {
                clearInterval(animationInterval);
            }
        }
        
        // Initialize selected animation
        function initAnimation() {
            switch(currentAnimation) {
                case 'particles':
                    initParticles();
                    break;
                case 'waves':
                    initWaves();
                    break;
                case 'shapes':
                    initShapes();
                    break;
                case 'neon':
                    initNeon();
                    break;
                case 'matrix':
                    initMatrix();
                    break;
            }
        }
        
        // Particle animation
        function initParticles() {
            for (let i = 0; i < 50; i++) {
                createParticle();
            }
            
            animationInterval = setInterval(() => {
                if (document.querySelectorAll('.particle').length < 50) {
                    createParticle();
                }
            }, 500);
        }
        
        function createParticle() {
            const particle = document.createElement('div');
            particle.classList.add('particle');
            
            const size = Math.random() * 6 + 2;
            particle.style.width = `${size}px`;
            particle.style.height = `${size}px`;
            
            particle.style.left = `${Math.random() * 100}%`;
            particle.style.top = `${Math.random() * 100}%`;
            
            header.appendChild(particle);
            
            // Animate particle
            const duration = Math.random() * 10 + 5;
            const keyframes = [
                { transform: 'translate(0, 0)', opacity: 0 },
                { transform: `translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px)`, opacity: 0.7 },
                { transform: `translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px)`, opacity: 0 }
            ];
            
            particle.animate(keyframes, {
                duration: duration * 1000,
                easing: 'ease-in-out'
            });
            
            // Remove particle after animation
            setTimeout(() => {
                if (particle.parentNode) {
                    particle.remove();
                }
            }, duration * 1000);
        }
        
        // Wave animation
        function initWaves() {
            for (let i = 0; i < 3; i++) {
                createWave(i);
            }
        }
        
        function createWave(index) {
            const wave = document.createElement('div');
            wave.classList.add('wave');
            
            wave.style.background = `linear-gradient(90deg, transparent, rgba(34, 211, 238, ${0.1 + index * 0.1}), transparent)`;
            wave.style.bottom = `${index * 20}px`;
            
            header.appendChild(wave);
            
            // Animate wave
            const keyframes = [
                { transform: 'translateX(-50%)' },
                { transform: 'translateX(0%)' }
            ];
            
            wave.animate(keyframes, {
                duration: 8000 + index * 2000,
                iterations: Infinity,
                easing: 'linear'
            });
        }
        
        // Floating shapes animation
        function initShapes() {
            for (let i = 0; i < 15; i++) {
                createShape();
            }
        }
        
        function createShape() {
            const shape = document.createElement('div');
            shape.classList.add('shape');
            
            const size = Math.random() * 60 + 20;
            shape.style.width = `${size}px`;
            shape.style.height = `${size}px`;
            
            shape.style.left = `${Math.random() * 100}%`;
            shape.style.top = `${Math.random() * 100}%`;
            
            header.appendChild(shape);
            
            // Animate shape
            const duration = Math.random() * 20 + 10;
            const keyframes = [
                { transform: 'translate(0, 0) rotate(0deg)' },
                { transform: `translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px) rotate(${Math.random() * 360}deg)` }
            ];
            
            shape.animate(keyframes, {
                duration: duration * 1000,
                iterations: Infinity,
                direction: 'alternate',
                easing: 'ease-in-out'
            });
        }
        
        // Neon glow animation
        function initNeon() {
            const glow = document.createElement('div');
            glow.classList.add('neon-glow');
            
            header.appendChild(glow);
            
            // Animate glow
            const keyframes = [
                { opacity: 0, transform: 'scale(1)' },
                { opacity: 0.7, transform: 'scale(1.2)' },
                { opacity: 0, transform: 'scale(1.4)' }
            ];
            
            glow.animate(keyframes, {
                duration: 4000,
                iterations: Infinity,
                easing: 'ease-in-out'
            });
        }
        
        // Matrix rain animation
        function initMatrix() {
            const chars = '01';
            const headerWidth = header.offsetWidth;
            const headerHeight = header.offsetHeight;
            const columns = Math.floor(headerWidth / 20);
            
            for (let i = 0; i < columns; i++) {
                createMatrixColumn(i, chars);
            }
        }
        
        function createMatrixColumn(columnIndex, chars) {
            const startDelay = Math.random() * 5000;
            
            setTimeout(() => {
                const createChar = () => {
                    const char = document.createElement('div');
                    char.classList.add('matrix-char');
                    char.textContent = chars.charAt(Math.floor(Math.random() * chars.length));
                    
                    char.style.left = `${columnIndex * 20}px`;
                    char.style.top = `-20px`;
                    
                    header.appendChild(char);
                    
                    // Animate char
                    const duration = Math.random() * 3000 + 2000;
                    const keyframes = [
                        { top: '-20px', opacity: 0 },
                        { opacity: 1 },
                        { top: `${headerHeight}px`, opacity: 0 }
                    ];
                    
                    char.animate(keyframes, {
                        duration: duration,
                        easing: 'linear'
                    });
                    
                    // Remove char after animation
                    setTimeout(() => {
                        if (char.parentNode) {
                            char.remove();
                        }
                    }, duration);
                };
                
                // Create characters at intervals
                const interval = setInterval(createChar, 100);
                
                // Stop after a while and restart with delay
                setTimeout(() => {
                    clearInterval(interval);
                    setTimeout(() => {
                        createMatrixColumn(columnIndex, chars);
                    }, Math.random() * 10000 + 5000);
                }, Math.random() * 15000 + 10000);
                
            }, startDelay);
        }
        
        // Update code snippet based on selected animation
        function updateCodeSnippet() {
            let code = '';
            
            switch(currentAnimation) {
                case 'particles':
                    code = `&lt;div align="center"&gt;
  &lt;img src="https://capsule-render.vercel.app/api?type=waving&color=22d3ee&height=250&section=header&text=Hi%20👋,%20I'm%20Madhawa%20Diyanath%20Swarnakantha&fontSize=40&fontColor=ffffff&animation=fadeIn&fontAlignY=40" /&gt;
  &lt;!-- Add particle animation with JavaScript --&gt;
&lt;/div&gt;`;
                    break;
                case 'waves':
                    code = `&lt;div align="center"&gt;
  &lt;!-- Wave animation background --&gt;
  &lt;svg viewBox="0 0 1200 120" preserveAspectRatio="none"&gt;
    &lt;path d="M0,0V46.29c47.79,22.2,103.59,32.17,158,28,70.36-5.37,136.33-33.31,206.8-37.5C438.64,32.43,512.34,53.67,583,72.05c69.27,18,138.3,24.88,209.4,13.08,36.15-6,69.85-17.84,104.45-29.34C989.49,25,1113-14.29,1200,52.47V0Z" opacity=".25" fill="#22d3ee"&gt;&lt;/path&gt;
    &lt;path d="M0,0V15.81C13,36.92,27.64,56.86,47.69,72.05,99.41,111.27,165,111,224.58,91.58c31.15-10.15,60.09-26.07,89.67-39.8,40.92-19,84.73-46,130.83-49.67,36.26-2.85,70.9,9.42,98.6,31.56,31.77,25.39,62.32,62,103.63,73,40.44,10.79,81.35-6.69,119.13-24.28s75.16-39,116.92-43.05c59.73-5.85,113.28,22.88,168.9,38.84,30.2,8.66,59,6.17,87.09-7.5,22.43-10.89,48-26.93,60.65-49.24V0Z" opacity=".5" fill="#22d3ee"&gt;&lt;/path&gt;
    &lt;path d="M0,0V5.63C149.93,59,314.09,71.32,475.83,42.57c43-7.64,84.23-20.12,127.61-26.46,59-8.63,112.48,12.24,165.56,35.4C827.93,77.22,886,95.24,951.2,90c86.53-7,172.46-45.71,248.8-84.81V0Z" fill="#22d3ee"&gt;&lt;/path&gt;
  &lt;/svg&gt;
  &lt;h1&gt;Hi 👋, I'm Madhawa Diyanath Swarnakantha&lt;/h1&gt;
&lt;/div&gt;`;
                    break;
                case 'shapes':
                    code = `&lt;div align="center"&gt;
  &lt;!-- Floating shapes background --&gt;
  &lt;div class="shapes-container"&gt;
    &lt;div class="shape"&gt;&lt;/div&gt;
    &lt;div class="shape"&gt;&lt;/div&gt;
    &lt;div class="shape"&gt;&lt;/div&gt;
    &lt;!-- Add more shapes --&gt;
  &lt;/div&gt;
  &lt;h1&gt;Hi 👋, I'm Madhawa Diyanath Swarnakantha&lt;/h1&gt;
&lt;/div&gt;

&lt;style&gt;
  .shapes-container {
    position: relative;
    width: 100%;
    height: 250px;
    overflow: hidden;
  }
  
  .shape {
    position: absolute;
    border-radius: 50%;
    background: rgba(34, 211, 238, 0.1);
    border: 1px solid rgba(34, 211, 238, 0.3);
    animation: float 15s infinite ease-in-out;
  }
  
  @keyframes float {
    0%, 100% { transform: translate(0, 0) rotate(0deg); }
    50% { transform: translate(30px, -30px) rotate(180deg); }
  }
&lt;/style&gt;`;
                    break;
                case 'neon':
                    code = `&lt;div align="center"&gt;
  &lt;!-- Neon glow effect --&gt;
  &lt;div class="neon-container"&gt;
    &lt;h1 class="neon-text"&gt;Hi 👋, I'm Madhawa Diyanath Swarnakantha&lt;/h1&gt;
  &lt;/div&gt;
&lt;/div&gt;

&lt;style&gt;
  .neon-container {
    position: relative;
    padding: 2rem;
    background: #0f172a;
  }
  
  .neon-text {
    color: #fff;
    text-shadow: 
      0 0 5px #22d3ee,
      0 0 10px #22d3ee,
      0 0 20px #22d3ee,
      0 0 40px #22d3ee;
    animation: neon-pulse 2s infinite alternate;
  }
  
  @keyframes neon-pulse {
    from {
      text-shadow: 
        0 0 5px #22d3ee,
        0 0 10px #22d3ee,
        0 0 20px #22d3ee,
        0 0 40px #22d3ee;
    }
    to {
      text-shadow: 
        0 0 10px #22d3ee,
        0 0 20px #22d3ee,
        0 0 30px #22d3ee,
        0 0 50px #22d3ee;
    }
  }
&lt;/style&gt;`;
                    break;
                case 'matrix':
                    code = `&lt;div align="center"&gt;
  &lt;!-- Matrix rain background --&gt;
  &lt;canvas id="matrixCanvas"&gt;&lt;/canvas&gt;
  &lt;h1&gt;Hi 👋, I'm Madhawa Diyanath Swarnakantha&lt;/h1&gt;
&lt;/div&gt;

&lt;script&gt;
  const canvas = document.getElementById('matrixCanvas');
  const ctx = canvas.getContext('2d');
  
  canvas.width = window.innerWidth;
  canvas.height = 250;
  
  const chars = "01";
  const charArray = chars.split("");
  const fontSize = 14;
  const columns = canvas.width / fontSize;
  const drops = [];
  
  for (let i = 0; i < columns; i++) {
    drops[i] = 1;
  }
  
  function drawMatrix() {
    ctx.fillStyle = "rgba(15, 23, 42, 0.04)";
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    
    ctx.fillStyle = "#22d3ee";
    ctx.font = fontSize + "px monospace";
    
    for (let i = 0; i < drops.length; i++) {
      const text = charArray[Math.floor(Math.random() * charArray.length)];
      ctx.fillText(text, i * fontSize, drops[i] * fontSize);
      
      if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) {
        drops[i] = 0;
      }
      drops[i]++;
    }
  }
  
  setInterval(drawMatrix, 35);
&lt;/script&gt;`;
                    break;
            }
            
            codeSnippet.textContent = code;
        }
        
        // Copy code to clipboard
        copyBtn.addEventListener('click', () => {
            const textArea = document.createElement('textarea');
            textArea.value = codeSnippet.textContent;
            document.body.appendChild(textArea);
            textArea.select();
            document.execCommand('copy');
            document.body.removeChild(textArea);
            
            // Visual feedback
            const originalText = copyBtn.textContent;
            copyBtn.textContent = 'Copied!';
            setTimeout(() => {
                copyBtn.textContent = originalText;
            }, 2000);
        });
        
        // Initialize with particles animation
        initAnimation();
        updateCodeSnippet();
    </script>
</body>
</html>
