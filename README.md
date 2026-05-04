<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ryan Krause - CV</title>
  <style>
    :root {
      --primary: #0a3d62; /* Deep Blue */
      --accent: #f1c40f; /* Gold */
      --bg: #ffffff;
      --text: #333;
    }
    body.dark {
      --primary: #1e272e; /* Dark navy */
      --accent: #ffa801; /* Warm gold */
      --bg: #121212;
      --text: #f5f5f5;
    }
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      background-color: var(--bg);
      color: var(--text);
      scroll-behavior: smooth;
      transition: background-color 0.3s ease, color 0.3s ease;
    }
    header {
      background-color: var(--primary);
      color: #fff;
      padding: 2rem;
      text-align: center;
    }
    nav {
      background-color: #f4f4f4;
      padding: 1rem;
      text-align: center;
      position: sticky;
      top: 0;
      z-index: 1000;
    }
    body.dark nav {
      background-color: #2f3640;
    }
    nav a {
      margin: 0 1rem;
      text-decoration: none;
      color: var(--primary);
      font-weight: bold;
      transition: color 0.3s ease;
    }
    nav a:hover {
      color: var(--accent);
    }
    section {
      padding: 2rem;
      max-width: 900px;
      margin: auto;
      opacity: 0;
      transform: translateY(20px);
      transition: all 0.6s ease;
    }
    section.visible {
      opacity: 1;
      transform: translateY(0);
    }
    h2 {
      color: var(--primary);
      border-bottom: 2px solid var(--accent);
      padding-bottom: 0.5rem;
    }
    .btn {
      display: inline-block;
      background-color: var(--accent);
      color: var(--primary);
      padding: 0.7rem 1.2rem;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
      transition: background-color 0.3s ease, transform 0.3s ease;
    }
    .btn:hover {
      background-color: #d4ac0d;
      transform: scale(1.05);
    }
    footer {
      background-color: var(--primary);
      color: #fff;
      text-align: center;
      padding: 1rem;
      margin-top: 2rem;
    }
    #toggle-dark {
      cursor: pointer;
      background: none;
      border: 2px solid var(--accent);
      padding: 0.5rem 1rem;
      border-radius: 5px;
      color: var(--accent);
      font-weight: bold;
      margin-left: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Ryan Krause</h1>
    <p>Freelancer | Developer | Creative Strategist</p>
  </header>

  <nav>
    <a href="#about">About</a>
    <a href="#experience">Experience</a>
    <a href="#skills">Skills</a>
    <a href="#contact">Contact</a>
    <button id="toggle-dark">🌙 Dark Mode</button>
  </nav>

  <section id="about">
    <h2>About Me</h2>
    <p>Brief intro about your background, freelancing focus, and goals.</p>
  </section>

  <section id="experience">
    <h2>Experience</h2>
    <p>List your key projects, freelance work, and achievements.</p>
  </section>

  <section id="skills">
    <h2>Skills</h2>
    <p>Highlight technical skills (Excel, AutoBPO, Canva, Clash Royale deck‑building strategy 😉).</p>
  </section>

  <section id="contact">
    <h2>Contact</h2>
    <a href="mailto:your.email@example.com" class="btn">Email Me</a>
    <a href="cv.pdf" class="btn" download>Download CV</a>
  </section>

  <footer>
    <p>&copy; 2026 Ryan Krause. All rights reserved.</p>
  </footer>

  <script>
    // Reveal sections on scroll
    const sections = document.querySelectorAll("section");
    const revealOnScroll = () => {
      const triggerBottom = window.innerHeight * 0.85;
      sections.forEach(section => {
        const boxTop = section.getBoundingClientRect().top;
        if(boxTop < triggerBottom) {
          section.classList.add("visible");
        }
      });
    };
    window.addEventListener("scroll", revealOnScroll);
    revealOnScroll();

    // Dark mode toggle
    const toggleBtn = document.getElementById("toggle-dark");
    toggleBtn.addEventListener("click", () => {
      document.body.classList.toggle("dark");
      toggleBtn.textContent = document.body.classList.contains("dark") ? "☀️ Light Mode" : "🌙 Dark Mode";
    });
  </script>
</body>
</html>
