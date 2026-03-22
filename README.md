# education-ai
"Education AI chatbot for homework help"
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>AI Education Platform</title>
<style>
  :root {
    --blue: #e6f3ff;
    --green: #e8f7f1;
    --accent: #4aa3a1;
    --text: #1f2937;
    --muted: #6b7280;
    --card: #ffffff;
  }

  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    color: var(--text);
    background: linear-gradient(180deg, var(--blue), var(--green));
  }

  h1, h2, h3 {
    margin: 0 0 0.5em;
    line-height: 1.2;
  }

  p {
    margin: 0 0 1em;
    color: var(--muted);
  }

  section {
    padding: 3rem 1.25rem;
  }

  .container {
    max-width: 1100px;
    margin: 0 auto;
  }

  .hero {
    text-align: center;
    padding-top: 4rem;
  }

  .hero h1 {
    font-size: clamp(2rem, 5vw, 3rem);
  }

  .hero p {
    font-size: 1.1rem;
  }

  .cta {
    display: inline-block;
    margin-top: 1.5rem;
    padding: 0.75rem 1.5rem;
    background: var(--accent);
    color: #fff;
    border-radius: 999px;
    text-decoration: none;
    font-weight: 600;
  }

  .grid {
    display: grid;
    gap: 1.25rem;
  }

  @media (min-width: 768px) {
    .grid-3 {
      grid-template-columns: repeat(3, 1fr);
    }
    .grid-2 {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  .card {
    background: var(--card);
    border-radius: 16px;
    padding: 1.25rem;
    box-shadow: 0 10px 25px rgba(0,0,0,0.05);
  }

  .feature-icon {
    font-size: 2rem;
  }

  /* Study Plan Builder */
  .builder input, .builder select {
    width: 100%;
    padding: 0.6rem;
    margin-bottom: 0.75rem;
    border-radius: 8px;
    border: 1px solid #d1d5db;
    font-size: 0.95rem;
  }

  .builder button {
    width: 100%;
    padding: 0.7rem;
    border-radius: 8px;
    border: none;
    background: var(--accent);
    color: #fff;
    font-weight: 600;
    cursor: pointer;
  }

  .plan-output {
    margin-top: 1rem;
    font-size: 0.95rem;
  }

  /* Chatbot */
  .chatbox {
    display: flex;
    flex-direction: column;
    height: 300px;
  }

  .messages {
    flex: 1;
    overflow-y: auto;
    font-size: 0.9rem;
    margin-bottom: 0.5rem;
  }

  .msg {
    margin-bottom: 0.5rem;
  }

  .bot {
    color: var(--accent);
  }

  .user {
    text-align: right;
    font-weight: 600;
  }

  .chatbox input {
    padding: 0.6rem;
    border-radius: 8px;
    border: 1px solid #d1d5db;
  }

  /* Pricing */
  .price {
    font-size: 2rem;
    font-weight: 700;
    margin: 0.5rem 0;
  }

  footer {
    text-align: center;
    padding: 2rem 1rem;
    font-size: 0.85rem;
    color: var(--muted);
  }
</style>
</head>
<body>

<section class="hero">
  <div class="container">
    <h1>AI that studies with you 🤖📚</h1>
    <p>Your personal tutor for planning, practicing, and mastering any subject.</p>
    <a class="cta" href="#tools">Try it free</a>
  </div>
</section>

<section id="tools">
  <div class="container grid grid-2">
    <div class="card builder">
      <h2>🗂️ Study Plan Builder</h2>
      <p>Create a simple weekly plan in seconds.</p>
      <input id="subject" placeholder="Subject (e.g. Biology)" />
      <select id="level">
        <option>Beginner</option>
        <option>Intermediate</option>
        <option>Advanced</option>
      </select>
      <input id="hours" type="number" placeholder="Hours per week" />
      <button onclick="buildPlan()">Build my plan</button>
      <div class="plan-output" id="plan"></div>
    </div>

    <div class="card">
      <h2>💬 AI Tutor Chat</h2>
      <p>Ask questions and get instant guidance.</p>
      <div class="chatbox">
        <div class="messages" id="messages">
          <div class="msg bot">👋 Hi! What are you studying today?</div>
        </div>
        <input id="chatInput" placeholder="Type a question and press Enter…" />
      </div>
    </div>
  </div>
</section>

<section>
  <div class="container">
    <h2>✨ Features</h2>
    <div class="grid grid-3">
      <div class="card">
        <div class="feature-icon">📝</div>
        <h3>Homework Help</h3>
        <p>Step-by-step explanations to unblock you fast.</p>
      </div>
      <div class="card">
        <div class="feature-icon">❓</div>
        <h3>Quiz Generator</h3>
        <p>Practice with auto-generated questions.</p>
      </div>
      <div class="card">
        <div class="feature-icon">📄</div>
        <h3>Notes Summarizer</h3>
        <p>Turn long notes into clear key points.</p>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="container">
    <h2>🎓 Who it's for</h2>
    <div class="grid grid-2">
      <div class="card">
        <h3>Students</h3>
        <p>Study smarter, stay organized, and gain confidence before exams.</p>
      </div>
      <div class="card">
        <h3>Teachers</h3>
        <p>Create quizzes, summaries, and support students at scale.</p>
      </div>
    </div>
  </div>
</section>

<section>
  <div class="container">
    <h2>💳 Simple Pricing</h2>
    <div class="grid grid-3">
      <div class="card">
        <h3>Free</h3>
        <div class="price">\$0</div>
        <p>Basic chat + study plans</p>
      </div>
      <div class="card">
        <h3>Student</h3>
        <div class="price">\$9</div>
        <p>Unlimited help & quizzes</p>
      </div>
      <div class="card">
        <h3>Teacher</h3>
        <div class="price">\$19</div>
        <p>Class tools & analytics</p>
      </div>
    </div>
  </div>
</section>

<footer>
  © 2026 AI Education Platform · Learn better, together 🌱
</footer>

<script>
  function buildPlan() {
    const subject = document.getElementById("subject").value || "your subject";
    const level = document.getElementById("level").value;
    const hours = document.getElementById("hours").value || 5;
    document.getElementById("plan").innerText =
      `📅 Plan: Study ${subject} (${level}) for about ${hours} hours per week.\n• Review basics\n• Practice problems\n• Weekly recap`;
  }

  const input = document.getElementById("chatInput");
  const messages = document.getElementById("messages");

  input.addEventListener("keypress", e => {
    if (e.key === "Enter" && input.value.trim()) {
      const userMsg = document.createElement("div");
      userMsg.className = "msg user";
      userMsg.textContent = input.value;
      messages.appendChild(userMsg);

      const botMsg = document.createElement("div");
      botMsg.className = "msg bot";
      botMsg.textContent = "🤔 Let's break that down together step by step.";
      messages.appendChild(botMsg);

      input.value = "";
      messages.scrollTop = messages.scrollHeight;
    }
  });
</script>

</body>
</html>
