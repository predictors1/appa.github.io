<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>AI Signal</title>
<style>
    body {
        margin: 0;
        background: radial-gradient(circle at top, #1e293b, #020617);
        color: white;
        font-family: Arial, sans-serif;
        text-align: center;
        padding-top: 60px;
    }

    h1 {
        font-size: 32px;
    }

    .subtitle {
        opacity: 0.7;
        font-size: 15px;
    }

    .card {
        margin: 40px auto;
        padding: 30px;
        width: 300px;
        border-radius: 20px;
        background: rgba(255,255,255,0.05);
        backdrop-filter: blur(12px);
        box-shadow: 0 0 30px rgba(0,255,150,0.2);
    }

    .btn {
        padding: 18px 40px;
        font-size: 20px;
        border: none;
        border-radius: 12px;
        cursor: pointer;
        background: linear-gradient(45deg, #22c55e, #4ade80);
        color: white;
        margin-top: 20px;
        animation: pulse 2s infinite;
    }

    @keyframes pulse {
        0% { box-shadow: 0 0 0px rgba(34,197,94,0.7); }
        50% { box-shadow: 0 0 25px rgba(34,197,94,1); }
        100% { box-shadow: 0 0 0px rgba(34,197,94,0.7); }
    }

    .status {
        margin-top: 20px;
        font-size: 18px;
        opacity: 0.85;
    }

    .signal {
        margin-top: 30px;
        font-size: 34px;
        font-weight: bold;
    }

    .emoji {
        font-size: 50px;
        margin-top: 15px;
        animation: float 2s infinite ease-in-out;
    }

    @keyframes float {
        0% { transform: translateY(0px); }
        50% { transform: translateY(-10px); }
        100% { transform: translateY(0px); }
    }

    .history {
        margin-top: 25px;
        font-size: 14px;
        opacity: 0.6;
    }

    .users {
        margin-top: 10px;
        font-size: 14px;
        color: #4ade80;
    }

</style>
</head>
<body>

<h1>🎯 AI Betting Signal</h1>
<div class="subtitle">Real-time pattern analysis</div>
<div class="users">✔ 12,842 players online</div>

<div class="card">

    <button class="btn" onclick="generateSignal()">GET SIGNAL</button>

    <div class="status" id="status"></div>
    <div class="emoji" id="emoji">🎯</div>
    <div class="signal" id="signal">--</div>
    <div class="history" id="history"></div>

</div>

<script>
let history = [];

function generateSignal() {
    document.getElementById("signal").innerText = "--";
    document.getElementById("status").innerText = "Analyzing betting activity...";
    document.getElementById("emoji").innerText = "🔍";

    setTimeout(() => {
        document.getElementById("status").innerText = "Checking recent rounds...";
        document.getElementById("emoji").innerText = "📊";
    }, 800);

    setTimeout(() => {
        document.getElementById("status").innerText = "Calculating optimal entry...";
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
        history = history.slice(0, 5);

        document.getElementById("history").innerText =
            "Recent signals: " + history.join(" • ");

    }, 2000);
}
</script>

</body>
</html>
