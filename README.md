<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Osama Ahmed | GitHub Profile</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link
        href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400;1,700&family=Tajawal:wght@200;300;400;500;700;800;900&display=swap"
        rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        :root {
            --bg-dark: #0a0a0f;
            --bg-card: #12121a;
            --primary: #00d9ff;
            --secondary: #7c3aed;
            --accent: #f59e0b;
            --text-main: #e2e8f0;
            --text-dim: #94a3b8;
            --grid-color: rgba(0, 217, 255, 0.03);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-font-smoothing: antialiased;
        }

        body {
            background-color: var(--bg-dark);
            background-image:
                linear-gradient(var(--grid-color) 1px, transparent 1px),
                linear-gradient(90deg, var(--grid-color) 1px, transparent 1px);
            background-size: 30px 30px;
            color: var(--text-main);
            font-family: 'Tajawal', sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 100vh;
        }

        header,
        section,
        footer {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeUp 0.8s forwards;
        }

        .container {
            width: 100%;
            max-width: 900px;
            padding: 40px 20px;
            display: flex;
            flex-direction: column;
            gap: 60px;
        }

        h1,
        h2,
        h3,
        .heading-font {
            font-family: 'Space Mono', monospace;
        }

        /* Blobs */
        .blobs {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            overflow: hidden;
            filter: blur(80px);
        }

        .blob {
            position: absolute;
            border-radius: 50%;
            opacity: 0.15;
            animation: float 8s ease-in-out infinite;
        }

        .blob-1 {
            width: 300px;
            height: 300px;
            background: var(--primary);
            top: 10%;
            left: -5%;
            animation-delay: 0s;
        }

        .blob-2 {
            width: 400px;
            height: 400px;
            background: var(--secondary);
            bottom: 10%;
            right: -5%;
            animation-delay: -2s;
        }

        .blob-3 {
            width: 250px;
            height: 250px;
            background: var(--accent);
            top: 50%;
            left: 50%;
            animation-delay: -4s;
        }

        /* 1. HERO SECTION */
        .hero {
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
            animation-delay: 0.1s;
        }

        .avatar-container {
            position: relative;
            width: 140px;
            height: 140px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 10px;
        }

        .avatar-ring {
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 50%;
            padding: 4px;
            background: linear-gradient(45deg, var(--primary), var(--secondary), var(--accent), var(--primary));
            background-size: 300% 300%;
            animation: spin 3s linear infinite;
        }

        .avatar-content {
            position: relative;
            width: calc(100% - 8px);
            height: calc(100% - 8px);
            background: var(--bg-dark);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 64px;
            z-index: 1;
        }

        .hero-name {
            font-size: 3.5rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 5px;
            letter-spacing: -1px;
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--text-dim);
            font-family: 'Space Mono', monospace;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .typing-container {
            font-family: 'Space Mono', monospace;
            font-size: 1rem;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 5px;
            min-height: 1.5em;
        }

        .cursor {
            width: 10px;
            height: 1.2em;
            background: var(--primary);
            animation: blink 1s step-end infinite;
        }

        .hero-badges {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 10px;
        }

        .badge-pill {
            padding: 8px 16px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 100px;
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--text-main);
            display: flex;
            align-items: center;
            gap: 8px;
            backdrop-filter: blur(4px);
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
            transition: var(--transition);
        }

        .badge-pill:hover {
            border-color: var(--primary);
            box-shadow: 0 0 20px rgba(0, 217, 255, 0.2);
            transform: translateY(-2px);
        }

        /* 2. SOCIAL LINKS BAR */
        .social-bar {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 15px;
            animation-delay: 0.2s;
        }

        .social-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 14px;
            background: var(--bg-card);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            color: var(--text-main);
            text-decoration: none;
            font-weight: 600;
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .social-btn span {
            position: relative;
            z-index: 1;
        }

        .social-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.05), transparent);
            transition: 0.5s;
        }

        .social-btn:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3), 0 0 15px rgba(0, 217, 255, 0.1);
        }

        .social-btn:hover::before {
            left: 100%;
        }

        .social-btn:hover span {
            color: var(--primary);
        }

        /* 3. ABOUT ME CARDS */
        .about-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            animation-delay: 0.3s;
        }

        .about-card {
            background: var(--bg-card);
            padding: 30px;
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.03);
            position: relative;
            overflow: hidden;
            transition: var(--transition);
        }

        .about-card::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            transition: var(--transition);
        }

        .about-card:hover {
            transform: translateY(-8px);
            border-color: rgba(0, 217, 255, 0.1);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
        }

        .about-card:hover::after {
            width: 100%;
        }

        .card-icon {
            font-size: 24px;
            margin-bottom: 15px;
            display: block;
        }

        .card-title {
            font-size: 1.15rem;
            font-weight: 700;
            color: var(--primary);
            margin-bottom: 10px;
            display: block;
        }

        .card-text {
            color: var(--text-dim);
            font-size: 0.95rem;
            line-height: 1.5;
        }

        /* 4. LANGUAGES & TOOLS */
        .skills-section {
            animation-delay: 0.4s;
        }

        .section-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 30px;
        }

        .section-header h2 {
            font-size: 1.5rem;
            color: var(--text-main);
            white-space: nowrap;
        }

        .line {
            height: 1px;
            background: rgba(255, 255, 255, 0.1);
            width: 100%;
        }

        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }

        .skill-card {
            background: var(--bg-card);
            padding: 20px;
            border-radius: 14px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 12px;
            width: 120px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .skill-card img {
            width: 50px;
            height: 50px;
            filter: drop-shadow(0 0 5px rgba(0, 0, 0, 0.5));
            transition: var(--transition);
        }

        .skill-name {
            font-size: 0.85rem;
            font-weight: 600;
            color: var(--text-dim);
            font-family: 'Space Mono', monospace;
        }

        .skill-card:hover {
            transform: translateY(-6px);
            border-color: var(--primary);
            box-shadow: 0 0 20px rgba(0, 217, 255, 0.15);
        }

        .skill-card:hover img {
            transform: scale(1.1);
        }

        .skill-card:hover .skill-name {
            color: var(--primary);
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: -100%;
            left: -100%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.03), transparent);
            transform: rotate(45deg);
            transition: 0.5s;
        }

        .skill-card:hover::before {
            top: 100%;
            left: 100%;
        }

        /* 5. GITHUB STATS */
        .stats-section {
            animation-delay: 0.5s;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 20px;
            margin-bottom: 20px;
        }

        .stats-image {
            width: 100%;
            border-radius: 12px;
            background: var(--bg-card);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
        }

        .stats-image:hover {
            transform: scale(1.02);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border-color: var(--secondary);
        }

        .streak-full {
            width: 100%;
            margin-top: 10px;
        }

        /* 6. CONTRIBUTION ACTIVITY GRAPH */
        .activity-section {
            animation-delay: 0.6s;
        }

        /* 7. PROFILE VIEWS BADGE */
        .views-badge {
            display: flex;
            justify-content: center;
            margin-top: 20px;
            animation-delay: 0.7s;
        }

        /* 8. FOOTER */
        footer {
            margin-top: 60px;
            padding: 40px 0;
            width: 100%;
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            text-align: center;
            animation-delay: 0.8s;
        }

        .footer-text {
            font-size: 0.9rem;
            color: var(--text-dim);
            font-weight: 500;
            letter-spacing: 1px;
        }

        .footer-accent {
            color: var(--accent);
        }

        /* Keyframes */
        @keyframes spin {
            from {
                background-position: 0% 0%;
                transform: rotate(0deg);
            }

            to {
                background-position: 100% 100%;
                transform: rotate(360deg);
            }
        }

        @keyframes float {

            0%,
            100% {
                transform: translateY(0) scale(1);
            }

            50% {
                transform: translateY(-30px) scale(1.05);
            }
        }

        @keyframes blink {
            50% {
                opacity: 0;
            }
        }

        @keyframes fadeUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Mobile Responsive */
        @media (max-width: 768px) {
            .hero-name {
                font-size: 2.5rem;
            }

            .social-bar {
                grid-template-columns: repeat(2, 1fr);
            }

            .about-grid {
                grid-template-columns: 1fr;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .social-bar {
                grid-template-columns: 1fr;
            }

            .hero-badges {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>

<body>

    <div class="blobs">
        <div class="blob blob-1"></div>
        <div class="blob blob-2"></div>
        <div class="blob blob-3"></div>
    </div>

    <div class="container" style="max-width: 1000px; padding: 0;">

        <!-- 0. WAVING HEADER -->
        <div style="width: 100%; overflow: hidden; border-radius: 0 0 20px 20px; margin-bottom: 40px;">
            <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=180&section=header&text=Osama%20Ahmed&fontSize=42&fontColor=fff&animation=twinkling&fontAlignY=32&desc=Web%20Developer%20in%20Progress&descAlignY=55&descSize=18"
                width="100%" style="display: block;" />
        </div>

        <!-- 1. HERO SECTION -->
        <header class="hero" style="padding: 0 20px;">
            <div class="avatar-container">
                <div class="avatar-ring"></div>
                <div class="avatar-content">👨‍💻</div>
            </div>
            <h1 class="hero-name">Osama Ahmed</h1>
            <p class="hero-subtitle">Web Developer in Progress</p>
            <div class="typing-container">
                <span id="typing-text">// </span>
                <span class="cursor"></span>
            </div>
            <div class="hero-badges">
                <div class="badge-pill">⚡ Web Developer</div>
                <div class="badge-pill">🔮 VS Code</div>
                <div class="badge-pill">🚀 Always Learning</div>
            </div>
        </header>

        <!-- 2. SOCIAL LINKS BAR -->
        <nav class="social-bar" style="padding: 0 20px;">
            <a href="mailto:oa825814@gmail.com" class="social-btn" target="_blank" rel="noopener noreferrer">
                <span><i class="fa-solid fa-envelope" style="color: var(--primary);"></i> Gmail</span>
            </a>
            <a href="https://wa.me/201110958865" class="social-btn" target="_blank" rel="noopener noreferrer">
                <span><i class="fa-brands fa-whatsapp" style="color: #25D366;"></i> WhatsApp</span>
            </a>
            <a href="https://www.linkedin.com/in/osama-ahmed-113102361/" class="social-btn" target="_blank"
                rel="noopener noreferrer">
                <span><i class="fa-brands fa-linkedin" style="color: #0077B5;"></i> LinkedIn</span>
            </a>
            <a href="https://github.com/OsamaTech10" class="social-btn" target="_blank" rel="noopener noreferrer">
                <span><i class="fa-brands fa-github" style="color: var(--text-main);"></i> GitHub</span>
            </a>
        </nav>

        <!-- 3. ABOUT ME CARDS -->
        <section class="about-grid" style="padding: 0 20px;">
            <div class="about-card">
                <span class="card-icon">💡</span>
                <span class="card-title">Curious Mind</span>
                <p class="card-text">Passionate about technology and programming with a love for problem-solving.</p>
            </div>
            <div class="about-card">
                <span class="card-icon">🚀</span>
                <span class="card-title">Current Focus</span>
                <p class="card-text">Diving deep into HTML5, CSS3, and JavaScript to build modern web experiences.</p>
            </div>
            <div class="about-card">
                <span class="card-icon">💻</span>
                <span class="card-title">My Setup</span>
                <p class="card-text">Using VS Code to explore and build real-world web projects.</p>
            </div>
            <div class="about-card">
                <span class="card-icon">🎯</span>
                <span class="card-title">My Goal</span>
                <p class="card-text">Always eager to learn, grow, and tackle new challenges head-on.</p>
            </div>
        </section>

        <!-- 4. LANGUAGES & TOOLS -->
        <section class="skills-section" style="padding: 0 20px;">
            <div class="section-header">
                <h2>Tech Stack</h2>
                <div class="line"></div>
            </div>
            <div style="text-align: center; margin-bottom: 25px;">
                <img src="https://skillicons.dev/icons?i=html,css,js,vscode,git,github&theme=dark" alt="Skill Icons" />
            </div>
            <div class="skills-grid">
                <div class="skill-card">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg"
                        alt="VS Code">
                    <span class="skill-name">VS Code</span>
                </div>
                <div class="skill-card">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5">
                    <span class="skill-name">HTML5</span>
                </div>
                <div class="skill-card">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3">
                    <span class="skill-name">CSS3</span>
                </div>
                <div class="skill-card">
                    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"
                        alt="JavaScript">
                    <span class="skill-name">JavaScript</span>
                </div>
            </div>
        </section>

        <!-- 5. GITHUB STATS -->
        <section class="stats-section" style="padding: 0 20px;">
            <div class="section-header">
                <h2>GitHub Performance</h2>
                <div class="line"></div>
            </div>
            <div class="stats-grid">
                <div class="stats-card">
                    <img class="stats-image"
                        src="https://github-readme-stats.vercel.app/api?username=OsamaTech10&show_icons=true&theme=tokyonight&hide_border=true&bg_color=12121a&title_color=00d9ff&text_color=e2e8f0&icon_color=7c3aed"
                        alt="GitHub Stats">
                </div>
                <div class="stats-card">
                    <img class="stats-image"
                        src="https://github-readme-stats.vercel.app/api/top-langs?username=OsamaTech10&layout=compact&theme=tokyonight&hide_border=true&bg_color=12121a&title_color=00d9ff&text_color=e2e8f0"
                        alt="Top Languages">
                </div>
            </div>
            <div class="stats-card streak-full">
                <img class="stats-image"
                    src="https://github-readme-streak-stats.herokuapp.com/?user=OsamaTech10&theme=tokyonight&hide_border=true&background=12121a&ring=00d9ff&fire=f59e0b&currStreakLabel=00d9ff"
                    alt="GitHub Streak" style="width: 100%;">
            </div>
        </section>

        <!-- 5.5 GITHUB TROPHIES -->
        <section class="trophies-section" style="padding: 0 20px;">
            <div class="section-header">
                <h2>GitHub Trophies</h2>
                <div class="line"></div>
            </div>
            <div
                style="background: var(--bg-card); border-radius: 16px; padding: 20px; border: 1px solid rgba(255, 255, 255, 0.05);">
                <img src="https://github-profile-trophy.vercel.app/?username=OsamaTech10&theme=tokyonight&no-frame=true&margin-w=10&column=6"
                    width="100%" alt="Trophies" />
            </div>
        </section>

        <!-- 6. CONTRIBUTION ACTIVITY GRAPH -->
        <section class="activity-section" style="padding: 0 20px;">
            <div class="section-header">
                <h2>Activity Graph</h2>
                <div class="line"></div>
            </div>
            <img class="stats-image"
                src="https://github-readme-activity-graph.vercel.app/graph?username=OsamaTech10&theme=tokyo-night&hide_border=true&bg_color=12121a&color=00d9ff&line=7c3aed&point=f59e0b"
                alt="Activity Graph">
        </section>

        <!-- 7. PROFILE VIEWS & WAVING FOOTER -->
        <div style="width: 100%; text-align: center; margin-top: 40px;">
            <div style="margin-bottom: 30px;">
                <img src="https://komarev.com/ghpvc/?username=OsamaTech10&color=00d9ff&style=for-the-badge&label=PROFILE+VIEWS"
                    alt="Profile Views">
            </div>
            <div style="width: 100%; overflow: hidden; border-radius: 20px 20px 0 0;">
                <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer&text=⚡+Built+with+passion+·+Always+learning+·+Never+stopping&fontSize=14&fontColor=ffffff&animation=twinkling&fontAlignY=65"
                    width="100%" style="display: block;" />
            </div>
        </div>

    </div>

    <script>
        // Typing animation
        const typingText = document.getElementById('typing-text');
        const text = "Exploring the world of Web Development & building the future";
        let index = 0;

        function type() {
            if (index < text.length) {
                typingText.innerHTML += text.charAt(index);
                index++;
                setTimeout(type, 50);
            }
        }

        // Delay typing until fade animation is partly done
        setTimeout(type, 1000);
    </script>
</body>

</html>
