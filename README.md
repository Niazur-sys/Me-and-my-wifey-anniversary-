# Me-and-my-wifey-anniversary- <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Anniversary</title>
    <link rel="stylesheet" href="style.css">
    <script defer src="script.js"></script>
</head>
<body>
    <audio id="bg-music" loop>
        <source src="music.mp3" type="audio/mpeg">
    </audio>
    
    <div id="click-to-start">
        <button onclick="startCelebration()">Click to Start</button>
    </div>

    <div id="fireworks-container"></div>

    <div id="main-content" class="hidden">
        <h1 id="anniversary-text">Happy Anniversary My love my wifey Mehnazuuuu💗</h1>
        <div id="message">
            <p id="typing-text"></p>
        </div>
        <div id="hearts-container"></div>
        <div id="falling-flowers"></div>
        <div id="animated-couple">
            <img src="couple.gif" alt="Couple Animation">
        </div>
    </div>
</body>
</html>body {
    background-color: black;
    color: white;
    text-align: center;
    font-family: 'Arial', sans-serif;
    overflow: hidden;
}

#click-to-start {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

button {
    padding: 15px 30px;
    font-size: 20px;
    cursor: pointer;
    background: pink;
    border: none;
    border-radius: 10px;
}

.hidden {
    display: none;
}

#anniversary-text {
    font-size: 3em;
    margin-top: 50px;
    animation: fadeIn 3s ease-in-out;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

#message {
    font-size: 1.5em;
    width: 80%;
    margin: 20px auto;
}

#hearts-container, #falling-flowers {
    position: absolute;
    width: 100%;
    height: 100%;
    pointer-events: none;
}

@keyframes floatHeart {
    0% { transform: translateY(0); }
    100% { transform: translateY(-100vh); }
}

.heart {
    position: absolute;
    color: red;
    font-size: 2em;
    animation: floatHeart 5s infinite linear;
}

@keyframes fallFlower {
    0% { transform: translateY(0); }
    100% { transform: translateY(100vh); }
}

.flower {
    position: absolute;
    color: pink;
    font-size: 1.5em;
    animation: fallFlower 4s infinite linear;
}

#animated-couple img {
    width: 200px;
    margin-top: 20px;
}function startCelebration() {
    document.getElementById("click-to-start").style.display = "none";
    document.getElementById("main-content").classList.remove("hidden");
    
    // ব্যাকগ্রাউন্ড মিউজিক চালু করা
    document.getElementById("bg-music").play();

    // ফায়ারওয়ার্ক শুরু করা
    startFireworks();

    // টাইপিং এফেক্ট চালু করা
    typeMessage();

    // হার্ট ও ফুল অ্যানিমেশন চালু করা
    createFloatingHearts();
    createFallingFlowers();
}

// টাইপিং এফেক্ট
let message = "Happy anniversary jannnn! You are my whole lifeline and you are my best wifey. I love you bushuuu shuna amrrr. It's been a year and I am still crushing on you. I love you more than anything else and we will end up marrying and there is no breakup. I love you and I will make every day special for you, in sha Allah. Don't leave me. I love you. Ami tumake balobashiiii💗";
let index = 0;

function typeMessage() {
    if (index < message.length) {
        document.getElementById("typing-text").innerHTML += message.charAt(index);
        index++;
        setTimeout(typeMessage, 50);
    }
}

// ফায়ারওয়ার্ক
function startFireworks() {
    let container = document.getElementById("fireworks-container");
    for (let i = 0; i < 10; i++) {
        let firework = document.createElement("div");
        firework.classList.add("firework");
        firework.style.left = Math.random() * 100 + "vw";
        container.appendChild(firework);
        setTimeout(() => firework.remove(), 2000);
    }
}

// হার্ট অ্যানিমেশন
function createFloatingHearts() {
    setInterval(() => {
        let heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "💖";
        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = Math.random() * 3 + 3 + "s";
        document.getElementById("hearts-container").appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
    }, 500);
}

// ফুল পড়ার অ্যানিমেশন
function createFallingFlowers() {
    setInterval(() => {
        let flower = document.createElement("div");
        flower.classList.add("flower");
        flower.innerHTML = "🌸";
        flower.style.left = Math.random() * 100 + "vw";
        flower.style.animationDuration = Math.random() * 3 + 3 + "s";
        document.getElementById("falling-flowers").appendChild(flower);
        setTimeout(() => flower.remove(), 5000);
    }, 800);
}
