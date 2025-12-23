# gift
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Anniversary</title>
    <style>
        body {
            background-color: #ffffff; /* Light pink background */
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            position: relative;
        }

        .container {
            background-color: pink; /* Semi-transparent white box */
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            text-align: center;
            z-index: 10;
            max-width: 600px;
            color: #333;
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }

        h1 {
            font-size: 3em;
            margin-bottom: 20px;
            color: #fa5db1; /* Deep pink for title */
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        p {
            font-size: 1.2em;
            line-height: 1.6;
            margin: 0;
        }

        /* Responsive for phones */
        @media (max-width: 768px) {
            .container {
                padding: 20px;
                margin: 20px;
            }
            h1 {
                font-size: 2em;
            }
            p {
                font-size: 1em;
            }
        }

        .fireworks {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .heart {
            position: absolute;
            font-size: 2em;
            animation: burst 4s linear infinite;
            opacity: 0.8;
        }

        @keyframes burst {
            0% { transform: translateY(100vh) rotate(0deg) scale(0.5); opacity: 1; }
            50% { transform: translateY(50vh) rotate(180deg) scale(1.2); opacity: 0.9; }
            100% { transform: translateY(-100px) rotate(360deg) scale(0.8); opacity: 0; }
        }

        .sparkle {
            position: absolute;
            font-size: 1.5em;
            animation: sparkleFloat 3s linear infinite;
            color: #FFD700; /* Gold for sparkles */
        }

        @keyframes sparkleFloat {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-100px) rotate(360deg); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Happy Anniversary</h1>
        <p>Here's to many more years of love, laughter, and unforgettable moments together. You make every day special, and I cherish every second with you. Wishing you endless happiness and love!</p>
    </div>
    <div class="fireworks"></div>
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const fireworks = document.querySelector('.fireworks');
            const hearts = ['🎊', '💋', '💕', '💗', '😍', '💘', '🫀'];
            const sparkles = ['✨', '🫶', '🎉'];

            function createParticle(type) {
                const particle = document.createElement('div');
                particle.classList.add(type === 'heart' ? 'heart' : 'sparkle');
                particle.textContent = type === 'heart' ? hearts[Math.floor(Math.random() * hearts.length)] : sparkles[Math.floor(Math.random() * sparkles.length)];
                particle.style.left = Math.random() * 100 + 'vw';
                particle.style.animationDelay = Math.random() * 2 + 's';
                fireworks.appendChild(particle);

                setTimeout(() => {
                    particle.remove();
                }, 4000);
            }

            // Create more particles for an amazing effect
            setInterval(() => createParticle('heart'), 200); // Hearts every 0.2 seconds
            setInterval(() => createParticle('sparkle'), 300); // Sparkles every 0.3 seconds
        });
    </script>
</body>
</html>
