<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>StudyWithAI | AI That Studies With You</title>
  <style>
    :root {
      --primary-blue: #2563eb;
      --secondary-blue: #0ea5e9;
      --soft-green: #10b981;
      --light-bg: #f8fafc;
      --text-dark: #1e293b;
      --text-light: #64748b;
      --card-bg: #ffffff;
      --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
      --radius: 12px;
      --transition: all 0.3s ease;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
      line-height: 1.6;
      color: var(--text-dark);
      background-color: var(--light-bg);
      padding: 0;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 16px;
    }

    /* Header */
    header {
      padding: 16px 0;
      background-color: var(--card-bg);
      box-shadow: var(--shadow);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .header-content {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.8rem;
      font-weight: 700;
      color: var(--primary-blue);
    }

    .logo span {
      color: var(--soft-green);
    }

    nav a {
      margin-left: 20px;
      text-decoration: none;
      color: var(--text-dark);
      font-weight: 500;
      transition: var(--transition);
    }

    nav a:hover {
      color: var(--primary-blue);
    }

    .btn {
      background-color: var(--primary-blue);
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: var(--radius);
      font-weight: 600;
      cursor: pointer;
      transition: var(--transition);
    }

    .btn:hover {
      background-color: var(--secondary-blue);
      transform: translateY(-2px);
    }

    /* Hero Section */
    .hero {
      padding: 64px 0;
      text-align: center;
      background: linear-gradient(135deg, var(--primary-blue), var(--soft-green));
      color: white;
      border-radius: 0 0 var(--radius) var(--radius);
    }

    .hero h1 {
      font-size: 3rem;
      font-weight: 800;
      margin-bottom: 16px;
      line-height: 1.3;
    }

    .hero p {
      font-size: 1.25rem;
      max-width: 700px;
      margin: 0 auto 24px;
      opacity: 0.95;
    }

    .hero .btn {
      background-color: white;
      color: var(--primary-blue);
      font-weight: 600;
    }

    .hero .btn:hover {
      background-color: #f1f5f9;
      transform: translateY(-2px);
    }

    .hero-emoji {
      font-size: 4rem;
      margin-top: 20px;
    }

    /* Features Section */
    .features {
      padding: 64px 0;
      text-align: center;
    }

    .section-title {
      font-size: 2.2rem;
      font-weight: 700;
      margin-bottom: 16px;
      color: var(--text-dark);
    }

    .section-subtitle {
      font-size: 1.1rem;
      color: var(--text-light);
      max-width: 700px;
      margin: 0 auto 40px;
    }

    .features-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 24px;
      margin-top: 32px;
    }

    .feature-card {
      background-color: var(--card-bg);
      border-radius: var(--radius);
      padding: 24px;
      box-shadow: var(--shadow);
      transition: var(--transition);
      border: 1px solid #e2e8f0;
    }

    .feature-card:hover {
      transform: translateY(-8px);
    }

    .feature-icon {
      font-size: 2.5rem;
      margin-bottom: 16px;
      color: var(--primary-blue);
    }

    .feature-card h3 {
      font-size: 1.4rem;
      margin-bottom: 12px;
      color: var(--text-dark);
    }

    .feature-card p {
      color: var(--text-light);
      font-size: 0.95rem;
    }

    /* Study Plan Builder */
    .plan-builder {
      padding: 64px 0;
      background-color: var(--light-bg);
      margin: 0 auto;
    }

    .builder-container {
      background-color: var(--card-bg);
      border-radius: var(--radius);
      padding: 32px;
      box-shadow: var(--shadow);
      max-width: 900px;
      margin: 0 auto;
      text-align: center;
    }

    .builder-form {
      display: flex;
      flex-direction: column;
      gap: 16px;
      margin-top: 24px;
    }

    .builder-form label {
      font-weight: 500;
      color: var(--text-dark);
      text-align: left;
    }

    .builder-form input, .builder-form select {
      padding: 12px;
      border: 1px solid #cbd5e1;
      border-radius: var(--radius);
      font-size: 1rem;
      transition: var(--transition);
    }

    .builder-form input:focus, .builder-form select:focus {
      outline: none;
      border-color: var(--primary-blue);
      box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.3);
    }

    .builder-submit {
      background-color: var(--soft-green);
      color: white;
      font-weight: 600;
      padding: 14px;
      border-radius: var(--radius);
      margin-top: 16px;
      border: none;
      cursor: pointer;
      transition: var(--transition);
    }

    .builder-submit:hover {
      background-color: #059669;
    }

    .plan-preview {
      margin-top: 24px;
      padding: 16px;
      background-color: #ebf9f5;
      border-radius: var(--radius);
      max-height: 300px;
      overflow-y: auto;
      border: 1px solid #a7f3d0;
      font-size: 0.95rem;
    }

    /* Chatbot Tutor */
    .chatbot {
      padding: 64px 0;
      text-align: center;
    }

    .chat-container {
      max-width: 900px;
      margin: 0 auto;
      background-color: var(--card-bg);
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: var(--shadow);
      height: 500px;
      display: flex;
      flex-direction: column;
    }

    .chat-header {
      background-color: var(--primary-blue);
      color: white;
      padding: 16px;
      text-align: center;
      font-weight: 600;
      font-size: 1.1rem;
    }

    .chat-messages {
      flex: 1;
      padding: 16px;
      overflow-y: auto;
      background-color: #f1f5f9;
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .message {
      max-width: 80%;
      padding: 12px 16px;
      border-radius: var(--radius);
      font-size: 0.95rem;
      line-height: 1.5;
    }

    .bot-message {
      align-self: flex-start;
      background-color: var(--primary-blue);
      color: white;
      border-radius: var(--radius) var(--radius) var(--radius) 0;
    }

    .user-message {
      align-self: flex-end;
      background-color: var(--soft-green);
      color: white;
      border-radius: var(--radius) var(--radius) 0 var(--radius);
    }

    .chat-input {
      display: flex;
      padding: 12px 16px;
      background-color: #f1f5f9;
      border-top: 1px solid #e2e8f0;
    }

    .chat-input input {
      flex: 1;
      padding: 10px 12px;
      border: 1px solid #cbd5e1;
      border-radius: var(--radius);
      font-size: 0.95rem;
      outline: none;
    }

    .chat-input button {
      background-color: var(--primary-blue);
      color: white;
      border: none;
      padding: 10px 16px;
      border-radius: var(--radius);
      margin-left: 8px;
      cursor: pointer;
      font-weight: 500;
    }

    /* Use Cases */
    .use-cases {
      padding: 64px 0;
      background-color: var(--light-bg);
    }

    .use-cases-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 24px;
      margin-top: 32px;
    }

    .use-case {
      background-color: var(--card-bg);
      border-radius: var(--radius);
      padding: 24px;
      box-shadow: var(--shadow);
      border-top: 4px solid var(--soft-green);
    }

    .use-case h3 {
      font-size: 1.4rem;
      margin-bottom: 12px;
      color: var(--text-dark);
    }

    .use-case p {
      color: var(--text-light);
      margin-bottom: 16px;
      font-size: 0.95rem;
    }

    .use-case-emoji {
      font-size: 2rem;
      margin-bottom: 16px;
    }

    /* Pricing */
    .pricing {
      padding: 64px 0;
      text-align: center;
    }

    .pricing-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 24px;
      margin-top: 32px;
    }

    .pricing-card {
      background-color: var(--card-bg);
      border-radius: var(--radius);
      padding: 32px;
      box-shadow: var(--shadow);
      border: 1px solid #e2e8f0;
      transition: var(--transition);
    }

    .pricing-card:hover {
      transform: translateY(-8px);
    }

    .pricing-card h3 {
      font-size: 1.6rem;
      margin-bottom: 12px;
      color: var(--text-dark);
    }

    .pricing-card .price {
      font-size: 2.5rem;
      font-weight: 700;
      color: var(--primary-blue);
      margin: 8px 0;
    }

    .pricing-card .price span {
      font-size: 0.85rem;
      color: var(--text-light);
    }

    .pricing-card ul {
      list-style: none;
      margin: 20px 0;
      text-align: left;
      color: var(--text-light);
    }

    .pricing-card li {
      margin-bottom: 10px;
      display: flex;
      align-items: center;
    }

    .pricing-card li::before {
      content: "✓";
      color: var(--soft-green);
      margin-right: 8px;
      font-weight: 700;
    }

    .popular {
      border: 2px solid var(--soft-green);
      position: relative;
    }

    .popular::before {
      content: "Most Popular";
      position: absolute;
      top: -12px;
      left: 50%;
      transform: translateX(-50%);
      background-color: var(--soft-green);
      color: white;
      font-size: 0.85rem;
      font-weight: 600;
      padding: 4px 12px;
      border-radius: 20px;
    }

    /* Footer */
    footer {
      padding: 32px 0;
      background-color: var(--card-bg);
      text-align: center;
      color: var(--text-light);
      font-size: 0.9rem;
      border-top: 1px solid #e2e8f0;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .hero h1 {
        font-size: 2.4rem;
      }

      .hero p {
        font-size: 1.1rem;
      }

      .features-grid, .use-cases-grid, .pricing-grid {
        grid-template-columns: 1fr;
      }

      .chat-container {
        height: 450px;
      }

      .chat-messages {
        padding: 12px;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <div class="header-content">
        <div class="logo">Study<span>WithAI</span></div>
        <nav>
          <a href="#features">Features</a>
          <a href="#plan">Study Plan</a>
          <a href="#chat">Tutor Bot</a>
          <a href="#pricing">Pricing</a>
        </nav>
      </div>
    </div>
  </header>

  <section class="hero">
    <div class="container">
      <h1>AI that studies with you</h1>
      <p>Get personalized homework help, generate quizzes, summarize notes — your AI study partner adapts to your pace and learning goals.</p>
      <button class="btn" onclick="document.getElementById('plan').scrollIntoView({behavior: 'smooth'})">Build My Study Plan</button>
      <div class="hero-emoji">📚🤖✨</div>
    </div>
  </section>

  <section id="features" class="features">
    <div class="container">
      <h2 class="section-title">Smart Study Features</h2>
      <p class="section-subtitle">Everything you need to master your coursework with AI-powered learning tools.</p>
      
      <div class="features-grid">
        <div class="feature-card">
          <div class="feature-icon">📄</div>
          <h3>Homework Help</h3>
          <p>Get step-by-step solutions for problems across math, science, and humanities. Understand the "why" behind every answer.</p>
        </div>
        
        <div class="feature-card">
          <div class="feature-icon">🎯</div>
          <h3>Quiz Generator</h3>
          <p>Create custom quizzes from your notes or textbooks. Perfect for self-testing and exam prep.</p>
        </div>
        
        <div class="feature-card">
          <div class="feature-icon">📰</div>
          <h3>Notes Summarizer</h3>
          <p>Turn lengthy lectures and readings into concise, easy-to-review summaries with key points highlighted.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="plan" class="plan-builder">
    <div class="container">
      <h2 class="section-title">Build Your Study Plan</h2>
      <p class="section-subtitle">Customize your study schedule based on your subjects, goals, and available time.</p>
      
      <div class="builder-container">
        <form class="builder-form">
          <div>
            <label for="subject">Subject</label>
            <select id="subject" required>
              <option value="">Select a subject</option>
              <option value="math">Mathematics</option>
              <option value="science">Science</option>
              <option value="history">History</option>
              <option value="literature">Literature</option>
              <option value="language">Language</option>
            </select>
          </div>
          
          <div>
            <label for="goal">Learning Goal</label>
            <select id="goal" required>
              <option value="">Select a goal</option>
              <option value="review">Review for exam</option>
              <option value="understand">Understand concept</option>
              <option value="master">Master topic</option>
              <option value="prepare">Prepare assignment</option>
            </select>
          </div>
          
          <div>
            <label for="time">Available Study Time (hours/week)</label>
            <input type="number" id="time" min="1" max="50" value="10" required />
          </div>
          
          <div>
            <label for="duration">Study Duration (days)</label>
            <input type="number" id="duration" min="1" max="30" value="7" required />
          </div>
          
          <button type="submit" class="builder-submit" onclick="generatePlan(event)">Generate Plan</button>
        </form>
        
        <div class="plan-preview" id="planPreview">
          <p>Your study plan will appear here...</p>
        </div>
      </div>
    </div>
  </section>

  <section id="chat" class="chatbot">
    <div class="container">
      <h2 class="section-title">Chat with Your Tutor Bot</h2>
      <p class="section-subtitle">Ask questions, test your knowledge, and get instant feedback anytime.</p>
      
      <div class="chat-container">
        <div class="chat-header">StudyWithAI Assistant 🤖</div>
        <div class="chat-messages" id="chatMessages">
          <div class="message bot-message">Hi there! I'm your AI study buddy. How can I help you today?</div>
        </div>
        <div class="chat-input">
          <input type="text" id="chatInput" placeholder="Type your question..." />
          <button onclick="sendMessage()">Send</button>
        </div>
      </div>
    </div>
  </section>

  <section class="use-cases">
    <div class="container">
      <h2 class="section-title">For Students & Teachers</h2>
      <p class="section-subtitle">Designed to support learning at every level.</p>
      
      <div class="use-cases-grid">
        <div class="use-case">
          <div class="use-case-emoji">🎓</div>
          <h3>For Students</h3>
          <p>Get instant help with tough assignments, create personalized study schedules, and reinforce understanding with AI-powered quizzes.</p>
          <p>Perfect for high school and university students building strong study habits.</p>
        </div>
        
        <div class="use-case">
          <div class="use-case-emoji">🏫</div>
          <h3>For Teachers</h3>
          <p>Save time creating quizzes and lesson materials. Use AI to summarize class content and identify key learning points for your students.</p>
          <p>Enhance your curriculum with smart, adaptive learning tools.</p>
        </div>
      </div>
    </div>
  </section>

  <section id="pricing" class="pricing">
    <div class="container">
      <h2 class="section-title">Simple, Transparent Pricing</h2>
      <p class="section-subtitle">Choose the plan that fits your learning needs.</p>
      
      <div class="pricing-grid">
        <div class="pricing-card">
          <h3>Basic</h3>
          <div class="price">$9<span>/month</span></div>
          <ul>
            <li>Homework help</li>
            <li>Basic quiz generator</li>
            <li>Notes summarizer</li>
            <li>2 study plans per month</li>
            <li>1-on-1 chat support</li>
          </ul>
          <button class="btn">Get Started</button>
        </div>
        
        <div class="pricing-card popular">
          <h3>Premium</h3>
          <div class="price">$19<span>/month</span></div>
          <ul>
            <li>All Basic features</li>
            <li>Advanced study plan builder</li>
            <li>Custom quiz templates</li>
            <li>Priority chat support</li>
            <li>Weekly progress reports</li>
            <li>Offline access</li>
          </ul>
          <button class="btn">Get Started</button>
        </div>
        
        <div class="pricing-card">
          <h3>Teacher Pro</h3>
          <div class="price">$49<span>/month</span></div>
          <ul>
            <li>All Premium features</li>
            <li>Classroom collaboration features</li>
            <li>Gradebook integration</li>
            <li>Custom classroom content</li>
            <li>Multi-user access</li>
            <li>Teacher dashboard</li>
          </ul>
          <button class="btn">Get Started</button>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <p>© 2026 StudyWithAI. All rights reserved. | Privacy | Terms</p>
    </div>
  </footer>

  <script>
    function generatePlan(event) {
      event.preventDefault();
      const subject = document.getElementById('subject').value;
      const goal = document.getElementById('goal').value;
      const time = document.getElementById('time').value;
      const duration = document.getElementById('duration').value;
      
      const plan = `
        <strong>Your Study Plan</strong><br><br>
        <strong>Subject:</strong> ${subject.charAt(0).toUpperCase() + subject.slice(1)}<br>
        <strong>Goal:</strong> ${goal.replace(/-/g, ' ')}<br>
        <strong>Total Time:</strong> ${time} hours/week over ${duration} days<br><br>
        <strong>Daily Schedule:</strong><br>
        • 30 min: Review lecture notes<br>
        • 30 min: Practice problems<br>
        • 15 min: Flashcard quiz<br>
        • 5 min: Reflect and plan next session<br><br>
        <em>Tip: Use the AI summarizer to condense complex topics.</em>
      `;
      
      document.getElementById('planPreview').innerHTML = plan;
    }

    function sendMessage() {
      const input = document.getElementById('chatInput');
      const message = input.value.trim();
      if (!message) return;
      
      const messages = document.getElementById('chatMessages');
      
      // Add user message
      const userMsg = document.createElement('div');
      userMsg.className = 'message user-message';
      userMsg.textContent = message;
      messages.appendChild(userMsg);
      
      // Clear input
      input.value = '';
      
      // Simulate AI response (in real app, this would call an API)
      setTimeout(() => {
        let response;
        if (message.toLowerCase().includes('hello') || message.toLowerCase().includes('hi')) {
          response = "Hi! How can I help you study today?";
        } else if (message.toLowerCase().includes('math')) {
          response = "I can help you solve math problems step-by-step. Try asking me to solve 3x + 5 = 20!";
        } else if (message.toLowerCase().includes('quiz')) {
          response = "I can generate a quiz from your notes. Just send me your topic or 
