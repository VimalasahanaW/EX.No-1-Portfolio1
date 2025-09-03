# Ex01 Portfolio
## Date:03-09-25

## AIM
To create a Portfolio using HTML and CSS.

## ALGORITHM
### STEP 1
Create an HTML file (index.html)

### STEP 2
Create a CSS file (style.css)

### STEP 3
Include a navigation bar with links to different sections.

### STEP 4
Add structured sections for introduction, about, projects, and contact details.

### STEP 5
Define global styles for fonts, colors, and layout.

### STEP 6
Style the header, navigation bar, and sections.

### STEP 7
Use Flexbox or CSS Grid for layout design.

### STEP 8
Add hover effects and transitions for interactivity.

### STEP 9
Add Images and Media.

### STEP 10
Use optimized images for a professional look.

### STEP 11
Open the HTML file in a browser to check layout and functionality.

### STEP 12
Fix styling issues and refine content placement.

### STEP 13
Deploy the Portfolio.

### STEP 14
Upload to GitHub Pages for free hosting.

## PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Vimala Sahana W — Portfolio</title>
  <meta name="description" content="Personal portfolio website for Your Name: projects, skills, and contact." />

  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

  <style>
    :root {
      --bg: #020c19;         
      --panel: #010919;      
      --muted: #828aa3;       
      --text: #e6eaf2;       
      --brand: #7c5cff;      
      --brand-2: #22c55e;    
      --ring: rgba(124, 92, 255, 0.45); 
      --border: #1f2433;   
      --shadow: 0 10px 30px rgba(0,0,0,0.35);
      --radius: 16px;
      --radius-sm: 16px;
      --maxw: 1100px;
    }
    .light {
      --bg: #f8fafc86;
      --panel: #ffffff;
      --muted: #5b647a;
      --text: #0b1020;
      --brand: #170b02;
      --brand-2: #059669;
      --ring: rgba(109, 40, 217, 0.25);
      --border: #e5e7eb;
      --shadow: 0 10px 25px rgba(17, 24, 39, 0.08);
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    .container { width: 100%; max-width: var(--maxw); margin: 0 auto; padding: 0 20px; }
    header {
      position: sticky; top: 0; z-index: 50;
      backdrop-filter: blur(10px);
      background: color-mix(in srgb, var(--bg) 70%, transparent);
      border-bottom: 1px solid var(--border);
    }
    .nav {
      display: flex; align-items: center; justify-content: space-between; gap: 12px;
      height: 60px;
    }
    .brand { display: flex; align-items: center; gap: 10px; font-weight: 700; letter-spacing: 0.3px; }
    .brand-logo {
      width: 36px; height: 36px; border-radius: 50%;
      background: radial-gradient(120% 120% at 30% 20%, var(--brand) 0%, var(--brand-2) 60%, rgba(255,255,255,0.2) 100%);
      box-shadow: var(--shadow);
    }
    nav a { color: var(--muted); text-decoration: none; padding: 8px 12px; border-radius: 10px; }
    nav a:hover, nav a:focus { color: var(--text); background: color-mix(in srgb, var(--panel) 80%, transparent); outline: none; }

    .btn {
      display: inline-flex; align-items: center; justify-content: center;
      padding: 10px 16px; border-radius: 999px; border: 1px solid var(--border);
      color: var(--text); background: linear-gradient(180deg, color-mix(in srgb, var(--panel) 90%, transparent), var(--panel));
      box-shadow: var(--shadow); text-decoration: none; font-weight: 600;
    }
    .btn:hover { transform: translateY(-1px); }
    .btn:focus { outline: 3px solid var(--ring); outline-offset: 2px; }
    .btn.primary { background: linear-gradient(135deg, var(--brand), var(--brand-2)); border: none; }
    section { padding: 60px 0; }
    .section-title { font-size: 24px; margin: 0 0 18px; }
    .muted { color: var(--muted); }
    .card {
      background: linear-gradient(180deg, color-mix(in srgb, var(--panel) 85%, transparent), var(--panel));
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 20px;
      box-shadow: var(--shadow);
    }

    /* About */
    .about-grid { display: grid; grid-template-columns: 1.1fr 0.9fr; gap: 18px; }
    .list { margin: 0; padding-left: 18px; }

    /* Skills */
    .tags { display: flex; flex-wrap: wrap; gap: 10px; }
    .tag { padding: 8px 12px; border-radius: 999px; border: 1px solid var(--border); color: var(--muted); font-weight: 600; font-size: 14px; }

    /* Projects */
    .grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 18px; }
    .project h3 { margin: 10px 0 8px; font-size: 18px; }
    .project p { margin: 0 0 12px; }
    .project .links { display: flex; gap: 10px; }

    /* Timeline */
    .timeline { border-left: 2px dashed var(--border); padding-left: 16px; }
    .timeline-item { margin: 0 0 18px; }
    .timeline-item h4 { margin: 0; font-size: 16px; }
    .timeline-item .when { font-size: 13px; color: var(--muted); }

    /* Contact */
    form { display: grid; gap: 12px; }
    input, textarea {
      padding: 12px 14px; border-radius: 12px; border: 1px solid var(--border);
      background: color-mix(in srgb, var(--panel) 80%, transparent);
      color: var(--text); font: inherit;
    }
    textarea { min-height: 120px; resize: vertical; }
    input:focus, textarea:focus { outline: 3px solid var(--ring); outline-offset: 2px; }

    /* Footer */
    footer { padding: 40px 0; text-align: center; color: var(--muted); border-top: 1px solid var(--border); }

    /* Responsive */
    @media (max-width: 900px) {
      .hero-inner, .about-grid { grid-template-columns: 1fr; }
      .grid { grid-template-columns: 1fr 1fr; }
    }
    @media (max-width: 600px) {
      nav { display: none; }
      .grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>
  <header>
    <div class="container nav">
      <div class="brand" aria-label="Site brand">
        <div class="brand-logo" aria-hidden="true"></div>
        <span>Vimala Sahana W</span>
      </div>
      <nav aria-label="Primary">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
        <button class="btn" id="themeBtn" type="button" aria-pressed="false">Toggle Theme</button>
      </nav>
    </div>
  </header>

  <main>
    <!-- HERO -->
    <section class="hero">
      <div class="container hero-inner">
        <div>
          <span class="chip" aria-label="Availability">
            <span>🟢</span> Open to work & freelance
          </span>
          <h1 class="title">Hi, I'm <span style="color: var(--brand)">Vimala Sahana W</span> — a Developer crafting clean, user‑friendly experiences.</h1>
          <p class="subtitle">I build responsive websites and applications with an eye for performance, accessibility, and delightful details.</p>
          <div class="cta">
            <a class="btn" href="#projects">View Projects</a>
            <a class="btn" href="mailto:vimalasahana28@gmail.com">Email Me</a>
            <a class="btn" href="c:\Users\admin\Downloads\VIMALA SAHANA W (2).pdf" download>Download Resume</a>
          </div>
        </div>
        <div class="avatar" aria-hidden="true"><span></span></div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about">
      <div class="container about-grid">
        <div class="card">
          <h2 class="section-title">About</h2>
          <p class="muted">I'm a software developer who enjoys turning complex problems into simple, beautiful, and intuitive designs. When I'm not coding, you'll find me exploring Figma or sketching UI ideas.</p>
          <ul class="list">
            <li>💼 Current: Frontend Developer</li>
            <li>🎓 Education: B.E in Computer Science and Engineering</li>
            <li>🌍 Location: Chennai, India</li>
          </ul>
        </div>
        <div class="card">
          <h2 class="section-title">Highlights</h2>
          <ul class="list">
            <li>Solved 50+ Leet Code Challenges.</li>
            <li>Built 10+ responsive Websites.</li>
            <li>Actively participated in Collge events and Hackathon.</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- SKILLS -->
    <section id="skills">
      <div class="container">
        <h2 class="section-title">Skills</h2>
        <div class="card">
          <div class="tags">
            <span class="tag">HTML5</span>
            <span class="tag">CSS</span>
            <span class="tag">JavaScript</span>
            <span class="tag">C</span>
            <span class="tag">Python</span>
            <span class="tag">Git</span>
            <span class="tag">SQL</span>
            <span class="tag">Figma</span>
          </div>
        </div>
      </div>
    </section>

    <!-- PROJECTS -->
    <section id="projects">
      <div class="container">
        <h2 class="section-title">Projects</h2>
        <div class="grid">
          <article class="card project">
            
            <h3>Project One</h3>
            <h1>Stock Market Prediction</h1>
            <p> A machine learning project that analyzes historical data and market trends to forecast stock prices in real time. The system combines data visualization and predictive modeling for better market insights.</p>
            <div class="links">
              <a class="btn" href="#" target="_blank" rel="noopener">Live</a>
              <a class="btn" href="#" target="_blank" rel="noopener">Code</a>
            </div>
          </article>
          <article class="card project">
            <h3>Project Two</h3>
            <h1>Train Delay Prediction System</h1>
            <p>A machine learning model that uses historical schedules, weather, and traffic data to predict the likelihood and duration of train delays. It helps improve passenger planning and railway management efficiency.</p>
            <div class="links">
              <a class="btn" href="#" target="_blank" rel="noopener">Live</a>
              <a class="btn" href="#" target="_blank" rel="noopener">Code</a>
            </div>
          </article>
          <article class="card project">
            <h3>Project Three</h3>
            <h1>Heart Disease Prediction</h1>
            <p>A machine learning model that analyzes patient health data to predict the risk of heart attack. It assists in early diagnosis and preventive healthcare decisions.</p>
            <div class="links">
              <a class="btn" href="#" target="_blank" rel="noopener">Live</a>
              <a class="btn" href="#" target="_blank" rel="noopener">Code</a>
            </div>
          </article>
        </div>
      </div>
    </section>
    <!-- CONTACT -->
    <section id="contact">
      <div class="container">
        <h2 class="section-title">Contact</h2>
        <div class="card">
          <p class="muted">Have a project in mind or want to say hi? Send a message:</p>
          <form id="contactForm" action="https://docs.google.com/forms/d/e/1FAIpQLSeKdXGwc505jEMDWuO75tMLv0aEUEz41EzlXSpJHpdBXS1Mvw/viewform?usp=sharing&ouid=111665433450922040771" method="POST">
            <label>
              <span class="muted">Your Name</span>
              <input name="name" required placeholder="Vimala Sahana W" />
            </label>
            <label>
              <span class="muted">Email</span>
              <input type="email" name="email" required placeholder="vimalasahana28@gmail.com" />
              
            </label>
            <label>
              <span class="muted">Message</span>
              <textarea name="message" required placeholder="Type your message..."></textarea>
            </label>
            <label>
              <span class="muted">Location</span>
              <input type="location" name="Location" required placeholder="Chennai" />
              
            </label>
            <button class="btn" type="submit">Send Message</button>
            <p id="formMsg" class="muted" role="status" aria-live="polite"></p>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      © <span id="year"></span> Vimala Sahana W • Built with HTML, CSS & JS
    </div>
  </footer>

  <script>
    // Year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Theme toggle (light/dark)
    const themeBtn = document.getElementById('themeBtn');
    const saved = localStorage.getItem('theme');
    if (saved === 'light') document.documentElement.classList.add('light');
    themeBtn.setAttribute('aria-pressed', saved === 'light' ? 'true' : 'false');

    themeBtn.addEventListener('click', () => {
      const isLight = document.documentElement.classList.toggle('light');
      themeBtn.setAttribute('aria-pressed', isLight ? 'true' : 'false');
      localStorage.setItem('theme', isLight ? 'light' : 'dark');
    });

    
  </script>
</body>
</html>
```


## OUTPUT
<img width="1918" height="959" alt="image" src="https://github.com/user-attachments/assets/9148674e-7a2e-411e-adac-e99b78c45916" />
<img width="1919" height="972" alt="image" src="https://github.com/user-attachments/assets/dfcb0280-d55f-4106-ba04-64b963e18acf" />
<img width="1918" height="972" alt="image" src="https://github.com/user-attachments/assets/95050df1-d333-44d3-9a54-51d1062c3ae9" />




## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
