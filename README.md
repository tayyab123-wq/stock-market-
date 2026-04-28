<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>PSX Stock Analyzer - Smart Investing Guide</title>

  <!-- Lexend font -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Lexend:wght@300;400;500;600;700&display=swap"
    rel="stylesheet"
  />

  <!-- Chart.js -->
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --bg: #0f0f23;
      --bg-light: #1a1a3e;
      --dark: #2d1b69;
      --primary: #00ff88;
      --secondary: #00bfff;
      --orange: #ffaa00;
      --red: #ff4444;
    }

    body {
      font-family: "Lexend", sans-serif;
      background: linear-gradient(135deg, var(--bg) 0%, var(--bg-light) 50%, var(--dark) 100%);
      color: #fff;
      min-height: 100vh;
      overflow-x: hidden;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }

    h1 {
      text-align: center;
      font-size: 2.5rem;
      font-weight: 700;
      margin-bottom: 20px;
      background: linear-gradient(45deg, var(--primary), var(--secondary));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: glow 2s ease-in-out infinite alternate;
    }

    @keyframes glow {
      0% {
        text-shadow: 0 0 20px var(--primary);
      }
      100% {
        text-shadow: 0 0 40px var(--secondary);
      }
    }

    /* Circle animations */
    .profit-circle {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      margin: 20px auto;
      position: relative;
      animation: spin 2s linear infinite, pulse 1.5s ease-in-out infinite alternate;
    }

    .profit-chart--up {
      background: conic-gradient(
        var(--primary) 0% 75%,
        var(--red) 75% 100%
      );
    }

    .profit-chart--growth {
      background: conic-gradient(
        var(--orange) 0% 90%,
        var(--red) 90% 100%
      );
    }

    .profit-chart--mixed {
      background: conic-gradient(
        var(--secondary) 0% 60%,
        var(--orange) 60% 100%
      );
    }

    .profit-circle::after {
      content: "Profit ↑";
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-weight: 600;
      font-size: 1rem;
      color: #000;
      text-shadow: 0 0 5px rgba(255, 255, 255, 0.8);
    }

    @keyframes spin {
      0% {
        transform: rotate(0deg);
      }
      100% {
        transform: rotate(360deg);
      }
    }

    @keyframes pulse {
      0% {
        box-shadow: 0 0 0 0 rgba(0, 255, 136, 0.7);
      }
      70% {
        box-shadow: 0 0 0 20px rgba(0, 255, 136, 0);
      }
      100% {
        box-shadow: 0 0 0 0 rgba(0, 255, 136, 0);
      }
    }

    /* Sections */
    .section {
      background: rgba(255, 255, 255, 0.05);
      backdrop-filter: blur(10px);
      border-radius: 20px;
      padding: 30px;
      margin: 30px 0;
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.3s ease;
    }

    .section:hover {
      transform: translateY(-10px);
      box-shadow: 0 20px 40px rgba(0, 255, 136, 0.3);
    }

    .glow-hover {
      transition: all 0.3s;
    }

    .glow-hover:hover {
      filter: drop-shadow(0 0 10px var(--primary));
    }

    h2 {
      font-size: 1.8rem;
      margin-bottom: 20px;
      color: var(--primary);
    }

    h3 {
      font-size: 1.4rem;
      margin: 20px 0 10px;
      color: var(--secondary);
    }

    p {
      margin: 10px 0;
      line-height: 1.6;
    }

    ul {
      list-style: none;
      padding-left: 0;
    }

    li {
      padding: 10px;
      margin: 10px 0;
      background: rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      transition: all 0.3s;
    }

    li:hover {
      background: rgba(0, 255, 136, 0.2);
      transform: scale(1.02);
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin: 20px 0;
    }

    th,
    td {
      padding: 12px;
      text-align: left;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }

    th {
      background: rgba(0, 255, 136, 0.2);
      color: var(--primary);
    }

    /* Charts */
    .chart-container {
      position: relative;
      height: 300px;
      margin: 20px 0;
    }

    canvas {
      border-radius: 10px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    }

    /* Responsive */
    @media (max-width: 768px) {
      h1 {
        font-size: 2rem;
      }

      .container {
        padding: 10px;
      }
    }
  </style>
</head>

<body>
  <div class="container">
    <h1>🔥 PSX Stock Analyzer & Checklist</h1>

    <!-- Intro section -->
    <div class="section glow-hover">
      <h2>Good question—this is exactly the mindset you need before investing 👍</h2>
      <p>
        Most beginners just “sun kar buy” karte hain, aur loss hota hai. Tum
        smart ho ke pehle samajhna chahte ho.
      </p>
      <div class="profit-circle profit-chart--up"></div>
    </div>

    <!-- UBL Section -->
    <div class="section">
      <h2>🏦 UBL (United Bank Limited) Analysis</h2>
      <p>
        UBL ko lenay se pehle in cheezon ko check karo for long‑term,
        dividend‑oriented investing.
      </p>
      <ul>
        <li>✅ Profit growing consistently 📈</li>
        <li>✅ EPS strong and stable</li>
        <li>✅ P/E ratio reasonable (not too high vs peers)</li>
        <li>✅ Regular dividend paying bank 💸</li>
        <li>✅ Low NPLs (non‑performing loans)</li>
        <li>✅ Deposits growing year over year</li>
        <li>✅ Interest‑rate‑friendly economy (higher rates → more bank profit)</li>
      </ul>
      <div class="chart-container">
        <canvas id="ublChart"></canvas>
      </div>
    </div>

    <!-- Engro Section -->
    <div class="section">
      <h2>🏭 Engro Corporation Analysis</h2>
      <p>
        Engro ek diversified group hai (fertilizer, energy, petrochemicals, food)
        jahan profit growth + dividend dono important hain.
      </p>
      <ul>
        <li>✅ Profit stable ya gradually growing</li>
        <li>✅ Fertilizer demand strong (agriculture season)</li>
        <li>✅ Gas price stable ya low (key cost factor)</li>
        <li>✅ Govt policies supportive (subsidies, allocations)</li>
        <li>✅ Strong dividend history 💸</li>
        <li>✅ Market position strong in core sectors</li>
        <li>✅ Future projects in energy/food/petro → growth potential</li>
      </ul>
      <div class="chart-container">
        <canvas id="engroChart"></canvas>
      </div>
    </div>

    <!-- Sazgar Case Study -->
    <div class="section">
      <h2>🚀 Sazgar Engineering Works – Case Study</h2>
      <p>
        Pehle rickshaw bana kar normal business tha, price ~20 Rs. Jab Haval car
        launch hui aur sales boom hui, market ne future profit dekha aur price
        20 Rs se 2000+ Rs tak chala gaya. Iska lesson hai:
      </p>
      <ul>
        <li>✅ Future growth visible ho (new product, expansion)</li>
        <li>✅ Demand strong ho (salaam sale, exports)</li>
        <li>✅ Company capacity expand kar rahi ho</li>
        <li>✅ News & announcements supportive (deals, partnerships)</li>
        <li>⚠️ Lekin price pehle hi bohat zyada na ho (late entry = risk)</li>
      </ul>
      <p>
        Smart investor tab hota hai jab tum project early stage me identify kar lo,
        not jab price 2000 cross ho chuka ho.
      </p>
      <div class="profit-circle profit-chart--growth"></div>
    </div>

    <!-- Stock Checklist (10/10) -->
    <div class="section">
      <h2>🧾 PSX Stock Checklist (10/10 System)</h2>
      <p>
        Har company pe ye 10 cheezen 0 ya 1 score de kar total nikalo:
      </p>
      <table>
        <thead>
          <tr>
            <th>Point</th>
            <th>Score logic</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>1. Profit Growth</td>
            <td>✔️ Last 3–5 years me profit upar ja raha = 1 / else 0</td>
          </tr>
          <tr>
            <td>2. EPS Strong</td>
            <td>✔️ Earnings per share stable ya growing = 1 / else 0</td>
          </tr>
          <tr>
            <td>3. Dividend</td>
            <td>✔️ Consistent dividend, no cuts = 1 / else 0</td>
          </tr>
          <tr>
            <td>4. Debt Control</td>
            <td>✔️ Company pe zyada loan nahi = 1 / else 0</td>
          </tr>
          <tr>
            <td>5. Market Position</td>
            <td>✔️ Industry leader ya strong player = 1 / else 0</td>
          </tr>
          <tr>
            <td>6. Future Growth</td>
            <td>✔️ New projects, expansion, demand = 1 / else 0</td>
          </tr>
          <tr>
            <td>7. Reasonable Price</td>
            <td>✔️ Overvalued nahi, P/E vs sector = 1 / else 0</td>
          </tr>
          <tr>
            <td>8. Sector Strong</td>
            <td>✔️ Sector overall grow kar raha hai = 1 / else 0</td>
          </tr>
          <tr>
            <td>9. Positive News</td>
            <td>✔️ Company & economy level positive = 1 / else 0</td>
          </tr>
          <tr>
            <td>10. Chart Trend</td>
            <td>✔️ Price stable ya uptrend me, not falling knife = 1 / else 0</td>
          </tr>
        </tbody>
      </table>
      <h3>Score Interpretation</h3>
      <ul>
        <li>8–10 = 🔥 Strong Buy (long‑term, with good entry price)</li>
        <li>6–7 = 👍 Okay (but be careful, wait for dip)</li>
        <li>4–5 = ⚠️ Risky (only if you accept volatility)</li>
        <li>0–3 = ❌ Avoid (for now, or wait for improvement)</li>
      </ul>
    </div>

    <!-- Recommended PSX Shortlist -->
    <div class="section">
      <h2>🚀 Best PSX Stocks Shortlist (2026 Concept)</h2>
      <p>
        Ye stocks “safe + dividend + growth” mix ke liye pro‑level idea hai; entry
        price aur risk level tumhare strategy par depend karega.
      </p>
      <ul>
        <li>
          🏦 <strong>UBL, Meezan Bank, MCB</strong> – Stable banks, profit growth,
          regular dividends
        </li>
        <li>
          🏭 <strong>Engro, Fauji Fertilizer</strong> – Agriculture demand strong,
          dividend engine
        </li>
        <li>
          ⚡ <strong>HUBCO</strong> – Power company, regular income + dividend
        </li>
        <li>
          🛢️ <strong>OGDC, PPL</strong> – Oil & gas, energy demand high
        </li>
        <li>
          🚗 <strong>Sazgar Engineering</strong> – High‑risk high‑reward growth
          story (future projects)
        </li>
      </ul>
      <p>
        Agar tum beginner ho to: 50% safe (banks, fertilizer), 30% dividend heavy
        (power, oil), 20% growth (Sazgar type) keep karo.
      </p>
      <div class="profit-circle profit-chart--mixed"></div>
    </div>
  </div>

  <script>
    // Build UBL profit/time chart
    const ublChartCtx = document.getElementById("ublChart");
    new Chart(ublChartCtx, {
      type: "line",
      data: {
        labels: ["2023", "2024", "2025", "2026"],
        datasets: [
          {
            label: "UBL Profit (PKR mn)",
            data: [100, 120, 150, 180],
            borderColor: "#00ff88",
            backgroundColor: "rgba(0,255,136,0.1)",
            tension: 0.4,
            fill: true,
          },
        ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          y: {
            beginAtZero: true,
          },
        },
      },
    });

    // Build Engro revenue by segment chart
    const engroChartCtx = document.getElementById("engroChart");
    new Chart(engroChartCtx, {
      type: "bar",
      data: {
        labels: ["Fertilizer", "Energy", "Petrochemicals", "Food"],
        datasets: [
          {
            label: "Engro Revenue (PKR mn)",
            data: [40, 25, 20, 15],
            backgroundColor: [
              "#00ff88",
              "#00bfff",
              "#ffaa00",
              "#ff6666",
            ],
          },
        ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          y: {
            beginAtZero: true,
          },
        },
      },
    });
  </script>
</body>
</html>
