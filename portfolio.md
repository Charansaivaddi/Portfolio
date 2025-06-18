---
layout: default
title: Charan Sai Vaddi
---

<style>
:root {
  --bg: #0f0f0f;
  --fg: #eaeaea;
  --accent: #4fc3f7;
  --font-main: 'Fira Code', monospace;
  --scroll-speed: 0.3;
}
body[data-theme="light"] {
  --bg: #f5f5f5;
  --fg: #1c1c1c;
  --accent: #0077cc;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  scroll-behavior: smooth;
}
body {
  background-color: var(--bg);
  color: var(--fg);
  font-family: var(--font-main);
  overflow-x: hidden;
}
nav {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 100;
}
nav a {
  margin: 0 10px;
  color: var(--accent);
  text-decoration: none;
  font-weight: bold;
  transition: color 0.3s;
}
nav a:hover {
  color: var(--fg);
}
.toggle-btn {
  cursor: pointer;
  background: none;
  border: 1px solid var(--accent);
  color: var(--accent);
  padding: 5px 10px;
  margin-left: 20px;
  font-family: var(--font-main);
}
header {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  background: linear-gradient(to bottom, var(--bg), transparent), url('https://images.unsplash.com/photo-1526378722459-8f3f3b7b1591?auto=format&fit=crop&w=1600&q=80');
  background-size: cover;
  background-attachment: fixed;
  background-position: center;
}
header h1 {
  font-size: 3rem;
  color: var(--accent);
  animation: blink 1s steps(2, start) infinite;
}
header p {
  margin-top: 1rem;
  max-width: 600px;
  font-style: italic;
}
@keyframes blink {
  0%   { opacity: 1; }
  50%  { opacity: 0.2; }
  100% { opacity: 1; }
}
section {
  padding: 6rem 2rem;
  max-width: 900px;
  margin: auto;
}
h2 {
  margin-bottom: 1rem;
  border-left: 5px solid var(--accent);
  padding-left: 1rem;
  font-size: 1.8rem;
}
.project {
  background: rgba(0, 0, 0, 0.1);
  border-left: 3px solid var(--accent);
  padding: 1rem;
  margin-bottom: 1rem;
}
footer {
  text-align: center;
  padding: 2rem;
  font-size: 0.9rem;
  opacity: 0.5;
}
a {
  color: var(--accent);
}
.parallax {
  transform: translateY(var(--scroll));
  transition: transform 0.3s ease;
}
@media (max-width: 600px) {
  header h1 {
    font-size: 2rem;
  }
  nav {
    top: 10px;
    right: 10px;
  }
}
</style>

<nav>
  <a href="#about">About</a>
  <a href="#projects">Projects</a>
  <a href="#contact">Contact</a>
  <button class="toggle-btn" onclick="toggleTheme()">Toggle Theme</button>
</nav>

<header class="parallax">
  <h1>$ whoami</h1>
  <p>“Blending algorithms with intuition. Exploring meaning through code.”</p>
</header>

## About Me {#about}

I’m **Charan** — a builder and thinker.  
I develop systems that combine reinforcement learning, symbolic reasoning, and math.  
With curiosity as my compass, I prototype, experiment, and refine ideas that blend structure and abstraction.

---

## Projects {#projects}

### 🧠 RL Math Solver
Chain-of-thought RL agents solving symbolic math expressions with learned strategies. Evaluation across word problems and formal systems.

### 🌍 Predator-Prey Sim
Visual IBM Data Simulation with metric logging for agent behavior in adaptive ecological environments.

### 🌀 Diffusion Noise Classifier
Classifier over ejected noise during reverse diffusion steps. Used to identify failed generation samples proactively.

---

## Contact {#contact}

- **Email**: [charansai@example.com](mailto:charansai@example.com)  
- **GitHub**: [github.com/charansai](https://github.com/charansai)  
- **Blog**: [charansai.blog](https://charansai.blog)

---

<footer>
  &copy; 2025 Charan Sai Vaddi — Built with terminal soul
</footer>

<script>
// Theme toggle
const toggleTheme = () => {
  const current = document.body.getAttribute("data-theme");
  const next = current === "dark" ? "light" : "dark";
  document.body.setAttribute("data-theme", next);
  localStorage.setItem("theme", next);
};

// Load theme from localStorage
window.onload = () => {
  const saved = localStorage.getItem("theme");
  if (saved) document.body.setAttribute("data-theme", saved);
};

// Parallax effect
window.addEventListener('scroll', () => {
  const scrolled = window.scrollY;
  document.querySelectorAll('.parallax').forEach(el => {
    el.style.setProperty('--scroll', `${scrolled * 0.3}px`);
  });
});
</script>
