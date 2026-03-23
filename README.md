<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>AI Betting Signal</title>

<style>
body {
    margin: 0;
    background: linear-gradient(135deg, #020617, #0f172a, #020617);
    color: white;
    font-family: Arial, sans-serif;
    text-align: center;
    padding-top: 60px;
}

h1 {
    font-size: 34px;
    background: linear-gradient(45deg, #22c55e, #38bdf8);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.subtitle {
    opacity: 0.8;
    font-size: 15px;
}

.users {
    margin-top: 8px;
    font-size: 14px;
    color: #4ade80;
}

.card {
    margin: 40px auto;
    padding: 30px;
    width: 320px;
    border-radius: 20px;
    background: rgba(255,255,255,0.05);
    backdrop-filter: blur(15px);
}

.btn {
    padding: 18px 45px;
    font-size: 20px;
    border: none;
    border-radius: 14px;
    cursor: pointer;
    background: linear-gradient(45deg, #22c55e, #4ade80, #38bdf8);
    color: white;
}

.btn:disabled {
    opacity: 0.6;
    cursor: not-allowed;
}

.status {
    margin-top: 20px;
    font-size: 18px;
}

.signal {
    margin-top: 30px;
    font-size: 38px;
    font-weight: bold;
}

.emoji {
    font-size: 55px;
    margin-top: 15px;
}

.history {
    margin-top: 25px;
    font-size: 14px;
    opacity: 0.65;
}
</style>
</head>

<body>

<h1>🎯 AI Betting Signal</h1>
<div class="subtitle">Smart round analysis system</div>
<div class="users">✔ 13,204 players online</div>

<div class="card">
    <button class="btn" id="btn" onclick="generateSignal()">GET SIGNAL</button>

    <div class="status" id="status"></div>
    <div class="emoji" id="emoji">🎯</div>
    <div class="signal" id="signal">--</div>
    <div class="history" id="history"></div>
</div>

<script>
let history = [];
let cooldown = false;
let timeLeft = 60;
let timer;

function generateSignal() {
    if (cooldown) return;

    cooldown = true;
    timeLeft = 60;

    const btn = document.getElementById("btn");
    btn.disabled = true;

    startTimer();

    document.getElementById("signal").innerText = "--";
    document.getElementById("status").innerText = "Analyzing...";
    document.getElementById("emoji").innerText = "🔍";

    setTimeout(() => {
        document.getElementById("status").innerText = "Tracking...";
        document.getElementById("emoji").innerText = "📊";
    }, 700);

    setTimeout(() => {
        document.getElementById("status").innerText = "Calculating...";
        document.getElementById("emoji").innerText = "🤖";
    }, 1400);

    setTimeout(() => {
        let multiplier = (Math.random() * 5 + 1).toFixed(2);

        let signalText;
        let emoji;

        if (multiplier < 2) {
            signalText = "LOW " + multiplier + "x";
            emoji = "⚠️";
        } else if (multiplier < 3.5) {
            signalText = "MEDIUM " + multiplier + "x";
            emoji = "🔥";
        } else {
            signalText = "HIGH " + multiplier + "x";
            emoji = "🚀";
        }

        document.getElementById("status").innerText = "Signal ready";
        document.getElementById("signal").innerText = signalText;
        document.getElementById("emoji").innerText = emoji;

        history.unshift(multiplier + "x");
        history = history.slice(0, 6);

        document.getElementById("history").innerText =
            "Recent signals: " + history.join(" • ");

    }, 2000);
}

function startTimer() {
    const btn = document.getElementById("btn");

    timer = setInterval(() => {
        timeLeft--;
        btn.innerText = "WAIT " + timeLeft + "s";

        if (timeLeft <= 0) {
            clearInterval(timer);
            cooldown = false;
            btn.disabled = false;
            btn.innerText = "GET SIGNAL";
        }
    }, 1000);
}
</script>

</body>
</html>
