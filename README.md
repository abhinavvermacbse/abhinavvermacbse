<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Abhinav Verma | Java Backend Developer</title>

<style>
:root {
    --primary: #2563eb;
    --dark: #0f172a;
    --light: #f8fafc;
    --gray: #64748b;
}

body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: var(--light);
    color: var(--dark);
    scroll-behavior: smooth;
    transition: 0.3s;
}

.dark {
    background: var(--dark);
    color: var(--light);
}

nav {
    position: fixed;
    width: 100%;
    background: white;
    padding: 15px 40px;
    display: flex;
    justify-content: space-between;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    z-index: 1000;
}

.dark nav {
    background: #1e293b;
}

nav a {
    margin: 0 15px;
    text-decoration: none;
    color: var(--primary);
    font-weight: bold;
}

section {
    padding: 100px 40px;
    min-height: 100vh;
}

.hero {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
}

.btn {
    background: var(--primary);
    color: white;
    padding: 10px 20px;
    border-radius: 8px;
    text-decoration: none;
    margin-top: 20px;
    display: inline-block;
    cursor: pointer;
}

.skills {
    max-width: 600px;
    margin: auto;
}

.skill {
    margin-bottom: 20px;
}

.bar {
    height: 10px;
    background: #ddd;
    border-radius: 10px;
    overflow: hidden;
}

.progress {
    height: 100%;
    width: 0;
    background: var(--primary);
    transition: 2s;
}

.projects {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

.card {
    background: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    transition: 0.3s;
    cursor: pointer;
}

.dark .card {
    background: #1e293b;
}

.card:hover {
    transform: translateY(-10px);
}

.counter {
    font-size: 40px;
    color: var(--primary);
}

footer {
    text-align: center;
    padding: 20px;
    background: #e2e8f0;
}

.dark footer {
    background: #1e293b;
}
</style>
</head>

<body>

<nav>
    <div><strong>Abhinav Verma</strong></div>
    <div>
        <a href="#about">About</a>
        <a href="#skills">Skills</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
        <span class="btn" onclick="toggleMode()">🌙</span>
    </div>
</nav>

<section class="hero">
    <h1>🚀 Java Backend Developer</h1>
    <p>Spring Boot | REST APIs | MySQL | Secure & Scalable Systems</p>
    <a href="#contact" class="btn">Let's Connect</a>
</section>

<section id="about">
    <h2>About Me</h2>
    <p>I build scalable, secure backend systems with strong focus on performance and clean architecture.</p>
    <div>
        <span class="counter" data-target="10000">0</span>+ Records Processed<br><br>
        <span class="counter" data-target="35">0</span>% Performance Boost<br><br>
        <span class="counter" data-target="25">0</span>% Efficiency Increase
    </div>
</section>

<section id="skills">
    <h2>Tech Skills</h2>
    <div class="skills">
        <div class="skill">
            Java & Spring Boot
            <div class="bar"><div class="progress" data-width="90%"></div></div>
        </div>
        <div class="skill">
            MySQL & Query Optimization
            <div class="bar"><div class="progress" data-width="85%"></div></div>
        </div>
        <div class="skill">
            Security (JWT & AES-256)
            <div class="bar"><div class="progress" data-width="80%"></div></div>
        </div>
    </div>
</section>

<section id="projects">
    <h2>Projects</h2>
    <div class="projects">
        <div class="card" onclick="alert('Government land lease survey platform with JWT authentication & PDF/Excel reports.')">
            <h3>🏛 Survey Platform</h3>
            <p>Spring Boot + React | Secure | Scalable</p>
        </div>
        <div class="card" onclick="alert('Admin panel for exams & results with optimized APIs and reduced latency.')">
            <h3>🧑‍💼 Pareekshn Admin Panel</h3>
            <p>High-performance backend system</p>
        </div>
    </div>
</section>

<section id="contact">
    <h2>Contact</h2>
    <p>📍 Noida, India</p>
    <p>📧 abhinavvermaworkplace@gmail.com</p>
    <a class="btn" href="mailto:abhinavvermaworkplace@gmail.com">Email Me</a>
</section>

<footer>
    © 2026 Abhinav Verma | Java Backend Developer
</footer>

<script>
function toggleMode() {
    document.body.classList.toggle("dark");
}

// Animate skill bars
window.addEventListener("scroll", () => {
    document.querySelectorAll(".progress").forEach(bar => {
        let position = bar.getBoundingClientRect().top;
        if (position < window.innerHeight) {
            bar.style.width = bar.dataset.width;
        }
    });

    document.querySelectorAll(".counter").forEach(counter => {
        let position = counter.getBoundingClientRect().top;
        if (position < window.innerHeight && counter.innerText == "0") {
            let target = +counter.dataset.target;
            let count = 0;
            let step = target / 100;
            let interval = setInterval(() => {
                count += step;
                if (count >= target) {
                    counter.innerText = target;
                    clearInterval(interval);
                } else {
                    counter.innerText = Math.floor(count);
                }
            }, 20);
        }
    });
});
</script>

</body>
</html>
