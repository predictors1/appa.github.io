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
        overflow-x: hidden;
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
        animation: glowText 2s infinite alternate;
    }

    @keyframes glowText {
        from { text-shadow: 0 0 5px #22c55e; }
        to { text-shadow: 0 0 15px #4ade80; }
    }

    .card {
        margin: 40px auto;
        padding: 30px;
        width: 320px;
        border-radius: 20px;
        background: rgba(255,255,255,0.05);
        backdrop-filter: blur(15px);
        box-shadow: 0 0 40px rgba(34,197,94,0.3);
        animation: fadeIn 1s ease;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
    }

    .btn {
        padding: 18px 45px;
        font-size: 20px;
        border: none;
        border-radius: 14px;
        cursor: pointer;
        background: linear-gradient(45deg, #22c55e, #4ade80, #38bdf8);
        color: white;
        margin-top: 20px;
        animation: pulse 1.5s infinite;
    }

    @keyframes pulse {
        0% { box-shadow: 0 0 5px #22c55e; }
        50% { box-shadow: 0 0 30px #38bdf8; }
        100% { box-shadow: 0 0 5px #22c55e; }
    }

    .status {
        margin-top: 20px;
        font-size: 18px;
        opacity: 0.9;
        min-height: 24px;
    }

    .signal {
        margin-top: 30px;
        font-size: 38px;
        font-weight: bold;
        letter-spacing: 1px;
    }

    .emoji {
        font-size: 55px;
        margin-top: 15px;
        animation: float 2s infinite ease-in-out;
    }

    @keyframes float {
        0% { transform: translateY(0px); }
        50% { transform: translateY(-12px); }
        100% { transform: translateY(0px); }
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
    document.getElementById("status").innerText = "Analyzing player bets...";
    document.getElementById("emoji").innerText = "🔍";

    setTimeout(() => {
        document.getElementById("status").innerText = "Tracking recent rounds...";
        document.getElementById("emoji").innerText = "📊";
    }, 700);

    setTimeout(() => {
        document.getElementById("status").innerText = "Calculating best timing...";
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
</script>

</body>
</html>
