# Stat-track
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AFL Stat Tracker</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      text-align: center;
      padding: 50px;
    }

    h1 {
      margin-bottom: 40px;
    }

    .button-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin-bottom: 40px;
    }

    .stat-button, .reset-button {
      background-color: #007bff;
      border: none;
      color: white;
      padding: 20px 40px;
      font-size: 18px;
      border-radius: 10px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .stat-button:hover, .reset-button:hover {
      background-color: #0056b3;
    }

    .count {
      display: block;
      margin-top: 10px;
      font-size: 22px;
      font-weight: bold;
    }

    .reset-button {
      background-color: #dc3545;
    }

    .reset-button:hover {
      background-color: #a71d2a;
    }
  </style>
</head>
<body>

  <h1>AFL Stat Tracker</h1>

  <div class="button-container">
    <button class="stat-button" onclick="increment('kicks')">
      Kicks<span class="count" id="kicks">0</span>
    </button>
    <button class="stat-button" onclick="increment('handballs')">
      Handballs<span class="count" id="handballs">0</span>
    </button>
    <button class="stat-button" onclick="increment('marks')">
      Marks<span class="count" id="marks">0</span>
    </button>
    <button class="stat-button" onclick="increment('goals')">
      Goals<span class="count" id="goals">0</span>
    </button>
    <button class="stat-button" onclick="increment('tackles')">
      Tackles<span class="count" id="tackles">0</span>
    </button>
  </div>

  <button class="reset-button" onclick="resetAll()">Reset All</button>

  <script>
    const counters = {
      kicks: 0,
      handballs: 0,
      marks: 0,
      goals: 0,
      tackles: 0
    };

    function increment(stat) {
      counters[stat]++;
      document.getElementById(stat).textContent = counters[stat];
    }

    function resetAll() {
      for (let stat in counters) {
        counters[stat] = 0;
        document.getElementById(stat).textContent = 0;
      }
    }
  </script>

</body>
</html>
