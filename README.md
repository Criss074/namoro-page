<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Você quer namorar comigo?</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f8f9fa;
            text-align: center;
            overflow: hidden;
        }

        .container {
            padding: 20px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            cursor: pointer;
            background-color: #ff6b6b;
            color: white;
            border-radius: 5px;
            margin: 10px;
        }

        .no-button {
            background-color: #dcdcdc;
        }

        .yes-button {
            background-color: #6ccf6e;
        }

        .heart {
            font-size: 50px;
            animation: heart 1s infinite alternate;
        }

        @keyframes heart {
            0% {
                transform: scale(1);
            }
            100% {
                transform: scale(1.2);
            }
        }

        .fireworks {
            position: absolute;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            display: none;
        }

        .firework {
            position: absolute;
            bottom: 0;
            width: 10px;
            height: 10px;
            background-color: #ff6b6b;
            border-radius: 50%;
            animation: fireworkAnimation 1.5s ease-out infinite;
        }

        @keyframes fireworkAnimation {
            0% {
                transform: translateY(0) scale(1);
                opacity: 1;
            }
            100% {
                transform: translateY(-200px) scale(1.5);
                opacity: 0;
            }
        }

        .message {
            font-size: 24px;
            color: #ff6b6b;
            margin-top: 20px;
        }

        .balloon {
            font-size: 80px;
            color: #ff6b6b;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Você quer namorar comigo?</h1>
    <button class="yes-button" id="yesButton" onclick="showLove()">Sim</button>
    <button class="no-button" id="noButton" onclick="moveButton()">Não</button>
</div>

<div id="fireworks" class="fireworks"></div>
<div id="message" class="message"></div>

<script>
    var clickCount = 0;

    // Função que mostra a mensagem de amor e animações
    function showLove() {
        clickCount++;

        if (clickCount >= 5) {
            // Mostra a mensagem fofa com o balão de coração
            document.getElementById('message').innerHTML = 'Você me faz mais feliz do que eu jamais imaginei! 💖';
            document.getElementById('message').style.color = '#6ccf6e';
            document.getElementById('message').innerHTML += '<br><span class="balloon">💘</span>';

            // Exibe os fogos de artifício
            document.getElementById('fireworks').style.display = 'block';
            generateFireworks();

            // Desativa o botão "Sim"
            document.getElementById('yesButton').disabled = true;
        }
    }

    // Função que gera os fogos de artifício
    function generateFireworks() {
        for (var i = 0; i < 20; i++) {
            var firework = document.createElement('div');
            firework.classList.add('firework');
            firework.style.left = Math.random() * 100 + '%';
            firework.style.animationDelay = Math.random() * 2 + 's';
            document.getElementById('fireworks').appendChild(firework);
        }
    }

    // Função que troca a posição do botão "Não"
    function moveButton() {
        var button = document.getElementById("noButton");
        var container = document.querySelector(".container");
        container.appendChild(button);  // Move o botão para o final do container
    }
</script>

</body>
</html>
