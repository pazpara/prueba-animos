<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta para mi pareja</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to right, #ff9a9e, #fad0c4, #ffd1ff);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }
        .container {
            position: relative;
            text-align: center;
        }
        #card {
            display: none;
            background-color: #fff;
            border: 2px solid #ff69b4;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
            padding: 30px;
            width: 400px;
            height: 300px;
            text-align: center;
            color: #ff69b4;
            position: relative;
            transform: translateY(-50%);
            opacity: 0;
            transition: transform 0.5s, opacity 0.5s;
        }
        #card.open {
            display: block;
            transform: translateY(0);
            opacity: 1;
        }
        .paper {
            background-color: #b3e5fc;
            border-radius: 5px;
            padding: 20px;
            margin-top: 20px;
            color: #0077c2;
        }
        #openCard {
            background-color: #ff69b4;
            border: none;
            border-radius: 5px;
            color: #fff;
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.3s;
            box-shadow: 0 4px 14px 0 rgba(255, 105, 180, 0.39);
        }
        #openCard:hover {
            background-color: #ff1493;
            transform: scale(1.1);
        }
        .hearts {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff69b4;
            border-radius: 50% 50% 0 0;
            transform: rotate(-45deg);
            animation: float 5s infinite;
        }
        .heart::before,
        .heart::after {
            content: "";
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: #ff69b4;
            border-radius: 50%;
        }
        .heart::before {
            top: -10px;
            left: 0;
        }
        .heart::after {
            top: 0;
            left: -10px;
        }
        @keyframes float {
            0% {
                transform: translateX(0) rotate(-45deg);
                opacity: 1;
            }
            100% {
                transform: translateX(-300px) translateY(-600px) rotate(-45deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <button id="openCard">Abrir Carta</button>
        <div id="card" class="card">
            <div class="paper">
                Hoy todo va a salir bien, y si no sale bien, le obligaremos al destino que saldrá bien.
            </div>
        </div>
        <div class="hearts">
            <div class="heart" style="left: 10%; animation-duration: 6s;"></div>
            <div class="heart" style="left: 30%; animation-duration: 4s; animation-delay: 2s;"></div>
            <div class="heart" style="left: 50%; animation-duration: 7s; animation-delay: 4s;"></div>
            <div class="heart" style="left: 70%; animation-duration: 5s; animation-delay: 1s;"></div>
            <div class="heart" style="left: 90%; animation-duration: 8s; animation-delay: 3s;"></div>
        </div>
    </div>

    <script>
        document.getElementById('openCard').addEventListener('click', function() {
            var card = document.getElementById('card');
            card.classList.toggle('open');
        });
    </script>
</body>
</html>
