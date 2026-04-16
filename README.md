<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>The Midnight Archive | Mystery Escape Room</title>
  <style>
    :root {
      --bg: #000;
      --text: #fff;
      --accent: #0077c8;
      --border: #333;
      --panel: #111;
      --danger: #c91414;
    }

    body {
      font-family: 'Segoe UI', Arial, sans-serif;
      background-color: var(--bg);
      color: var(--text);
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      text-align: center;
      background-image: url('https://images.unsplash.com/photo-1543466835-158384736582?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80');
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
    }

    .container {
      max-width: 800px;
      padding: 40px;
      background: rgba(17, 17, 17, 0.9);
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
      border: 1px solid var(--accent);
      backdrop-filter: blur(8px);
    }

    h1 {
      color: var(--accent);
      font-size: 2.4em;
      margin-bottom: 10px;
      text-transform: uppercase;
      letter-spacing: 1px;
      text-shadow: 0 0 10px rgba(0, 119, 200, 0.4);
    }

    .subtitle {
      color: #aaa;
      font-size: 1.1em;
      margin-bottom: 30px;
      font-style: italic;
    }

    .timer {
      background: rgba(201, 20, 20, 0.2);
      border: 1px solid var(--danger);
      border-radius: 12px;
      padding: 15px;
      margin-bottom: 25px;
      font-size: 1.4em;
      font-weight: bold;
      color: var(--danger);
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
      position: relative;
      overflow: hidden;
    }

    .timer-bar {
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      background: linear-gradient(90deg, var(--danger), var(--accent));
      transform: scaleX(1);
      transform-origin: left;
      animation: timerFill 1500s linear forwards;
      z-index: 1;
    }

    @keyframes timerFill {
      0% { transform: scaleX(1); }
      100% { transform: scaleX(0); }
    }

    .timer-text {
      position: relative;
      z-index: 2;
    }

    .puzzle {
      background: rgba(30, 30, 30, 0.7);
      border-radius: 12px;
      padding: 25px;
      margin-bottom: 25px;
      border: 1px solid var(--border);
      transition: transform 0.3s ease;
    }

    .puzzle:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px rgba(0, 119, 200, 0.2);
    }

    .puzzle h2 {
      color: var(--accent);
      margin-top: 0;
      font-size: 1.5em;
    }

    .puzzle p {
      margin: 15px 0;
      line-height: 1.6;
      font-size: 1.05em;
    }

    .hint {
      font-size: 0.9em;
      color: #aaa;
      font-style: italic;
      margin-top: 10px;
    }

    .answer {
      margin-top: 15px;
      padding: 12px;
      background: rgba(0, 119, 200, 0.2);
      border: 1px solid var(--accent);
      border-radius: 8px;
      font-family: monospace;
      font-size: 1.1em;
      color: var(--accent);
      display: inline-block;
    }

    .final {
      margin-top: 30px;
      padding: 20px;
      background: rgba(201, 20, 20, 0.2);
      border: 1px solid var(--danger);
      border-radius: 12px;
      font-size: 1.2em;
      font-weight: bold;
    }

    .final span {
      color: var(--danger);
    }

    .final.ended {
      background: rgba(201, 20, 20, 0.4);
      border-color: #ff0000;
    }

    .final.ended h3 {
      color: #ff0000;
      font-size: 1.4em;
    }

    .submit-btn {
      display: inline-block;
      margin-top: 20px;
      padding: 14px 30px;
      background: var(--accent);
      color: white;
      font-size: 1.2em;
      font-weight: bold;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background 0.3s ease;
      text-decoration: none;
      box-shadow: 0 4px 10px rgba(0, 119, 200, 0.3);
    }

    .submit-btn:hover {
      background: #005a99;
      transform: translateY(-2px);
    }

    @media (max-width: 600px) {
      .container {
        padding: 20px;
      }
      h1 {
        font-size: 2em;
      }
      .timer {
        font-size: 1.2em;
      }
      .submit-btn {
        padding: 12px 24px;
        font-size: 1em;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>The Midnight Archive</h1>
    <p class="subtitle">Solve the puzzles. Find the key. Escape before dawn.</p>

    <!-- Timer -->
    <div class="timer">
      <div class="timer-bar"></div>
      <div class="timer-text">25:00</div>
    </div>

    <div class="puzzle">
      <h2>Puzzle 1: The Torn Note</h2>
      <p>You find a torn piece of paper: “The key is hidden in the 12th word of the third paragraph. The paragraph begins: ‘The moon was high, and the clock struck...’”</p>
      <p><strong>Full text:</strong></p>
      <p style="font-style: italic; margin: 10px 0; font-size: 0.95em;">
        “The moon was high, and the clock struck midnight. A shadow moved across the floor. No one was there. But the door had been opened. The key was not in the lock. It was in the silence.”
      </p>
      <p class="hint">Count the words in the third paragraph.</p>
      <div class="answer">silence</div>
    </div>

    <div class="puzzle">
      <h2>Puzzle 2: The Clock Puzzle</h2>
      <p>A clock shows 3:45. The note says: “The time is not what it seems. Add the hour and minute. Then multiply by 2.”</p>
      <p class="hint">Think: 3 + 45 = ? Then × 2.</p>
      <div class="answer">96</div>
    </div>

    <div class="puzzle">
      <h2>Puzzle 3: The Hidden Word</h2>
      <p>A grid of letters:</p>
      <pre style="background: #111; padding: 15px; border-radius: 8px; font-family: monospace; font-size: 1.1em; text-align: left; margin: 15px auto; display: inline-block;">
S E C R E T
C L U E S
E N C R Y P T
R E A D
T I M E
      </pre>
      <p class="hint">Find the word “TIME” — it’s in a straight line.</p>
      <div class="answer">TIME</div>
    </div>

    <div class="puzzle">
      <h2>Puzzle 4: The Letter Shift</h2>
      <p>A message: “Khoor Zruog”</p>
      <p class="hint">Each letter is shifted forward by 3 in the alphabet. Try shifting backward.</p>
      <div class="answer">Hello World</div>
    </div>

    <div class="puzzle">
      <h2>Puzzle 5: The Number Sequence</h2>
      <p>A sequence: 2, 4, 8, 16, ???</p>
      <p class="hint">Each number is double the previous.</p>
      <div class="answer">32</div>
    </div>

    <div class="final" id="finalMessage">
      <p>Submit your answers to the <span>Clue Coordinator</span>. The final code is:</p>
      <p style="font-size: 1.3em; margin: 10px 0;">
        <strong>silence-96-TIME-Hello World-32</strong>
      </p>
      <p>Enter it to unlock the archive.</p>
    </div>

    <!-- Submit Button -->
    <a href="https://forms.office.com/r/YourFormID" target="_blank" class="submit-btn">
      📥 Submit Answers (Microsoft Forms)
    </a>
  </div>

  <script>
    // Timer settings (in seconds)
    const totalTime = 25 * 60; // 25 minutes
    let timeLeft = totalTime;

    const timerElement = document.querySelector('.timer-text');
    const timerBar = document.querySelector('.timer-bar');
    const finalMessage = document.getElementById('finalMessage');

    // Update timer display
    function updateTimer() {
      const minutes = Math.floor(timeLeft / 60);
      const seconds = timeLeft % 60;
      timerElement.textContent = `$${minutes.toString().padStart(2, '0')}:$${seconds.toString().padStart(2, '0')}`;

      // Update progress bar
      const progress = (1 - timeLeft / totalTime) * 100;
      timerBar.style.transform = `scaleX(${progress / 100})`;

      // End game
      if (timeLeft <= 0) {
        clearInterval(timerInterval);
        timerElement.textContent = "TIME'S UP!";
        timerBar.style.transform = 'scaleX(0)';
        finalMessage.classList.add('ended');
        finalMessage.innerHTML = `
          <h3>⏰ Time's up!</h3>
          <p>The archive has sealed. The mystery remains.</p>
          <p>Try again next time — or go solve the next one.</p>
        `;
      }

      timeLeft--;
    }

    // Start timer
    const timerInterval = setInterval(updateTimer, 1000);

    // Initialize
    updateTimer();
  </script>
</body>
</html>
