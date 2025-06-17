<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nikita Patidar - Data Scientist</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0a0a;
            color: #ffffff;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: linear-gradient(45deg, #0a0a0a, #1a1a2e, #16213e);
            background-size: 400% 400%;
            animation: gradientShift 8s ease infinite;
        }

        .floating-particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            background: #ff6b35;
            border-radius: 50%;
            opacity: 0.1;
            animation: float 15s infinite linear;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.1; }
            90% { opacity: 0.1; }
            100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; }
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        @keyframes glow {
            0%, 100% { box-shadow: 0 0 20px rgba(255, 107, 53, 0.3); }
            50% { box-shadow: 0 0 40px rgba(255, 107, 53, 0.6); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .header {
            text-align: center;
            padding: 50px 0;
            animation: fadeInUp 1s ease-out;
        }

        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid #ff6b35;
            margin-bottom: 20px;
            animation: pulse 2s infinite, glow 3s infinite;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 60px;
            margin: 0 auto 20px;
        }

        .name {
            font-size: 3.5rem;
            font-weight: bold;
            background: linear-gradient(45deg, #ff6b35, #f7931e, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
        }

        .typing-text {
            font-size: 1.5rem;
            color: #ff6b35;
            white-space: nowrap;
            overflow: hidden;
            border-right: 3px solid #ff6b35;
            width: 100%;
            margin: 0 auto;
            animation: typing 4s steps(40, end), blink 0.75s step-end infinite;
        }

        .section {
            margin: 60px 0;
            padding: 30px;
            background: rgba(255, 255, 255, 0.02);
            border-radius: 20px;
            border: 1px solid rgba(255, 107, 53, 0.1);
            backdrop-filter: blur(10px);
            animation: fadeInUp 1s ease-out;
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.2);
        }

        .section-title {
            font-size: 2.5rem;
            margin-bottom: 20px;
            text-align: center;
            background: linear-gradient(45deg, #ff6b35, #ffd700);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .about-item {
            padding: 20px;
            background: rgba(255, 107, 53, 0.05);
            border-radius: 15px;
            border-left: 4px solid #ff6b35;
            transition: all 0.3s ease;
        }

        .about-item:hover {
            background: rgba(255, 107, 53, 0.1);
            transform: translateX(10px);
        }

        .tech-stack {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .tech-item {
            padding: 20px;
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(247, 147, 30, 0.1));
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(255, 107, 53, 0.2);
            cursor: pointer;
        }

        .tech-item:hover {
            transform: scale(1.1) rotate(2deg);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.3);
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.2), rgba(247, 147, 30, 0.2));
        }

        .tech-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
            display: block;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.05), rgba(26, 26, 46, 0.8));
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 107, 53, 0.2);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 107, 53, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(255, 107, 53, 0.3);
        }

        .project-title {
            font-size: 1.5rem;
            color: #ff6b35;
            margin-bottom: 15px;
            font-weight: bold;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .stat-card {
            background: linear-gradient(135deg, rgba(255, 107, 53, 0.1), rgba(255, 215, 0, 0.1));
            padding: 30px;
            border-radius: 20px;
            text-align: center;
            border: 2px solid rgba(255, 107, 53, 0.2);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .stat-card:hover {
            transform: scale(1.05);
            border-color: #ff6b35;
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            color: #ff6b35;
            display: block;
            margin-bottom: 10px;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
            flex-wrap: wrap;
        }

        .contact-btn {
            padding: 15px 30px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border: none;
            border-radius: 50px;
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .contact-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s ease;
        }

        .contact-btn:hover::before {
            left: 100%;
        }

        .contact-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(255, 107, 53, 0.4);
        }

        .wave {
            display: inline-block;
            animation: wave 2s infinite;
        }

        @keyframes wave {
            0%, 20%, 60%, 100% { transform: rotate(0deg); }
            10%, 30% { transform: rotate(-10deg); }
            40%, 50% { transform: rotate(10deg); }
        }

        .scroll-indicator {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            animation: pulse 2s infinite;
            z-index: 1000;
        }

        @media (max-width: 768px) {
            .name { font-size: 2.5rem; }
            .typing-text { font-size: 1.2rem; }
            .section-title { font-size: 2rem; }
            .contact-links { flex-direction: column; align-items: center; }
        }
    </style>
</head>
<body>
    <div class="bg-animation"></div>
    <div class="floating-particles" id="particles"></div>

    <div class="container">
        <header class="header">
            <div class="profile-img">👋</div>
            <h1 class="name">Hi, I'm Nikita Patidar!</h1>
            <div class="typing-text">🚀 Data Scientist | Machine Learning | Generative AI Enthusiast</div>
        </header>

        <section class="section">
            <h2 class="section-title">👋 About Me</h2>
            <div class="about-grid">
                <div class="about-item">
                    <strong>👀 Interested in:</strong> Generative AI, Deep Learning, NLP, and Data Science
                </div>
                <div class="about-item">
                    <strong>🌱 Currently learning:</strong> LLM fine-tuning, MLOps, AI model deployment
                </div>
                <div class="about-item">
                    <strong>💞️ Looking to collaborate on:</strong> AI-driven solutions, ML projects, and open-source contributions
                </div>
                <div class="about-item">
                    <strong>⚡ Fun fact:</strong> I love breaking down complex AI topics into simple insights!
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">🚀 Tech Stack</h2>
            <div class="tech-stack">
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🐍</span>
                    <div>Python</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🧠</span>
                    <div>TensorFlow</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🔥</span>
                    <div>PyTorch</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">📊</span>
                    <div>Scikit-learn</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">⚡</span>
                    <div>FastAPI</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🗄️</span>
                    <div>PostgreSQL</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🍃</span>
                    <div>MongoDB</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">☁️</span>
                    <div>AWS</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🌐</span>
                    <div>Azure</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">🐳</span>
                    <div>Docker</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">☸️</span>
                    <div>Kubernetes</div>
                </div>
                <div class="tech-item" onclick="animateSkill(this)">
                    <span class="tech-icon">📝</span>
                    <div>Jupyter</div>
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">🌱 Currently Exploring</h2>
            <div class="about-grid">
                <div class="about-item">
                    <strong>🔥</strong> Fine-tuning Large Language Models (LLMs)
                </div>
                <div class="about-item">
                    <strong>🏗️</strong> Scaling AI models for production
                </div>
                <div class="about-item">
                    <strong>🌍</strong> MLOps & Cloud-based AI deployment
                </div>
                <div class="about-item">
                    <strong>📊</strong> Interpretable AI & Explainable Machine Learning
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">📊 GitHub Stats</h2>
            <div class="stats-container">
                <div class="stat-card" onclick="animateStat(this)">
                    <span class="stat-number" data-target="150">0</span>
                    <div>Repositories</div>
                </div>
                <div class="stat-card" onclick="animateStat(this)">
                    <span class="stat-number" data-target="500">0</span>
                    <div>Commits</div>
                </div>
                <div class="stat-card" onclick="animateStat(this)">
                    <span class="stat-number" data-target="50">0</span>
                    <div>Pull Requests</div>
                </div>
                <div class="stat-card" onclick="animateStat(this)">
                    <span class="stat-number" data-target="25">0</span>
                    <div>Projects</div>
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">🖥️ Latest AI & ML Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-title">🤖 LLM-Based Chatbot</div>
                    <p>Fine-tuned GPT for personalized responses using Python and OpenAI API. Implemented advanced conversation flow and context management.</p>
                    <br>
                    <strong>Tech:</strong> Python, OpenAI API, Transformers
                </div>
                <div class="project-card">
                    <div class="project-title">📉 Stock Price Prediction</div>
                    <p>Deep Learning model for financial forecasting using LSTM networks and time series analysis with TensorFlow.</p>
                    <br>
                    <strong>Tech:</strong> TensorFlow, LSTM, Time Series Analysis
                </div>
                <div class="project-card">
                    <div class="project-title">🧠 AI-Powered Resume Screener</div>
                    <p>Automated resume ranking system using NLP and transformer models to streamline recruitment processes.</p>
                    <br>
                    <strong>Tech:</strong> NLP, Transformers, BERT
                </div>
                <div class="project-card">
                    <div class="project-title">🔎 Fake News Detection</div>
                    <p>Text classification system using BERT transformers to identify and classify fake news articles with high accuracy.</p>
                    <br>
                    <strong>Tech:</strong> NLP, BERT, Text Classification
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">🔗 Connect with Me</h2>
            <div class="contact-links">
                <a href="https://linkedin.com/in/yourname" class="contact-btn" target="_blank">
                    💼 LinkedIn
                </a>
                <a href="mailto:your.email@gmail.com" class="contact-btn">
                    📧 Email
                </a>
                <a href="https://twitter.com/yourhandle" class="contact-btn" target="_blank">
                    🐦 Twitter
                </a>
                <a href="https://github.com/patidarnikita183" class="contact-btn" target="_blank">
                    🐱 GitHub
                </a>
            </div>
        </section>
    </div>

    <div class="scroll-indicator" onclick="scrollToTop()">
        ↑
    </div>

    <script>
        // Create floating particles
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.width = particle.style.height = Math.random() * 10 + 5 + 'px';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Animate skill cards
        function animateSkill(element) {
            element.style.transform = 'scale(1.2) rotate(5deg)';
            element.style.boxShadow = '0 15px 35px rgba(255, 107, 53, 0.5)';
            setTimeout(() => {
                element.style.transform = '';
                element.style.boxShadow = '';
            }, 300);
        }

        // Animate stats counter
        function animateStat(card) {
            const numberElement = card.querySelector('.stat-number');
            const target = parseInt(numberElement.dataset.target);
            let current = 0;
            const increment = target / 50;
            
            const timer = setInterval(() => {
                current += increment;
                if (current >= target) {
                    current = target;
                    clearInterval(timer);
                }
                numberElement.textContent = Math.floor(current);
            }, 20);
        }

        // Scroll to top
        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationDelay = '0.2s';
                    entry.target.style.animationFillMode = 'forwards';
                }
            });
        }, observerOptions);

        // Add mouse movement effect
        document.addEventListener('mousemove', (e) => {
            const cursor = document.createElement('div');
            cursor.style.position = 'fixed';
            cursor.style.left = e.clientX + 'px';
            cursor.style.top = e.clientY + 'px';
            cursor.style.width = '5px';
            cursor.style.height = '5px';
            cursor.style.background = 'rgba(255, 107, 53, 0.3)';
            cursor.style.borderRadius = '50%';
            cursor.style.pointerEvents = 'none';
            cursor.style.zIndex = '1000';
            cursor.style.animation = 'fadeOut 1s forwards';
            document.body.appendChild(cursor);
            
            setTimeout(() => {
                cursor.remove();
            }, 1000);
        });

        // Add fadeOut animation
        const style = document.createElement('style');
        style.textContent = `
            @keyframes fadeOut {
                to {
                    opacity: 0;
                    transform: scale(3);
                }
            }
        `;
        document.head.appendChild(style);

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            
            // Observe all sections
            document.querySelectorAll('.section').forEach(section => {
                observer.observe(section);
            });
        });

        // Add parallax effect to background
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelector('.bg-animation');
            const speed = scrolled * 0.5;
            parallax.style.transform = `translateY(${speed}px)`;
        });
    </script>
</body>
</html>
