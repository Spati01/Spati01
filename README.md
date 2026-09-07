<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Subhadip Pati — Java Backend Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,400;0,500;0,600;0,700;1,400&family=Space+Grotesk:wght@500;600;700&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#14161a;
  --bg-panel:#1b1e24;
  --bg-elevated:#22262e;
  --bg-hover:#282c35;
  --border:#33373f;
  --border-soft:#2a2e36;
  --text:#d4d8dc;
  --text-dim:#7d8590;
  --text-faint:#4d525c;
  --amber:#e3a85e;
  --green:#7fb77e;
  --blue:#6fa8dc;
  --red:#e37d7d;
  --purple:#b490d1;
  --mono:'JetBrains Mono', monospace;
  --display:'Space Grotesk', sans-serif;
  --body:'IBM Plex Sans', sans-serif;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
@media (prefers-reduced-motion: reduce){
  html{scroll-behavior:auto;}
  *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important;}
}
body{
  background:var(--bg);
  color:var(--text);
  font-family:var(--body);
  line-height:1.6;
  -webkit-font-smoothing:antialiased;
  position:relative;
}
a{color:inherit;text-decoration:none;}
::selection{background:var(--amber);color:#14161a;}
:focus-visible{outline:2px solid var(--amber);outline-offset:2px;border-radius:2px;}

body::before{
  content:"";position:fixed;inset:0;z-index:-2;pointer-events:none;
  background-image:
    radial-gradient(1.4px 1.4px at 12% 22%, #fff, transparent 60%),
    radial-gradient(1px 1px at 32% 68%, #fff, transparent 60%),
    radial-gradient(1.6px 1.6px at 52% 12%, #fff, transparent 60%),
    radial-gradient(1px 1px at 71% 45%, #fff, transparent 60%),
    radial-gradient(1.2px 1.2px at 88% 78%, #fff, transparent 60%),
    radial-gradient(1px 1px at 6% 88%, #fff, transparent 60%),
    radial-gradient(1.4px 1.4px at 44% 92%, #fff, transparent 60%),
    radial-gradient(1px 1px at 95% 30%, #fff, transparent 60%);
  background-repeat:repeat;
  background-size:340px 340px;
  opacity:.45;
}
body::after{
  content:"";position:fixed;inset:0;z-index:-3;pointer-events:none;
  background:
    radial-gradient(ellipse 60% 40% at 80% 0%, rgba(180,144,209,.10), transparent 60%),
    radial-gradient(ellipse 50% 35% at 10% 100%, rgba(111,168,220,.08), transparent 60%);
}
.container{max-width:960px;margin:0 auto;padding:0 24px;}

/* ---------- Top chrome / tab bar ---------- */
.chrome{
  position:sticky;top:0;z-index:100;
  background:var(--bg-panel);
  border-bottom:1px solid var(--border);
  backdrop-filter:blur(8px);
}
.chrome-titlebar{
  display:flex;align-items:center;gap:8px;
  padding:10px 16px;
  border-bottom:1px solid var(--border-soft);
}
.dot{width:11px;height:11px;border-radius:50%;}
.dot.red{background:#e37d7d;}
.dot.yellow{background:#e3c85e;}
.dot.green{background:#7fb77e;}
.chrome-path{
  margin-left:12px;
  font-family:var(--mono);
  font-size:12.5px;
  color:var(--text-dim);
}
.chrome-path .pkg{color:var(--purple);}
.chrome-path .sep{color:var(--text-faint);}

.tabs{
  display:flex;
  overflow-x:auto;
  scrollbar-width:none;
}
.tabs::-webkit-scrollbar{display:none;}
.tab{
  display:flex;align-items:center;gap:7px;
  padding:11px 18px;
  font-family:var(--mono);
  font-size:13px;
  color:var(--text-dim);
  border-right:1px solid var(--border-soft);
  white-space:nowrap;
  cursor:pointer;
  position:relative;
  transition:color .15s, background .15s;
}
.tab:hover{color:var(--text);background:var(--bg-hover);}
.tab.active{color:var(--text);background:var(--bg);}
.tab.active::after{
  content:"";position:absolute;left:0;right:0;bottom:-1px;height:2px;background:var(--amber);
}
.tab .ext{color:var(--amber);}
.tab .dirty{color:var(--text-faint);font-size:10px;}

/* ---------- Shared editor-pane look ---------- */
.pane{
  display:grid;
  grid-template-columns:56px 1fr;
}
.gutter{
  padding:64px 0 64px;
  text-align:right;
  font-family:var(--mono);
  font-size:12px;
  color:var(--text-faint);
  user-select:none;
  border-right:1px solid var(--border-soft);
}
.gutter span{display:block;padding-right:14px;height:28px;line-height:28px;}
.pane-body{padding:64px 32px 64px 32px;}
section{border-bottom:1px solid var(--border-soft);}
.eyebrow{
  font-family:var(--mono);font-size:12.5px;color:var(--text-dim);
  margin-bottom:10px;letter-spacing:.02em;
}
.eyebrow .kw{color:var(--purple);}
.eyebrow .fn{color:var(--blue);}
.eyebrow .an{color:var(--amber);}
h2.section-title{
  font-family:var(--display);
  font-size:clamp(24px,3.2vw,32px);
  font-weight:600;
  color:#fff;
  margin-bottom:28px;
}

/* ---------- Hero ---------- */
.hero .pane-body{padding-top:56px;}
.code-line{
  font-family:var(--mono);
  font-size:clamp(13px,1.9vw,15.5px);
  white-space:pre-wrap;
}
.kw{color:var(--purple);}
.tp{color:var(--blue);}
.str{color:var(--green);}
.an{color:var(--amber);}
.cm{color:var(--text-faint);font-style:italic;}
.fn{color:var(--blue);}
.pn{color:var(--text-dim);}

.hero-name{
  font-family:var(--display);
  font-weight:700;
  font-size:clamp(34px,6vw,58px);
  color:#fff;
  margin:22px 0 6px;
  line-height:1.05;
}
.hero-role{
  font-family:var(--mono);
  font-size:clamp(14px,2vw,17px);
  color:var(--amber);
  margin-bottom:22px;
}
.hero-desc{
  max-width:560px;
  color:var(--text-dim);
  font-size:15.5px;
  margin-bottom:32px;
}
.hero-actions{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:44px;}
.btn{
  font-family:var(--mono);font-size:13px;
  padding:11px 20px;border-radius:6px;
  border:1px solid var(--border);
  cursor:pointer;
  transition:transform .15s, border-color .15s, background .15s;
  display:inline-flex;align-items:center;gap:8px;
}
.btn-primary{background:var(--amber);color:#14161a;border-color:var(--amber);font-weight:600;}
.btn-primary:hover{transform:translateY(-1px);filter:brightness(1.08);}
.btn-ghost{color:var(--text);background:transparent;}
.btn-ghost:hover{border-color:var(--text-dim);background:var(--bg-hover);}

/* console output block */
.console{
  background:var(--bg-elevated);
  border:1px solid var(--border);
  border-radius:8px;
  overflow:hidden;
  max-width:640px;
}
.console-head{
  display:flex;align-items:center;gap:8px;
  padding:8px 14px;
  border-bottom:1px solid var(--border-soft);
  font-family:var(--mono);font-size:11.5px;color:var(--text-faint);
}
.console-body{padding:16px 18px;font-family:var(--mono);font-size:13px;}
.console-body .out-line{margin-bottom:6px;}
.console-body .prompt{color:var(--green);}
.console-body .val{color:var(--text);}
.console-body .lbl{color:var(--text-dim);}
.blink{display:inline-block;width:8px;height:15px;background:var(--amber);vertical-align:middle;animation:blink 1.1s steps(1) infinite;margin-left:2px;}
@keyframes blink{50%{opacity:0;}}

/* ---------- About ---------- */
.field-row{
  display:grid;grid-template-columns:150px 1fr;
  gap:4px 18px;
  padding:10px 0;
  border-bottom:1px dashed var(--border-soft);
  font-size:14.5px;
}
.field-row:last-child{border-bottom:none;}
.field-key{font-family:var(--mono);color:var(--blue);font-size:13px;}
.field-val{color:var(--text-dim);}
.about-lede{
  max-width:600px;
  color:var(--text);
  font-size:16px;
  margin-bottom:30px;
}

/* ---------- Skills as dependencies ---------- */
.dep-file{
  background:var(--bg-elevated);
  border:1px solid var(--border);
  border-radius:8px;
  overflow:hidden;
}
.dep-file-head{
  padding:9px 16px;font-family:var(--mono);font-size:12px;color:var(--text-faint);
  border-bottom:1px solid var(--border-soft);
}
.dep-group{padding:18px 20px 6px;}
.dep-group-name{
  font-family:var(--mono);font-size:12px;color:var(--text-faint);
  margin-bottom:10px;text-transform:uppercase;letter-spacing:.06em;
}
.dep-list{display:flex;flex-wrap:wrap;gap:9px;margin-bottom:18px;}
.dep{
  font-family:var(--mono);font-size:12.5px;
  padding:6px 11px;border-radius:5px;
  background:var(--bg-panel);border:1px solid var(--border);
  display:flex;align-items:center;gap:8px;
  transition:border-color .15s, transform .15s;
}
.dep:hover{border-color:var(--amber);transform:translateY(-1px);}
.dep img{width:14px;height:14px;display:block;filter:saturate(1.1);}
.dep .ver{color:var(--green);}
.dep .name{color:var(--text);}

/* ---------- Projects as file explorer ---------- */
.proj-list{display:flex;flex-direction:column;gap:14px;}
.proj{
  background:var(--bg-elevated);
  border:1px solid var(--border);
  border-radius:8px;
  padding:20px 22px;
  transition:border-color .15s;
}
.proj:hover{border-color:var(--text-faint);}
.proj-head{display:flex;align-items:baseline;justify-content:space-between;gap:12px;flex-wrap:wrap;margin-bottom:8px;}
.proj-name{font-family:var(--mono);font-size:15.5px;color:#fff;font-weight:600;}
.proj-name .ext{color:var(--amber);}
.proj-stat{font-family:var(--mono);font-size:12px;white-space:nowrap;color:var(--green);}
.proj-desc{color:var(--text-dim);font-size:14.5px;margin-bottom:14px;max-width:640px;}
.proj-tags{display:flex;flex-wrap:wrap;gap:7px;margin-bottom:14px;}
.tag{
  font-family:var(--mono);font-size:11.5px;color:var(--blue);
  border:1px solid var(--border);padding:3px 9px;border-radius:4px;
}
.proj-links{display:flex;gap:16px;}
.proj-links a{
  font-family:var(--mono);font-size:12.5px;color:var(--text-dim);
  border-bottom:1px solid transparent;
}
.proj-links a:hover{color:var(--amber);border-color:var(--amber);}

/* ---------- Journey as git log ---------- */
.commit{
  display:grid;grid-template-columns:20px 1fr;gap:14px;
  padding-bottom:28px;position:relative;
}
.commit:last-child{padding-bottom:0;}
.commit-rail{position:relative;display:flex;justify-content:center;}
.commit-rail::before{
  content:"";position:absolute;top:16px;bottom:-28px;width:1px;background:var(--border);
}
.commit:last-child .commit-rail::before{display:none;}
.commit-dot{
  width:9px;height:9px;border-radius:50%;background:var(--amber);
  margin-top:5px;flex-shrink:0;box-shadow:0 0 0 3px var(--bg);
}
.commit-hash{font-family:var(--mono);font-size:12px;color:var(--text-faint);}
.commit-msg{font-family:var(--display);font-weight:600;font-size:16.5px;color:#fff;margin:2px 0 4px;}
.commit-meta{font-family:var(--mono);font-size:12px;color:var(--text-dim);margin-bottom:8px;}
.commit-meta .branch{color:var(--purple);}
.commit-body{color:var(--text-dim);font-size:14.5px;max-width:600px;}

/* ---------- Contact / terminal ---------- */
.term{
  background:var(--bg-elevated);border:1px solid var(--border);border-radius:8px;overflow:hidden;
}
.term-head{
  padding:9px 16px;font-family:var(--mono);font-size:12px;color:var(--text-faint);
  border-bottom:1px solid var(--border-soft);display:flex;align-items:center;gap:8px;
}
.term-body{padding:22px;font-family:var(--mono);font-size:14px;}
.term-line{margin-bottom:12px;display:flex;gap:10px;flex-wrap:wrap;}
.term-line .p1{color:var(--green);}
.term-line .p2{color:var(--blue);}
.term-line .cmd{color:var(--text);}
.contact-links{display:flex;flex-direction:column;gap:10px;margin-top:6px;}
.contact-links a{
  display:flex;align-items:center;gap:10px;
  font-size:14.5px;color:var(--text);
  padding:9px 0;
  border-bottom:1px solid var(--border-soft);
  transition:color .15s, padding-left .15s;
}
.contact-links a:hover{color:var(--amber);padding-left:6px;}
.contact-links a .arrow{color:var(--text-faint);font-family:var(--mono);}

/* ---------- Footer status bar ---------- */
.statusbar{
  display:flex;justify-content:space-between;flex-wrap:wrap;gap:8px;
  padding:10px 24px;
  background:var(--bg-panel);
  border-top:1px solid var(--border);
  font-family:var(--mono);font-size:11.5px;color:var(--text-faint);
}
.statusbar .ok{color:var(--green);}
.statusbar span{display:inline-flex;align-items:center;gap:6px;}

/* ---------- responsive ---------- */
@media (max-width:720px){
  .pane{grid-template-columns:32px 1fr;}
  .gutter{padding:40px 0;}
  .gutter span{padding-right:8px;font-size:10.5px;}
  .pane-body{padding:40px 18px;}
  .field-row{grid-template-columns:110px 1fr;}
  .hero .pane-body{padding-top:36px;}
}
</style>
</head>
<body>

<header class="chrome">
  <div class="chrome-titlebar">
    <span class="dot red"></span><span class="dot yellow"></span><span class="dot green"></span>
    <span class="chrome-path"><span class="pkg">com.subhadippati</span><span class="sep">.</span>portfolio<span class="sep">.</span>Main</span>
  </div>
  <nav class="tabs" id="tabs">
    <a class="tab active" data-target="home" href="#home">Home<span class="ext">.java</span></a>
    <a class="tab" data-target="about" href="#about">About<span class="ext">.java</span></a>
    <a class="tab" data-target="skills" href="#skills">build<span class="ext">.gradle</span></a>
    <a class="tab" data-target="projects" href="#projects">Projects<span class="ext">.java</span></a>
    <a class="tab" data-target="journey" href="#journey">git<span class="ext">.log</span></a>
    <a class="tab" data-target="contact" href="#contact">Contact<span class="ext">.java</span><span class="dirty">●</span></a>
  </nav>
</header>

<main class="container">

  <!-- HOME / HERO -->
  <section id="home" class="pane hero">
    <div class="gutter"><span>1</span><span>2</span><span>3</span><span>4</span><span>5</span><span>6</span><span>7</span><span>8</span><span>9</span></div>
    <div class="pane-body">
      <div class="code-line"><span class="an">@Portfolio</span></div>
      <div class="code-line"><span class="kw">public class</span> <span class="tp">SubhadipPati</span> <span class="kw">implements</span> <span class="tp">BackendDeveloper</span> {</div>
      <h1 class="hero-name">Subhadip Pati</h1>
      <div class="hero-role">// Java Backend Developer — Spring Boot · REST APIs · SQL · DSA</div>
      <p class="hero-desc">I build backend systems with Java and Spring Boot — clean REST APIs, sane data models, and code that's easy to pick back up months later. 1,500+ DSA problems deep, and I still enjoy finding a cleaner solution to one I've already solved.</p>
      <div class="hero-actions">
        <a href="#projects" class="btn btn-primary">View Projects →</a>
        <a href="#contact" class="btn btn-ghost">Get in touch</a>
        <a href="https://drive.google.com/file/d/1j1xcntlsYsDDaS58-VwqCgOa3dG_c4r_/view?usp=sharing" target="_blank" class="btn btn-ghost">↓ Resume.pdf</a>
      </div>

      <div class="console">
        <div class="console-head">Console — run: Main.main()</div>
        <div class="console-body">
          <div class="out-line"><span class="prompt">&gt;</span> <span class="lbl">Compiling...</span> <span class="val">BUILD SUCCESSFUL</span></div>
          <div class="out-line"><span class="lbl">Focus:</span> <span class="val">Java · Spring Boot · Spring Security · JPA/Hibernate</span></div>
          <div class="out-line"><span class="lbl">DSA solved:</span> <span class="val">1,500+ problems on LeetCode</span></div>
          <div class="out-line"><span class="lbl">Currently:</span> <span class="val">Learning Microservices, Docker, AWS, System Design</span><span class="blink"></span></div>
        </div>
      </div>
      <div class="code-line" style="margin-top:28px;">}</div>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about" class="pane">
    <div class="gutter"><span>1</span><span>2</span><span>3</span><span>4</span><span>5</span><span>6</span><span>7</span></div>
    <div class="pane-body">
      <div class="eyebrow"><span class="kw">class</span> <span class="fn">About</span> <span class="pn">{</span></div>
      <h2 class="section-title">A bit of context</h2>
      <p class="about-lede">I got into backend development through DSA — the habit of hunting for the cleanest solution to a problem carried straight into how I build APIs. These days I care about writing Spring Boot services that are secure by default, well-structured, and easy to extend later.</p>
      <div>
        <div class="field-row"><div class="field-key">focus</div><div class="field-val">Java, Spring Boot, Spring Security, JPA/Hibernate, REST APIs</div></div>
        <div class="field-row"><div class="field-key">learning</div><div class="field-val">Microservices, Docker, AWS, System Design, AI + Java</div></div>
        <div class="field-row"><div class="field-key">collaborate_on</div><div class="field-val">Open-source Java/Spring Boot backends, scalable REST APIs, dev tools</div></div>
        <div class="field-row"><div class="field-key">need_help_with</div><div class="field-val">Microservices, Docker, AWS, system design in production</div></div>
        <div class="field-row"><div class="field-key">ask_me_about</div><div class="field-val">Java, Spring Boot, REST APIs, SQL, DSA, OOP, Spring Security, JWT</div></div>
        <div class="field-row"><div class="field-key">fun_fact</div><div class="field-val">1,500+ DSA problems solved, still hunting for the cleaner solution 🚀</div></div>
      </div>
    </div>
  </section>

  <!-- SKILLS as dependencies -->
  <section id="skills" class="pane">
    <div class="gutter"><span>1</span><span>2</span><span>3</span><span>4</span><span>5</span><span>6</span></div>
    <div class="pane-body">
      <div class="eyebrow"><span class="fn">dependencies</span> <span class="pn">{</span></div>
      <h2 class="section-title">What I build with</h2>
      <div class="dep-file">
        <div class="dep-file-head">build.gradle.kts — implementation</div>

        <div class="dep-group">
          <div class="dep-group-name">Languages</div>
          <div class="dep-list">
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt=""><span class="name">java</span><span class="ver">core</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original.svg" alt=""><span class="name">sql</span><span class="ver">core</span></span>
          </div>
        </div>

        <div class="dep-group">
          <div class="dep-group-name">Frameworks</div>
          <div class="dep-list">
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original.svg" alt=""><span class="name">spring-boot</span><span class="ver">3.x</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/spring/spring-original.svg" alt=""><span class="name">spring-security</span><span class="ver">6.x</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/hibernate/hibernate-original.svg" alt=""><span class="name">hibernate-jpa</span><span class="ver">6.x</span></span>
          </div>
        </div>

        <div class="dep-group">
          <div class="dep-group-name">Databases</div>
          <div class="dep-list">
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original.svg" alt=""><span class="name">mysql</span><span class="ver">stable</span></span>
            <span class="dep"><img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg" alt=""><span class="name">sql-server</span><span class="ver">stable</span></span>
          </div>
        </div>

        <div class="dep-group">
          <div class="dep-group-name">Tools</div>
          <div class="dep-list">
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" alt=""><span class="name">git</span><span class="ver">stable</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/github/github-original.svg" alt=""><span class="name">github</span><span class="ver">stable</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postman/postman-original.svg" alt=""><span class="name">postman</span><span class="ver">stable</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt=""><span class="name">linux</span><span class="ver">stable</span></span>
          </div>
        </div>

        <div class="dep-group">
          <div class="dep-group-name">Exploring</div>
          <div class="dep-list">
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original.svg" alt=""><span class="name">docker</span><span class="ver">learning</span></span>
            <span class="dep"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg" alt=""><span class="name">aws</span><span class="ver">learning</span></span>
            <span class="dep"><span class="name">microservices</span><span class="ver">learning</span></span>
            <span class="dep"><span class="name">system-design</span><span class="ver">learning</span></span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS -->
  <section id="projects" class="pane">
    <div class="gutter"><span>1</span><span>2</span><span>3</span><span>4</span><span>5</span><span>6</span></div>
    <div class="pane-body">
      <div class="eyebrow"><span class="kw">package</span> <span class="pn">projects;</span></div>
      <h2 class="section-title">Selected work</h2>

      <div class="proj-list">
        <div class="proj">
          <div class="proj-head">
            <div class="proj-name">Dynamic_PDF_Generation<span class="ext">.java</span></div>
            <div class="proj-stat">● active</div>
          </div>
          <p class="proj-desc">A Spring Boot REST API that generates PDF invoices on the fly using iText and a Java template engine — send structured JSON in, get a formatted PDF back.</p>
          <div class="proj-tags"><span class="tag">Spring Boot</span><span class="tag">Java</span><span class="tag">iText</span><span class="tag">REST API</span></div>
          <div class="proj-links"><a href="https://github.com/Spati01/Dynamic_PDF_Generation" target="_blank">Source →</a></div>
        </div>

        <div class="proj">
          <div class="proj-head">
            <div class="proj-name">Portfolio-Website<span class="ext">.html</span></div>
            <div class="proj-stat">🌐 live</div>
          </div>
          <p class="proj-desc">My personal portfolio site — built to showcase projects, skills, and experience in one place, deployed on GitHub Pages.</p>
          <div class="proj-tags"><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">JavaScript</span><span class="tag">GitHub Pages</span></div>
          <div class="proj-links"><a href="https://spati01.github.io/Portfolio-Website/" target="_blank">Live site →</a><a href="https://github.com/Spati01/Portfolio-Website" target="_blank">Source →</a></div>
        </div>

        <div class="proj">
          <div class="proj-head">
            <div class="proj-name">rag-chat-assistant<span class="ext">.md</span></div>
            <div class="proj-stat">✍️ article</div>
          </div>
          <p class="proj-desc">Wrote up how to build a production-ready RAG chat assistant using Elasticsearch and Spring Boot — from indexing to retrieval to the chat endpoint.</p>
          <div class="proj-tags"><span class="tag">Elasticsearch</span><span class="tag">Spring Boot</span><span class="tag">RAG</span></div>
          <div class="proj-links"><a href="https://medium.com/@subhadippati30/building-a-production-ready-rag-chat-assistant-with-elasticsearch-spring-boot-d8d9d2fd059b" target="_blank">Read on Medium →</a></div>
        </div>

        <div class="proj">
          <div class="proj-head">
            <div class="proj-name">dsa-practice<span class="ext">.log</span></div>
            <div class="proj-stat">🧩 1,500+ solved</div>
          </div>
          <p class="proj-desc">Ongoing problem-solving practice across arrays, trees, graphs, and dynamic programming — the habit that shaped how I approach backend design too.</p>
          <div class="proj-tags"><span class="tag">Data Structures</span><span class="tag">Algorithms</span><span class="tag">LeetCode</span></div>
          <div class="proj-links"><a href="https://leetcode.com/u/subhadip01/" target="_blank">LeetCode profile →</a></div>
        </div>
      </div>
    </div>
  </section>

  <!-- JOURNEY as git log -->
  <section id="journey" class="pane">
    <div class="gutter"><span>1</span><span>2</span><span>3</span><span>4</span><span>5</span><span>6</span></div>
    <div class="pane-body">
      <div class="eyebrow"><span class="fn">git log</span> <span class="pn">--author="subhadip" --reverse</span></div>
      <h2 class="section-title">The journey so far</h2>

      <div class="commits">
        <div class="commit">
          <div class="commit-rail"><div class="commit-dot"></div></div>
          <div>
            <div class="commit-hash">commit a1c9e02 <span class="branch">(HEAD → main)</span></div>
            <div class="commit-msg">Solved 1,500+ DSA problems</div>
            <div class="commit-meta">LeetCode · ongoing</div>
            <div class="commit-body">Still hunting for cleaner solutions to problems I've already solved — the habit that shapes how I think about code now.</div>
          </div>
        </div>
        <div class="commit">
          <div class="commit-rail"><div class="commit-dot"></div></div>
          <div>
            <div class="commit-hash">commit 7f3b410</div>
            <div class="commit-msg">Published: RAG chat assistant on Medium</div>
            <div class="commit-meta">Writing · Elasticsearch + Spring Boot</div>
            <div class="commit-body">Wrote a deep-dive on building a production-ready RAG chat assistant, from indexing to the chat endpoint.</div>
          </div>
        </div>
        <div class="commit">
          <div class="commit-rail"><div class="commit-dot"></div></div>
          <div>
            <div class="commit-hash">commit 4d2a891</div>
            <div class="commit-msg">Shipped Dynamic_PDF_Generation</div>
            <div class="commit-meta">Project · Spring Boot + iText</div>
            <div class="commit-body">Built a REST API that generates PDF invoices on the fly from structured JSON input.</div>
          </div>
        </div>
        <div class="commit">
          <div class="commit-rail"><div class="commit-dot"></div></div>
          <div>
            <div class="commit-hash">commit 0e75b6c</div>
            <div class="commit-msg">Deployed personal portfolio site</div>
            <div class="commit-meta">Project · GitHub Pages</div>
            <div class="commit-body">Put together a portfolio to showcase projects, skills, and how to get in touch.</div>
          </div>
        </div>
        <div class="commit">
          <div class="commit-rail"><div class="commit-dot"></div></div>
          <div>
            <div class="commit-hash">commit 1000000</div>
            <div class="commit-msg">Initial commit</div>
            <div class="commit-meta">Started the Java + Spring Boot journey</div>
            <div class="commit-body">Began learning backend development — Java fundamentals, then Spring Boot, then everything that followed.</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="pane" style="border-bottom:none;">
    <div class="gutter"><span>1</span><span>2</span><span>3</span><span>4</span><span>5</span></div>
    <div class="pane-body">
      <div class="eyebrow"><span class="kw">public static void</span> <span class="fn">main</span><span class="pn">(String[] args)</span> <span class="pn">{</span></div>
      <h2 class="section-title">Let's talk</h2>

      <div class="term">
        <div class="term-head"><span class="dot red"></span><span class="dot yellow"></span><span class="dot green"></span>&nbsp;&nbsp;zsh — contact</div>
        <div class="term-body">
          <div class="term-line"><span class="p1">subhadip@dev</span><span class="p2">~/portfolio</span><span class="cmd">$ cat reach_me.txt</span></div>
          <div class="contact-links">
            <a href="mailto:subhadippati30@gmail.com"><span class="arrow">→</span> subhadippati30@gmail.com</a>
            <a href="https://linkedin.com/in/subhadippati01" target="_blank"><span class="arrow">→</span> linkedin.com/in/subhadippati01</a>
            <a href="https://leetcode.com/u/subhadip01/" target="_blank"><span class="arrow">→</span> leetcode.com/u/subhadip01</a>
            <a href="https://spati01.github.io/Portfolio-Website/" target="_blank"><span class="arrow">→</span> spati01.github.io/Portfolio-Website</a>
            <a href="https://medium.com/@subhadippati30" target="_blank"><span class="arrow">→</span> medium.com/@subhadippati30</a>
          </div>
        </div>
      </div>
    </div>
  </section>

</main>

<footer class="statusbar">
  <span>⎇ main</span>
  <span>UTF-8</span>
  <span>Java 21</span>
  <span class="ok">● BUILD SUCCESS</span>
  <span>© 2026 Subhadip Pati</span>
</footer>

<script>
  const tabs = document.querySelectorAll('.tab');
  const sections = [...tabs].map(t => document.getElementById(t.dataset.target));

  tabs.forEach(tab => {
    tab.addEventListener('click', e => {
      tabs.forEach(t => t.classList.remove('active'));
      tab.classList.add('active');
    });
  });

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        const id = entry.target.id;
        tabs.forEach(t => t.classList.toggle('active', t.dataset.target === id));
      }
    });
  }, { rootMargin: '-40% 0px -50% 0px', threshold: 0 });

  sections.forEach(s => s && observer.observe(s));
</script>

</body>
</html>
