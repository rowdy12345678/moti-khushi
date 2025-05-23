<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Moti Khushi - A Joyful Experience</title>
    <style>
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            text-align: center;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            overflow: hidden;
            margin: 0;
        }
        h1 {
            font-size: 3.5em;
            color: #fff;
            text-shadow: 2px 2px 10px rgba(0,0,0,0.3);
            animation: bounce 1.5s infinite alternate;
        }
        p {
            font-size: 1.8em;
            color: white;
        }
        .balloon {
            width: 80px;
            height: 100px;
            background: red;
            border-radius: 50% 50% 40% 40%;
            position: absolute;
            bottom: -120px;
            animation: floatUp 6s linear infinite;
        }
        .emoji {
            font-size: 3rem;
            position: absolute;
            animation: floatEmoji 5s linear infinite;
        }
        @keyframes floatUp {
            0% { bottom: -120px; opacity: 0; }
            50% { opacity: 1; }
            100% { bottom: 100vh; opacity: 0; }
        }
        @keyframes floatEmoji {
            0% { transform: translateY(0px) rotate(0deg); }
            100% { transform: translateY(-150vh) rotate(360deg); }
        }
        @keyframes bounce {
            from { transform: translateY(0px); }
            to { transform: translateY(-15px); }
        }
        .button {
            background: #ff4081;
            border: none;
            padding: 15px 30px;
            color: white;
            font-size: 1.5em;
            cursor: pointer;
            border-radius: 10px;
            transition: 0.3s;
        }
        .button:hover {
            background: #e60073;
        }
    </style>
</head>
<body>
    <h1>Moti Khushi - The World of Happiness 🎉</h1>
    <p>Click the button for some extra happiness!</p>
    <button class="button" onclick="addEmoji()">Spread Happiness 😊</button>
    <audio id="happyMusic" src="https://www.bensound.com/bensound-music/bensound-happy.mp3" loop></audio>
    <script>
        function createBalloon() {
            const balloon = document.createElement("div");
            balloon.classList.add("balloon");
            balloon.style.left = Math.random() * 100 + "vw";
            balloon.style.background = `hsl(${Math.random() * 360}, 100%, 70%)`;
            document.body.appendChild(balloon);
            setTimeout(() => { balloon.remove(); }, 6000);
        }
        setInterval(createBalloon, 800);

        function addEmoji() {
            const emoji = document.createElement("div");
            emoji.classList.add("emoji");
            emoji.innerText = ['😂', '😍', '🎈', '🎉', '💖', '🌈'][Math.floor(Math.random() * 6)];
            emoji.style.left = Math.random() * 100 + "vw";
            emoji.style.top = "90vh";
            document.body.appendChild(emoji);
            setTimeout(() => { emoji.remove(); }, 5000);
        }

        document.body.addEventListener("click", function() {
            document.getElementById("happyMusic").play();
        });
    </script>
</body>
</html>
