<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Ti 💜</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(135deg, #6a0dad, #8e44ad, #3498db);
            font-family: Arial, sans-serif;
            overflow: hidden;
        }
        .card {
            width: 300px;
            height: 200px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            text-align: center;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 20px;
            font-weight: bold;
            cursor: pointer;
            position: relative;
        }
        .hidden-message {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 80%;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .heart {
            position: absolute;
            color: red;
            font-size: 20px;
            animation: float 4s infinite ease-in-out;
        }
        @keyframes float {
            0% { transform: translateY(0); opacity: 1; }
            100% { transform: translateY(-150px); opacity: 0; }
        }
    </style>
</head>
<body>
    <audio id="bg-music" loop>
        <source src="audio/rewrite-the-stars.mp3" type="audio/mpeg">
    </audio>
    <div class="card" onclick="showMessage()">
        💜 Toca para abrir 💜
        <div class="hidden-message" id="message">
            "Eres mi estrella favorita en este universo infinito mi Jensi. Gracias por iluminar mi vida con tu sonrisa y el brillo de tus lindos ojos mi amorcito lindo. 💜✨"
        </div>
    </div>

    <script>
        function showMessage() {
            document.getElementById("message").style.display = "block";
            document.getElementById("bg-music").play();
            createHearts();
        }

        function createHearts() {
            for (let i = 0; i < 10; i++) {
                let heart = document.createElement("div");
                heart.classList.add("heart");
                heart.innerHTML = "❤️";
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.animationDuration = Math.random() * 2 + 3 + "s";
                document.body.appendChild(heart);
                setTimeout(() => heart.remove(), 4000);
            }
        }
    </script>
</body>
</html>
