<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(10px);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #24292e 0%, #0d1117 100%);
            color: white;
            padding: 40px;
            text-align: center;
            position: relative;
        }

        .header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 20"><defs><radialGradient id="a" cx="50%" cy="0%" r="100%"><stop offset="0%" stop-color="%23ffffff" stop-opacity="0.1"/><stop offset="100%" stop-color="%23ffffff" stop-opacity="0"/></radialGradient></defs><rect width="100" height="20" fill="url(%23a)"/></svg>');
            opacity: 0.3;
        }

        .profile-content {
            position: relative;
            z-index: 1;
        }

        .profile-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            border: 4px solid #58a6ff;
            margin: 0 auto 20px;
            background: linear-gradient(45deg, #58a6ff, #1f6feb);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            font-weight: bold;
        }

        .profile-name {
            font-size: 2.5em;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #58a6ff, #1f6feb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .profile-title {
            font-size: 1.2em;
            color: #7c3aed;
            margin-bottom: 15px;
        }

        .profile-bio {
            font-size: 1.1em;
            line-height: 1.6;
            max-width: 600px;
            margin: 0 auto;
            opacity: 0.9;
        }

        .main-content {
            padding: 40px;
        }

        .section {
            margin-bottom: 50px;
        }

        .section-title {
            font-size: 2em;
            color: #24292e;
            margin-bottom: 25px;
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: linear-gradient(45deg, #58a6ff, #7c3aed);
            border-radius: 2px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            background: white;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .tech-icon {
            width: 50px;
            height: 50px;
            margin-bottom: 10px;
            transition: transform 0.3s ease;
        }

        .tech-item:hover .tech-icon {
            transform: scale(1.2);
        }

        .tech-name {
            font-weight: 600;
            color: #24292e;
            text-align: center;
            font-size: 0.9em;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .stat-card {
            background: white;
            border-radius: 15px;
            padding: 25px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
        }

        .stat-card img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
        }

        .github-link {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            background: #24292e;
            color: white;
            text-decoration: none;
            padding: 15px 30px;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            margin-top: 30px;
        }

        .github-link:hover {
            background: #1f6feb;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(31, 111, 235, 0.3);
        }

        .contact-section {
            text-align: center;
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 40px;
            margin: 0 -40px;
            border-radius: 0 0 20px 20px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .floating {
            animation: float 3s ease-in-out infinite;
        }

        @media (max-width: 768px) {
            .container {
                margin: 10px;
                border-radius: 15px;
            }
            
            .header {
                padding: 30px 20px;
            }
            
            .profile-name {
                font-size: 2em;
            }
            
            .main-content {
                padding: 30px 20px;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
                gap: 15px;
            }
            
            .stats-container {
                grid-template-columns: 1fr;
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="profile-content">
                <div class="profile-avatar floating">
                    👨‍💻
                </div>
                <h1 class="profile-name">Your Name</h1>
                <p class="profile-title">🚀 Full Stack Web Developer</p>
                <p class="profile-bio">
                    Passionate full stack developer with expertise in modern web technologies. 
                    I love creating beautiful, functional, and user-friendly applications that solve real-world problems.
                </p>
            </div>
        </div>

        <div class="main-content">
            <section class="section">
                <h2 class="section-title">🛠️ Technologies & Tools</h2>
                <div class="tech-grid">
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5" class="tech-icon">
                        <span class="tech-name">HTML5</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3" class="tech-icon">
                        <span class="tech-name">CSS3</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" class="tech-icon">
                        <span class="tech-name">JavaScript</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg" alt="PHP" class="tech-icon">
                        <span class="tech-name">PHP</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/laravel/laravel-plain.svg" alt="Laravel" class="tech-icon">
                        <span class="tech-name">Laravel</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MySQL" class="tech-icon">
                        <span class="tech-name">MySQL</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt="MongoDB" class="tech-icon">
                        <span class="tech-name">MongoDB</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="PostgreSQL" class="tech-icon">
                        <span class="tech-name">PostgreSQL</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="VS Code" class="tech-icon">
                        <span class="tech-name">VS Code</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg" alt="Figma" class="tech-icon">
                        <span class="tech-name">Figma</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" class="tech-icon">
                        <span class="tech-name">GitHub</span>
                    </div>
                    <div class="tech-item">
                        <img src="https://raw.githubusercontent.com/jgraph/drawio-desktop/dev/build/icon.svg" alt="Draw.io" class="tech-icon">
                        <span class="tech-name">Draw.io</span>
                    </div>
                </div>
            </section>

            <section class="section">
                <h2 class="section-title">📊 GitHub Statistics</h2>
                <div class="stats-container">
                    <div class="stat-card">
                        <img src="https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=58a6ff&icon_color=1f6feb&text_color=c9d1d9" alt="GitHub Stats">
                    </div>
                    <div class="stat-card">
                        <img src="https://github-readme-streak-stats.herokuapp.com/?user=YOUR_GITHUB_USERNAME&theme=tokyonight&hide_border=true&background=0D1117" alt="GitHub Streak">
                    </div>
                    <div class="stat-card">
                        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=58a6ff&text_color=c9d1d9" alt="Top Languages">
                    </div>
                    <div class="stat-card">
                        <img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=YOUR_GITHUB_USERNAME&theme=tokyonight" alt="Profile Summary">
                    </div>
                </div>
            </section>

            <div class="contact-section">
                <h2 class="section-title">🤝 Let's Connect!</h2>
                <p style="margin-bottom: 20px; color: #6c757d;">
                    Always excited to collaborate on interesting projects and meet fellow developers!
                </p>
                <a href="https://github.com/YOUR_GITHUB_USERNAME" class="github-link" target="_blank">
                    <svg width="20" height="20" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
                    </svg>
                    Visit My GitHub
                </a>
                <p style="margin-top: 20px; font-size: 0.9em; color: #6c757d;">
                    📧 your.email@example.com | 💼 LinkedIn: /in/yourprofile
                </p>
            </div>
        </div>
    </div>

    <script>
        // Add some interactive animations
        document.querySelectorAll('.tech-item').forEach(item => {
            item.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-10px) scale(1.05)';
            });
            
            item.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Smooth scroll animation for sections
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section').forEach(section => {
            section.style.opacity = '0';
            section.style.transform = 'translateY(30px)';
            section.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(section);
        });

        // Add typing effect to bio
        const bio = document.querySelector('.profile-bio');
        const bioText = bio.textContent;
        bio.textContent = '';
        
        let i = 0;
        const typeWriter = () => {
            if (i < bioText.length) {
                bio.textContent += bioText.charAt(i);
                i++;
                setTimeout(typeWriter, 30);
            }
        };
        
        setTimeout(typeWriter, 1000);
    </script>
</body>
</html>
