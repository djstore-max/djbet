<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jogo do Tigrinho</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #222;
            color: white;
        }
        .slot-machine {
            font-size: 50px;
            margin: 20px;
        }
        .button {
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            margin: 10px;
        }
        .balance {
            font-size: 20px;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <h1>🎰 Jogo do Tigrinho 🎰</h1>
    <div class="slot-machine">
        <span id="slot1">❓</span>
        <span id="slot2">❓</span>
        <span id="slot3">❓</span>
    </div>
    
    <p class="balance">Saldo: <span id="balance">100</span> moedas</p>

    <label for="bet">Aposta:</label>
    <input type="number" id="bet" value="10" min="1">
    
    <button class="button" onclick="spin()">Girar</button>
    
    <p id="message"></p>

    <script>
        let balance = 100;
        const symbols = ["🍒", "🔔", "💎", "🍀", "🎰", "⭐"];

        function spin() {
            let bet = parseInt(document.getElementById("bet").value);
            if (bet > balance || bet <= 0) {
                document.getElementById("message").innerText = "Aposta inválida!";
                return;
            }

            balance -= bet;

            let slot1 = Math.floor(Math.random() * symbols.length);
            let slot2 = Math.floor(Math.random() * symbols.length);
            let slot3 = Math.floor(Math.random() * symbols.length);

            document.getElementById("slot1").innerText = symbols[slot1];
            document.getElementById("slot2").innerText = symbols[slot2];
            document.getElementById("slot3").innerText = symbols[slot3];

            let winnings = 0;

            if (slot1 === slot2 && sl
