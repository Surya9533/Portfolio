# Ex01 Portfolio
## Date:

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
  <title>Surya | B.Tech CSE Portfolio</title>
  <meta name="description" content="Portfolio of Surya, B.Tech in Computer Science & Engineering (CSE). Projects, skills, and contact." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Poppins:wght@600;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg: #0b0f14;
      --surface: #121823;
      --card: #0f1520;
      --text: #e6edf3;
      --muted: #a6b2bd;
      --brand: #6ea8fe;   /* soft blue */
      --accent: #9bdbff;  /* light accent */
      --ok: #54d1b6;
      --warn: #f2c94c;
      --shadow: 0 10px 30px rgba(0,0,0,.3);
      --radius: 18px;
    }
    * {box-sizing: border-box}
    html {scroll-behavior: smooth}
    body{
      margin:0; background: radial-gradient(1000px 600px at 100% -10%, rgba(110,168,254,.12), rgba(0,0,0,0)) , radial-gradient(900px 500px at -10% 10%, rgba(155,219,255,.08), rgba(0,0,0,0)), var(--bg);
      color: var(--text); font: 16px/1.6 Inter, system-ui, -apple-system, Segoe UI, Roboto, Arial, "Apple Color Emoji","Segoe UI Emoji";
    }
    a {color: var(--accent); text-decoration: none}
    a:hover {text-decoration: underline}

    /* Container */
    .wrap{max-width:1100px; margin:0 auto; padding:0 20px}

    /* Header */
    header{
      position: sticky; top:0; z-index: 50;
      background: rgba(11,15,20,.7); backdrop-filter: blur(8px);
      border-bottom: 1px solid rgba(255,255,255,.06);
    }
    .nav{display:flex; align-items:center; justify-content:space-between; height:64px}
    .brand{display:flex; align-items:center; gap:12px; font-weight:700}
    .brand .logo{width:36px; height:36px; border-radius:10px; display:grid; place-items:center; background:linear-gradient(135deg, var(--brand), #7bd0ff); color:#0b0f14; font-weight:800; box-shadow: var(--shadow)}
    .nav a{color:var(--text)}
    .menu{display:flex; gap:20px}
    .menu a{opacity:.85}
    .menu a:hover{opacity:1}
    .cta{
      padding:10px 14px; border-radius:12px; background:linear-gradient(135deg, var(--brand), var(--accent)); color:#0b0f14; font-weight:700; box-shadow: var(--shadow);
    }

    /* Hero */
    .hero{padding:80px 0 40px}
    .hero-grid{display:grid; grid-template-columns: 1.1fr .9fr; gap:40px; align-items:center}
    h1{font-family:Poppins, Inter, system-ui; font-weight:800; line-height:1.1; letter-spacing:.2px; margin:0 0 14px}
    .title{font-size: clamp(32px, 4.5vw, 54px)}
    .subtitle{color:var(--muted); font-size: clamp(14px, 1.6vw, 18px)}
    .badges{display:flex; gap:10px; flex-wrap:wrap; margin:18px 0 28px}
    .badge{padding:8px 12px; border:1px solid rgba(255,255,255,.08); border-radius:999px; color: var(--muted); background: rgba(255,255,255,.02)}
    .hero .actions{display:flex; gap:12px; flex-wrap:wrap}
    .btn{
      padding:12px 16px; border-radius:14px; border:1px solid rgba(255,255,255,.08); background:var(--surface); color:var(--text); font-weight:600; box-shadow: var(--shadow)
    }
    .btn.primary{background:linear-gradient(135deg, var(--brand), var(--accent)); color:#0b0f14; border-color: transparent}
    
    .portrait{
      width:100%; aspect-ratio: 1/1; border-radius: var(--radius);
      background: linear-gradient(135deg, rgba(110,168,254,.2), rgba(155,219,255,.08));
      border: 1px solid rgba(255,255,255,.08);
      display:grid; place-items:center; color:var(--muted); font-weight:600
    }

    /* Section */
    section{padding:60px 0}
    .section-title{font-family:Poppins, Inter; font-weight:800; font-size: clamp(22px, 2.6vw, 30px); margin:0 0 16px}
    .section-sub{color:var(--muted); margin:0 0 24px}

    /* About */
    .about{display:grid; grid-template-columns: .9fr 1.1fr; gap:28px}
    .about .card{background:var(--card); border:1px solid rgba(255,255,255,.06); border-radius: var(--radius); padding:22px}

    /* Skills */
    .skills-grid{display:grid; grid-template-columns: repeat(auto-fit, minmax(220px,1fr)); gap:16px}
    .skill{background:var(--card); border:1px solid rgba(255,255,255,.06); border-radius: var(--radius); padding:18px}
    .skill h4{margin:0 0 8px}
    .tags{display:flex; flex-wrap:wrap; gap:8px}
    .tag{padding:6px 10px; background:rgba(255,255,255,.04); border:1px solid rgba(255,255,255,.06); border-radius:999px; color:var(--muted); font-size:14px}

    /* Contact */
    .contact-card{display:grid; gap:16px; background:var(--card); border:1px solid rgba(255,255,255,.06); border-radius: var(--radius); padding:22px}
    .contact-row{display:grid; grid-template-columns: 1fr 2fr; gap:12px}
    .contact-row strong{color:var(--muted)}
    form{display:grid; gap:12px}
    input, textarea{width:100%; padding:12px 14px; border-radius:12px; border:1px solid rgba(255,255,255,.08); background: #0d1320; color:var(--text)}
    textarea{min-height:120px; resize: vertical}

    /* Footer */
    footer{padding:26px 0; color:var(--muted); border-top:1px solid rgba(255,255,255,.08)}

    /* Responsive */
    @media (max-width: 900px){
      .hero-grid, .about{grid-template-columns: 1fr}
    }
  </style>
</head>
<body>
  <header>
    <div class="wrap nav">
      <div class="brand">
        <div class="logo">S</div>
        <span>Surya • B.Tech CSE</span>
      </div>
      <nav class="menu">
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#contact">Contact</a>
        <a class="cta" href="#contact">Hire Me</a>
      </nav>
    </div>
  </header>

  <main>
    <!-- Hero -->
    <section class="hero">
      <div class="wrap hero-grid">
        <div>
          <h1 class="title">Hi, I'm Surya<span style="opacity:.6"> —</span> a B.Tech CSE student crafting clean, useful software.</h1>
          <p class="subtitle">I love building web apps, exploring algorithms, and turning ideas into interactive experiences. Here's a snapshot of my work and what I bring to a team.</p>
          <div class="badges">
            <span class="badge">B.Tech • Computer Science & Engineering</span>
            <span class="badge">Open to Internships</span>
            <span class="badge">Based in India</span>
          </div>
          <div class="actions">
            <a class="btn primary" href="#projects">See Projects</a>
            <a class="btn" href="#contact">Get in Touch</a>
            <a class="btn" href="#resume" title="Add your resume link">Download Résumé</a>
          </div>
        </div>
        <div class="portrait" aria-label="Surya portrait placeholder">
          <div>
            <img src="suriya (1) (1).jpg" alt="">
          </div>
        </div>
      </div>
    </section>

    <!-- About -->
    <section id="about">
      <div class="wrap">
        <h2 class="section-title">About</h2>
        <p class="section-sub">I'm Surya, a B.Tech student in Computer Science & Engineering (CSE). I enjoy learning by building—especially front‑end interfaces, small utilities, and data‑driven features.</p>
        <div class="about">
          <div class="card">
            <h3 style="margin-top:0">Quick Facts</h3>
            <ul>
              <li>Program: <strong>B.Tech — Computer Science & Engineering</strong></li>
              <li>Interests: Web Development, Data Structures, UI/UX</li>
              <li>Currently exploring: React, Node.js, and basic AI/ML workflows</li>
              <li>Looking for: Internship opportunities and collaboration</li>
            </ul>
          </div>
          <div class="card">
            <h3 style="margin-top:0">What I Value</h3>
            <p>Readable code, thoughtful UX, and learning fast. I try to keep things simple, ship incrementally, and document as I go.</p>
            <p>When I'm not coding, I'm usually sketching UI ideas, reading tech blogs, or playing around with new tools.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills">
      <div class="wrap">
        <h2 class="section-title">Skills</h2>
        <p class="section-sub">A snapshot of tools and technologies I've worked with so far.</p>
        <div class="skills-grid">
          <div class="skill">
            <h4>Languages</h4>
            <div class="tags">
              <span class="tag">C</span>
              <span class="tag">C++</span>
              
              <span class="tag">Python</span>
            </div>
          </div>
          <div class="skill">
            <h4>Web</h4>
            <div class="tags">
              <span class="tag">HTML</span>
              <span class="tag">CSS</span>
              <span class="tag">React (basics)</span>
              <span class="tag">Node.js (basics)</span>
              <span class="tag">REST APIs</span>
            </div>
          </div>
          
          <div class="skill">
            <h4>Tools</h4>
            <div class="tags">
              <span class="tag">Git & GitHub</span>
              <span class="tag">VS Code</span>
              <span class="tag">Figma</span>
              <span class="tag">Postman</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    
      </div>
    </section>

    <!-- Contact -->
    <section id="contact">
      <div class="wrap">
        <h2 class="section-title">Contact</h2>
        <p class="section-sub">Want to collaborate or have an opportunity? Send a message—I'll reply soon.</p>
        <div class="contact-card">
          <div class="contact-row"><strong>Name</strong><span>Surya</span></div>
          <div class="contact-row"><strong>Program</strong><span>B.Tech — Computer Science & Engineering</span></div>
          <div class="contact-row"><strong>Email</strong><span><a href="mailto:timeline.surya15@gmail.com">timeline.surya15@gmail.com</a></span></div>

          <form onsubmit="event.preventDefault(); alert('Thanks! Replace this with a form service.');">
            <label>
              <span style="display:block; margin-bottom:6px">Your Name</span>
              <input required type="text" placeholder="Enter your name">
            </label>
            <label>
              <span style="display:block; margin-bottom:6px">Your Email</span>
              <input required type="email" placeholder="name@example.com">
            </label>
            <label>
              <span style="display:block; margin-bottom:6px">Message</span>
              <textarea required placeholder="Write your message..."></textarea>
            </label>
            <button class="btn primary" type="submit">Send Message</button>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="wrap">© <span id="y"></span> Surya • B.Tech CSE • Built with HTML & CSS</div>
  </footer>

  <script>
    // Set current year
    document.getElementById('y').textContent = new Date().getFullYear();
  </script>
</body>
</html>
```


## OUTPUT
<img width="1886" height="972" alt="image" src="https://github.com/user-attachments/assets/89d926b7-9e6f-464c-be37-fdf403afd249" />
<img width="1895" height="787" alt="image" src="https://github.com/user-attachments/assets/59062f16-c020-4c57-b65a-bf1e7db95c03" />
<img width="1895" height="937" alt="image" src="https://github.com/user-attachments/assets/295e2421-b9a9-4f3e-ae8a-dec6e02fec06" />




## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
