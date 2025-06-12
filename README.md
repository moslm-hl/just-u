# for-u
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Message for You</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .container {
            text-align: center;
            max-width: 800px;
            width: 100%;
        }

        .big-button {
            background: rgba(255, 255, 255, 0.9);
            border: none;
            border-radius: 20px;
            padding: 40px 60px;
            font-size: 2.5rem;
            font-weight: bold;
            color: #4c63d2;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            margin-bottom: 30px;
            backdrop-filter: blur(10px);
        }

        .big-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
            background: rgba(255, 255, 255, 1);
        }

        .big-button:active {
            transform: translateY(-2px);
        }

        .message {
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(10px);
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
            margin-top: 30px;
            line-height: 1.8;
            font-size: 1.2rem;
            color: #333;
            text-align: left;
        }

        .message.show {
            opacity: 1;
            transform: translateY(0);
        }

        .message p {
            margin-bottom: 1.5rem;
        }

        .message p:last-child {
            margin-bottom: 0;
            font-weight: bold;
            color: #4c63d2;
        }

        .floating-elements {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .flower, .heart {
            position: absolute;
            font-size: 25px;
            animation: float 8s ease-in-out infinite;
        }

        .flower.pink { color: rgba(255, 182, 193, 0.8); }
        .flower.purple { color: rgba(221, 160, 221, 0.8); }
        .flower.yellow { color: rgba(255, 255, 224, 0.8); }
        .flower.white { color: rgba(255, 255, 255, 0.7); }
        .flower.lavender { color: rgba(230, 230, 250, 0.8); }

        .heart.red { color: rgba(255, 99, 132, 0.8); }
        .heart.pink { color: rgba(255, 182, 193, 0.8); }
        .heart.purple { color: rgba(221, 160, 221, 0.8); }
        .heart.white { color: rgba(255, 255, 255, 0.7); }

        .background-flowers {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -2;
        }

        .bg-flower, .bg-heart {
            position: absolute;
            font-size: 40px;
            opacity: 0.1;
            animation: sway 10s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10%, 90% { opacity: 1; }
            50% { transform: translateY(-20vh) rotate(360deg); }
        }

        @keyframes sway {
            0%, 100% { transform: rotate(-5deg) scale(1); }
            50% { transform: rotate(5deg) scale(1.1); }
        }vh) rotate(360deg); }
        }

        @keyframes sway {
            0%, 100% { transform: rotate(-5deg) scale(1); }
            50% { transform: rotate(5deg) scale(1.1); }
        }
    </style>
</head>
<body>
    <div class="background-flowers" id="bgFlowers"></div>
    <div class="floating-elements" id="floatingFlowers"></div>
    
    <div class="container">
        <button class="big-button" onclick="showMessage()">
            Click on me
        </button>
        
        <div class="message" id="message">
            <p>I know things feel heavy right now, and I can't pretend to understand exactly what we're going through. But I want us to know that we matter more than we might feel in this moment. The pain we're experiencing is real, but it's not permanent - even when it feels like it will never end.</p>
            
            <p>Please don't give up on me. We have strength inside us, even if it feels completely absent right now. Sometimes we have to borrow hope from others until we can find our own again, and that's okay.</p>
            
            <p>We deserve care, compassion, and the chance to see what tomorrow might bring.</p>
            
            <p>Let's take it one breath at a time, one moment at a time. That's enough for now.</p>
        </div>
    </div>

    <script>
        function showMessage() {
            const message = document.getElementById('message');
            const button = document.querySelector('.big-button');
            
            message.classList.add('show');
            button.style.display = 'none';
            
            // Create floating flowers effect
            createFloatingFlowers();
        }

        function createFloatingFlowers() {
            const flowersContainer = document.getElementById('floatingFlowers');
            
            const flowers = ['🌸', '🌺', '🌼', '🌻', '🌷', '🌹', '💐', '🌿', '🌾', '🍀'];
            const hearts = ['💖', '💕', '💗', '❤️', '💜', '💙', '🤍', '💛'];
            const flowerColors = ['pink', 'purple', 'yellow', 'white', 'lavender'];
            const heartColors = ['red', 'pink', 'purple', 'white'];
            
            // Create floating flowers
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const flower = document.createElement('div');
                    flower.className = 'flower ' + flowerColors[Math.floor(Math.random() * flowerColors.length)];
                    flower.innerHTML = flowers[Math.floor(Math.random() * flowers.length)];
                    flower.style.left = Math.random() * 100 + '%';
                    flower.style.animationDelay = Math.random() * 3 + 's';
                    flower.style.animationDuration = (Math.random() * 4 + 6) + 's';
                    
                    flowersContainer.appendChild(flower);
                    
                    setTimeout(() => {
                        if (flower.parentNode) {
                            flower.parentNode.removeChild(flower);
                        }
                    }, 10000);
                }, i * 150);
            }
            
            // Create floating hearts
            for (let i = 0; i < 20; i++) {
                setTimeout(() => {
                    const heart = document.createElement('div');
                    heart.className = 'heart ' + heartColors[Math.floor(Math.random() * heartColors.length)];
                    heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                    heart.style.left = Math.random() * 100 + '%';
                    heart.style.animationDelay = Math.random() * 3 + 's';
                    heart.style.animationDuration = (Math.random() * 4 + 6) + 's';
                    
                    flowersContainer.appendChild(heart);
                    
                    setTimeout(() => {
                        if (heart.parentNode) {
                            heart.parentNode.removeChild(heart);
                        }
                    }, 10000);
                }, i * 200);
            }
            
            // Create big hearts
            for (let i = 0; i < 8; i++) {
                setTimeout(() => {
                    const bigHeart = document.createElement('div');
                    bigHeart.className = 'heart ' + heartColors[Math.floor(Math.random() * heartColors.length)];
                    bigHeart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                    bigHeart.style.left = Math.random() * 100 + '%';
                    bigHeart.style.fontSize = (Math.random() * 30 + 40) + 'px'; // Big hearts 40-70px
                    bigHeart.style.animationDelay = Math.random() * 4 + 's';
                    bigHeart.style.animationDuration = (Math.random() * 5 + 8) + 's';
                    
                    flowersContainer.appendChild(bigHeart);
                    
                    setTimeout(() => {
                        if (bigHeart.parentNode) {
                            bigHeart.parentNode.removeChild(bigHeart);
                        }
                    }, 13000);
                }, i * 300);
            }
        }

        function createBackgroundFlowers() {
            const bgContainer = document.getElementById('bgFlowers');
            const flowers = ['🌸', '🌺', '🌼', '🌻', '🌷', '🌹', '💐'];
            const hearts = ['💖', '💕', '💗', '❤️', '💜'];
            
            // Background flowers
            for (let i = 0; i < 15; i++) {
                const flower = document.createElement('div');
                flower.className = 'bg-flower';
                flower.innerHTML = flowers[Math.floor(Math.random() * flowers.length)];
                flower.style.left = Math.random() * 100 + '%';
                flower.style.top = Math.random() * 100 + '%';
                flower.style.animationDelay = Math.random() * 5 + 's';
                
                bgContainer.appendChild(flower);
            }
            
            // Background hearts
            for (let i = 0; i < 10; i++) {
                const heart = document.createElement('div');
                heart.className = 'bg-heart';
                heart.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                heart.style.left = Math.random() * 100 + '%';
                heart.style.top = Math.random() * 100 + '%';
                heart.style.animationDelay = Math.random() * 5 + 's';
                
                bgContainer.appendChild(heart);
            }
        }

        // Create background flowers when page loads
        window.addEventListener('load', createBackgroundFlowers);
    </script>
</body>
</html>
