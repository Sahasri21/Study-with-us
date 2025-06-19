<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Inclusive Learning for Children</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap');
  body {
    font-family: 'Poppins', sans-serif;
    margin: 0;
    background: #f5f9ff;
    color: #333;
  }
  header {
    background: #4169e1;
    color: white;
    padding: 1rem 2rem;
    text-align: center;
    box-shadow: 0 2px 5px rgba(65, 105, 225, 0.4);
  }
  header h1 {
    margin: 0;
    font-weight: 600;
  }
  nav {
    background: #ffffff;
    box-shadow: 0 2px 5px rgba(0,0,0,0.07);
    display: flex;
    justify-content: center;
    gap: 1rem;
    padding: 1rem 0;
    position: sticky;
    top: 0;
    z-index: 10;
  }
  nav button {
    background: transparent;
    border: none;
    padding: 0.5rem 1rem;
    font-size: 1rem;
    cursor: pointer;
    color: #4169e1;
    border-bottom: 2px solid transparent;
    transition: all 0.3s ease;
  }
  nav button.active, nav button:hover {
    border-bottom: 2px solid #4169e1;
    font-weight: 600;
  }
  main {
    max-width: 960px;
    margin: 2rem auto;
    padding: 0 1rem;
  }
  section {
    display: none;
  }
  section.active {
    display: block;
  }
  h2 {
    color: #4169e1;
    margin-bottom: 1rem;
    border-bottom: 2px solid #4169e1;
    display: inline-block;
    padding-bottom: 0.25rem;
  }
  .book-list {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(280px,1fr));
    gap: 1.5rem;
    margin-bottom: 2rem;
  }
  .book {
    background: white;
    border-radius: 8px;
    box-shadow: 0 3px 6px rgb(0 0 0 / 0.1);
    padding: 1rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  .book h3 {
    margin-top: 0;
    color: #23395d;
  }
  .book p {
    flex-grow: 1;
    font-size: 0.95rem;
    color: #555;
  }
  .audio-control, .assignment-control {
    margin-top: 1rem;
    text-align: center;
  }
  button.action-btn {
    background: #4169e1;
    border: none;
    color: white;
    padding: 0.5rem 1.2rem;
    border-radius: 5px;
    cursor: pointer;
    font-weight: 600;
    transition: background 0.3s ease;
  }
  button.action-btn:hover {
    background: #254eda;
  }
  .assignment-list {
    list-style: none;
    padding-left: 0;
  }
  .assignment-list li {
    background: #e8efff;
    margin-bottom: 0.75rem;
    padding: 0.8rem 1rem;
    border-radius: 6px;
    font-weight: 500;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  .assignment-list li:hover {
    background: #c7d6ff;
  }
  .voice-input-area {
    margin-top: 1rem;
    display: flex;
    gap: 1rem;
    align-items: center;
  }
  textarea#voiceTextInput {
    width: 100%;
    min-height: 80px;
    resize: vertical;
    font-size: 1rem;
    padding: 0.5rem;
    border-radius: 5px;
    border: 1px solid #ddd;
    font-family: 'Poppins', sans-serif;
  }
  .voice-controls {
    display: flex;
    gap: 0.5rem;
  }
  .footer {
    text-align: center;
    color: #777;
    margin: 4rem 0 2rem;
    font-size: 0.9rem;
  }
  /* Accessibility focus indicator */
  button:focus, textarea:focus {
    outline-color: #4169e1;
    outline-offset: 2px;
  }
</style>
</head>
<body>
<header>
  <h1>Inclusive Learning Platform</h1>
</header>
<nav aria-label="Main navigation">
  <button class="nav-btn active" data-target="home" aria-current="page">Home</button>
  <button class="nav-btn" data-target="maths">Maths</button>
  <button class="nav-btn" data-target="science">Science</button>
  <button class="nav-btn" data-target="social">Social</button>
  <button class="nav-btn" data-target="english">English</button>
  <button class="nav-btn" data-target="telugu">Telugu</button>
  <button class="nav-btn" data-target="hindi">Hindi</button>
  <button class="nav-btn" data-target="assignments">Assignments</button>
</nav>
<main>
  <!-- Home Section -->
  <section id="home" class="active" tabindex="0" aria-label="Home page">
    <h2>Welcome to the Inclusive Learning Platform</h2>
    <p>This website is designed especially for children with disabilities. It includes features such as Voice to Text, Text to Voice, and accessible digital books for various school subjects.</p>
    <p>Navigate to each subject to explore text-based visual books and voice books designed for blind or visually impaired children. You can also practice assignments tailored for learning enhancement.</p>
    <h3>Voice to Text Input</h3>
    <div class="voice-input-area">
      <textarea id="voiceTextInput" aria-label="Voice to text input area" placeholder="Speak something or type here..."></textarea>
      <div class="voice-controls">
        <button id="startListening" class="action-btn" aria-pressed="false" title="Start Voice to Text">🎤 Start</button>
        <button id="stopListening" class="action-btn" disabled title="Stop Voice to Text">■ Stop</button>
      </div>
    </div>
    <h3>Text to Voice Output</h3>
    <textarea id="textToSpeak" placeholder="Enter text here to listen..." aria-label="Text to synthesize voice"></textarea>
    <div class="audio-control">
      <button id="speakText" class="action-btn">🔊 Speak Text</button>
    </div>
  </section>

  <!-- Subject Sections Template -->
  <section id="maths" tabindex="0" aria-label="Maths subject page">
    <h2>Maths Books</h2>
    <div class="book-list">
      <article class="book" tabindex="0" aria-label="Visual book: Basic Mathematics">
        <h3>Basic Mathematics</h3>
        <p>Visual text book covering fundamental concepts like addition, subtraction, multiplication, and division.</p>
        <h1>Textbook</h1>
        <p><a href="https://drive.google.com/drive/folders/1UvyEtnfNKpQdZgBG39wfP3-r1n0WKoYY?usp=drive_link">Maths for Class X </a></p>
      </article>
      <article class="book" tabindex="0" aria-label="Voice book: Maths for Blind">
        <h3>Maths for Blind</h3>
        <p>Video Class with math lessons designed specifically for blind children.</p>
        <h1>Video class</h1>
        <p><a href="https://youtube.com/playlist?list=PLXU0YkjMp6qhcUkwtbVsQIHA8Hc38RS-X&si=sxKWcSs5j-HFeWP-">Maths for Class X </a></p>
        <div class="audio-control">
          <button class="action-btn voicebook" data-text="Welcome to Maths for Blind. Let's learn numbers and arithmetic.">🔊 Play Audio</button>
        </div>
      </article>
    </div>
  </section>
  
  <section id="science" tabindex="0" aria-label="Science subject page">
    <h2>Science Books</h2>
    <div class="book-list">
      <article class="book" tabindex="0" aria-label="Visual book: Basic Science">
        <h3>Basic Science</h3>
        <p>Visual text book explaining natural phenomena, plants, animals, and simple experiments.</p>
        <h1>Textbook</h1>
        <p><a href="https://drive.google.com/drive/folders/1vIeEyxAuXU_EJ_cPSUFGIH1A5TYg-4lE?usp=drive_link">Science for Class X </a></p>
      </article>
      <article class="book" tabindex="0" aria-label="Voice book: Science for Blind">
        <h3>Science for Blind</h3>
        <p>Video Class designed for blind children to understand science concepts through listening.</p>
        <h1>Video Class</h1>
        <p1><a href="https://youtube.com/playlist?list=PLSPOLy5YYuv6TrHoC7xFmvqT5P175Zu9A&si=Z5_pMwqLJZ3TRYwk">Science for Class X </a></p1>
        <p2><a href="https://youtube.com/playlist?list=PLSPOLy5YYuv431DhRwiwIbtNRAIitu22G&si=CQUZCjQYAHqcsLkM">Science for Class X </a></p2>
        <p3><a href="https://youtube.com/playlist?list=PLSPOLy5YYuv7G7jZKAW1Rq656eaB4NC_9&si=mCHEXIRFDnN8q804">Science for Class X </a></p3>
        <div class="audio-control">
          <button class="action-btn voicebook" data-text="Welcome to Science for Blind. Explore the wonders of nature and physics.">🔊 Play Audio</button>
        </div>
      </article>
    </div>
  </section>

  <section id="social" tabindex="0" aria-label="Social subject page">
    <h2>Social Studies Books</h2>
    <div class="book-list">
      <article class="book" tabindex="0" aria-label="Visual book: Social Studies">
        <h3>Social Studies Textbook</h3>
        <p>Visual text book covering geography, history, and civics for children.</p>
        <h1>Textbook</h1>
        <p><a href="https://drive.google.com/drive/folders/1lYiKbtIDMOjXsdK7T3vl7-3_DI3pD_DF?usp=drive_link">Social for Class X </a></p>
      </article>
      <article class="book" tabindex="0" aria-label="Voice book: Social Studies for Blind">
        <h3>Social Studies for Blind</h3>
        <p>Video class with lessons on society, cultures, and history.</p>
        <h1>Video class</h1>
        <p1><a href="https://youtube.com/playlist?list=PLIyfCVkc5NnFS5mjFoHt_yC708U7xojyK&si=Y6x1C66vrujlFDrl">Social for Class X </a></p></a>
        <div class="audio-control">
          <button class="action-btn voicebook" data-text="Welcome to Social Studies for Blind. Learn about history and cultures.">🔊 Play Audio</button>
        </div>
      </article>
    </div>
  </section>

  <section id="english" tabindex="0" aria-label="English subject page">
    <h2>English Books</h2>
    <div class="book-list">
      <article class="book" tabindex="0" aria-label="Visual book: English Grammar">
        <h3>English Grammar</h3>
        <p>Visual text book on basic grammar rules and sentence construction.</p>
        <h1>Textbook</h1>
        <p><a href="https://drive.google.com/drive/folders/11rR5mUeEZxOHUIMvXuCm62Ja1iFP9NhI?usp=drive_link">English for Class X </a></p>
      </article>
      <article class="book" tabindex="0" aria-label="Voice book: English for Blind">
        <h3>English for Blind</h3>
        <p>Video Class on English language learning designed for blind children.</p>
        <h1>Video Class</h1>
        <p1><a href="https://youtube.com/playlist?list=PLM7yGQ1t_ECL2uRWrcAjy1xgJkPZ4_TQv&si=x0Ij89P7BxV7MB1K">English for Class X </a></p1>
        <p2><a href="https://youtube.com/playlist?list=PLM7yGQ1t_ECI64N2yzMXt8hYqPwRpkP1A&si=9Yuben8RDtncs-IG">English for Class X</a></p2>
        <div class="audio-control">
          <button class="action-btn voicebook" data-text="Welcome to English for Blind. Learn alphabets, words, and sentences.">🔊 Play Audio</button>
        </div>
      </article>
    </div>
  </section>

  <section id="telugu" tabindex="0" aria-label="Telugu subject page">
    <h2>Telugu Books</h2>
    <div class="book-list">
      <article class="book" tabindex="0" aria-label="Visual book: Telugu Basics">
        <h3>Telugu Basics</h3>
        <p>Visual text book on Telugu letters, words, and common phrases.</p>
        <h1>Textbook</h1>
        <p><a href="https://drive.google.com/drive/folders/1UplGBez9hLig4-SUr0Rafibt4n2iGg4_?usp=drive_link">Telugu for Class X </a></p>
      </article>
      <article class="book" tabindex="0" aria-label="Voice book: Telugu for Blind">
        <h3>Telugu for Blind</h3>
        <p>Video Class for learning Telugu language for blind children.</p>
         <h1>Video Class</h1>
        <p1><a href="https://youtube.com/playlist?list=PL1sxfq7ZbDn5WoxHEqmA6AE1EAtE1P2hP&si=_qGk8FXQNitJaWYE">Telugu for Class X </a></p>
        <div class="audio-control">
          <button class="action-btn voicebook" data-text="Welcome to Telugu for Blind. Learn Telugu alphabets and simple words.">🔊 Play Audio</button>
        </div>
      </article>
    </div>
  </section>

  <section id="hindi" tabindex="0" aria-label="Hindi subject page">
    <h2>Hindi Books</h2>
    <div class="book-list">
      <article class="book" tabindex="0" aria-label="Visual book: Hindi Basics">
        <h3>Hindi Basics</h3>
        <p>Visual text book helping children learn Hindi letters and common vocabulary.</p>
        <h1>Textbook</h1>
        <p><a href="https://drive.google.com/drive/folders/1D4pbXRJ0En5uCbJ7JTQxW0fsQrTPs-d6?usp=drive_link">Hindi for Class X </a></p>
      </article>
      <article class="book" tabindex="0" aria-label="Voice book: Hindi for blind">
        <h3>Hindi for Blind</h3>
        <p>Video Class designed for blind children to learn Hindi language basics.</p>
        <h1>Video Class</h1>
        <p1><a href="https://youtu.be/3pl2q_xOWjE?si=tUwPuA8pfY3W1-mX">Hindi for Class X </a></p>
        <div class="audio-control">
          <button class="action-btn voicebook" data-text="Welcome to Hindi for Blind. Learn Hindi alphabets and words.">🔊 Play Audio</button>
        </div>
      </article>
    </div>
  </section>

  <section id="assignments" tabindex="0" aria-label="Assignments page">
    <h2>Practice Assignments</h2>
    <p>Select an assignment below to read the question and practice your answer using voice input or keyboard.</p>
    <ul class="assignment-list" role="list">
      <li tabindex="0" data-question="What is 5 plus 3?">Math: Simple Addition</li>
      <li tabindex="0" data-question="Name the planets in our solar system.">Science: Planets</li>
      <li tabindex="0" data-question="Who is the first Prime Minister of India?">Social Studies: Leaders</li>
      <li tabindex="0" data-question="Construct a sentence using the word 'beautiful'.">English: Sentence Construction</li>
      <li tabindex="0" data-question="Write the Telugu alphabet for A.">Telugu: Alphabets</li>
      <li tabindex="0" data-question="Write the Hindi word for 'water'.">Hindi: Vocabulary</li>
    </ul>

    <div id="assignment-question-container" style="margin-top: 1.5rem;">
      <h3>Question:</h3>
      <p id="assignment-question" style="font-weight: 600;"></p>
      <textarea id="assignment-answer" aria-label="Your answer" placeholder="Type or speak your answer here..." style="width:100%; min-height:100px; font-size: 1rem; border-radius: 6px; padding: 0.7rem; border: 1px solid #ccc;"></textarea>
      <div class="voice-controls" style="margin-top: 0.5rem;">
        <button id="startAnswerListening" class="action-btn" aria-pressed="false" title="Start Voice Input for Answer">🎤 Start</button>
        <button id="stopAnswerListening" class="action-btn" disabled title="Stop Voice Input for Answer">■ Stop</button>
      </div>
    </div>
  </section>
</main>
<footer class="footer" role="contentinfo">
  &copy; 2024 Inclusive Learning Platform - Designed for Disabled Children
</footer>

<script>
  // Navigation functionality
  const navButtons = document.querySelectorAll('nav .nav-btn');
  const sections = document.querySelectorAll('main section');
  
  navButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      navButtons.forEach(b => b.classList.remove('active'));
      btn.classList.add('active');
      const target = btn.dataset.target;
      sections.forEach(sec => {
        if(sec.id === target) {
          sec.classList.add('active');
          sec.focus();
        } else {
          sec.classList.remove('active');
        }
      });
    });
  });

  // Text to speech feature for voice books and speak text
  function speakText(text) {
    if ('speechSynthesis' in window) {
      const synth = window.speechSynthesis;
      if(synth.speaking) {
        synth.cancel();
      }
      if(text.trim() !== '') {
        const utterance = new SpeechSynthesisUtterance(text);
        utterance.lang = 'en-US';
        synth.speak(utterance);
      }
    } else {
      alert('Sorry, your browser does not support text to speech.');
    }
  }

  document.querySelectorAll('.voicebook').forEach(btn => {
    btn.addEventListener('click', () => {
      const text = btn.dataset.text;
      speakText(text);
    });
  });

  document.getElementById('speakText').addEventListener('click', () => {
    const text = document.getElementById('textToSpeak').value;
    speakText(text);
  });

  // Voice to text functionality for home page and assignments
  // Using Web Speech API
  let recognition;
  let isListening = false;
  if ('webkitSpeechRecognition' in window || 'SpeechRecognition' in window) {
    const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
    recognition = new SpeechRecognition();
    recognition.lang = 'en-IN';
    recognition.interimResults = false;
    recognition.maxAlternatives = 1;

    // Voice to text for home textarea
    const startBtn = document.getElementById('startListening');
    const stopBtn = document.getElementById('stopListening');
    const voiceTextInput = document.getElementById('voiceTextInput');

    startBtn.addEventListener('click', () => {
      if (!isListening) {
        recognition.start();
        startBtn.setAttribute('aria-pressed', 'true');
        startBtn.disabled = true;
        stopBtn.disabled = false;
        isListening = true;
      }
    });
    stopBtn.addEventListener('click', () => {
      if (isListening) {
        recognition.stop();
        startBtn.setAttribute('aria-pressed', 'false');
        startBtn.disabled = false;
        stopBtn.disabled = true;
        isListening = false;
      }
    });
    recognition.addEventListener('result', (event) => {
      const speechResult = event.results[0][0].transcript;
      voiceTextInput.value += (voiceTextInput.value ? ' ' : '') + speechResult;
    });
    recognition.addEventListener('end', () => {
      startBtn.disabled = false;
      stopBtn.disabled = true;
      startBtn.setAttribute('aria-pressed', 'false');
      isListening = false;
    });

    // Voice to text for assignment answer
    const startAnswerBtn = document.getElementById('startAnswerListening');
    const stopAnswerBtn = document.getElementById('stopAnswerListening');
    const assignmentAnswer = document.getElementById('assignment-answer');

    startAnswerBtn.addEventListener('click', () => {
      if (!isListening) {
        recognition.start();
        startAnswerBtn.setAttribute('aria-pressed', 'true');
        startAnswerBtn.disabled = true;
        stopAnswerBtn.disabled = false;
        isListening = true;
      }
    });
    stopAnswerBtn.addEventListener('click', () => {
      if (isListening) {
        recognition.stop();
        startAnswerBtn.setAttribute('aria-pressed', 'false');
        startAnswerBtn.disabled = false;
        stopAnswerBtn.disabled = true;
        isListening = false;
      }
    });
    recognition.addEventListener('result', (event) => {
      // Determine if current active section is assignments for appending correctly
      if(document.getElementById('assignments').classList.contains('active')) {
        const speechResult = event.results[0][0].transcript;
        assignmentAnswer.value += (assignmentAnswer.value ? ' ' : '') + speechResult;
      }
    });
    recognition.addEventListener('end', () => {
      startAnswerBtn.disabled = false;
      stopAnswerBtn.disabled = true;
      startAnswerBtn.setAttribute('aria-pressed', 'false');
      isListening = false;
    });
  } else {
    // Disable buttons if not supported
    ['startListening', 'stopListening', 'startAnswerListening', 'stopAnswerListening'].forEach(id => {
      const el = document.getElementById(id);
      el.disabled = true;
      el.title = 'Web Speech API not supported in this browser.';
    });
  }

  // Assignments question selection logic
  const assignmentListItems = document.querySelectorAll('.assignment-list li');
  const questionDisplay = document.getElementById('assignment-question');
  const answerInput = document.getElementById('assignment-answer');

  assignmentListItems.forEach(item => {
    item.addEventListener('click', () => {
      const question = item.dataset.question;
      questionDisplay.textContent = question;
      answerInput.value = '';
    });
    item.addEventListener('keypress', (e) => {
      if(e.key === 'Enter' || e.key === ' ') {
        e.preventDefault();
        item.click();
      }
    });
  });
</script>
</body>
</html>

