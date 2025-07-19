<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sahil Sojitra - FullStack Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        .profile-header {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            display: grid;
            grid-template-columns: 1fr auto;
            gap: 40px;
            align-items: center;
        }

        .profile-info h1 {
            font-size: 3rem;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: fadeInUp 1s ease-out;
        }

        .profile-info .subtitle {
            font-size: 1.5rem;
            color: #666;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease-out 0.2s both;
        }

        .profile-info .description {
            font-size: 1.1rem;
            color: #777;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.4s both;
        }

        .coding-gif {
            width: 350px;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            animation: float 3s ease-in-out infinite;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
        }

        .stat-card i {
            font-size: 3rem;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-card h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: #333;
        }

        .stat-card p {
            color: #666;
            font-size: 0.95rem;
        }

        .content-section {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 30px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title i {
            background: linear-gradient(45deg, #667eea, #764ba2);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-category h4 {
            font-size: 1.3rem;
            margin-bottom: 15px;
            color: #333;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            padding: 8px 16px;
            border-radius: 25px;
            font-size: 0.9rem;
            font-weight: 500;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .skill-tag:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        .contact-info {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            align-items: center;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            background: rgba(102, 126, 234, 0.1);
            padding: 12px 20px;
            border-radius: 25px;
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateY(-2px);
        }

        .contact-item i {
            color: #667eea;
            font-size: 1.2rem;
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 30px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 50px;
            height: 50px;
            background: linear-gradient(45deg, #667eea, #764ba2);
            color: white;
            border-radius: 50%;
            text-decoration: none;
            font-size: 1.5rem;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            transform: translateY(-5px) scale(1.1);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        .learning-list {
            list-style: none;
            padding: 0;
        }

        .learning-list li {
            background: rgba(102, 126, 234, 0.1);
            margin-bottom: 10px;
            padding: 15px 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
            transition: all 0.3s ease;
        }

        .learning-list li:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateX(10px);
        }

        .learning-list li i {
            color: #667eea;
            margin-right: 10px;
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

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        @media (max-width: 768px) {
            .profile-header {
                grid-template-columns: 1fr;
                text-align: center;
                padding: 30px 20px;
            }

            .profile-info h1 {
                font-size: 2.5rem;
            }

            .coding-gif {
                width: 280px;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: 1fr;
            }

            .content-section {
                padding: 30px 20px;
            }

            .section-title {
                font-size: 1.8rem;
            }

            .contact-info {
                justify-content: center;
            }
        }

        @media (max-width: 480px) {
            .container {
                padding: 10px;
            }

            .profile-info h1 {
                font-size: 2rem;
            }

            .profile-info .subtitle {
                font-size: 1.3rem;
            }

            .coding-gif {
                width: 250px;
            }

            .content-section {
                padding: 20px 15px;
            }

            .section-title {
                font-size: 1.5rem;
            }

            .skill-tags {
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Profile Header -->
        <div class="profile-header">
            <div class="profile-info">
                <h1>Hi 👋, I'm Sahil Sojitra</h1>
                <div class="subtitle">💻 A Passionate FullStack Developer</div>
                <div class="description">
                    Welcome to my GitHub profile! I'm a passionate software developer with expertise in building dynamic and scalable web applications using .NET, Angular, and modern web technologies.
                </div>
                <div class="contact-info">
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <span>23sahilsojitra@gmail.com</span>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-laugh"></i>
                        <span>Fun fact: I am Funny 😄</span>
                    </div>
                </div>
            </div>
            <img src="https://cdn.dribbble.com/users/1162077/screenshots/3848914/programmer.gif" alt="Coding Animation" class="coding-gif">
        </div>

        <!-- Stats Grid -->
        <div class="stats-grid">
            <div class="stat-card">
                <i class="fas fa-code"></i>
                <h3>Languages</h3>
                <p>C#, JavaScript, TypeScript, HTML, CSS</p>
            </div>
            <div class="stat-card">
                <i class="fas fa-cogs"></i>
                <h3>Frameworks</h3>
                <p>.NET Core, ASP.NET MVC, Angular</p>
            </div>
            <div class="stat-card">
                <i class="fas fa-database"></i>
                <h3>Database</h3>
                <p>SQL Server, Entity Framework</p>
            </div>
            <div class="stat-card">
                <i class="fas fa-cloud"></i>
                <h3>Learning</h3>
                <p>AWS, Azure, Microservices</p>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="content-section">
            <h2 class="section-title">
                <i class="fas fa-rocket"></i>
                Languages and Tools
            </h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h4><i class="fas fa-code"></i> Languages</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">C#</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">TypeScript</span>
                        <span class="skill-tag">HTML</span>
                        <span class="skill-tag">CSS</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h4><i class="fas fa-layer-group"></i> Frameworks</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">.NET Framework</span>
                        <span class="skill-tag">.NET Core</span>
                        <span class="skill-tag">ASP.NET MVC</span>
                        <span class="skill-tag">ASP.NET Web API</span>
                        <span class="skill-tag">Angular</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h4><i class="fas fa-tools"></i> Libraries & Tools</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">LINQ</span>
                        <span class="skill-tag">SignalR</span>
                        <span class="skill-tag">ADO.NET</span>
                        <span class="skill-tag">Dapper</span>
                        <span class="skill-tag">Entity Framework</span>
                        <span class="skill-tag">jQuery</span>
                        <span class="skill-tag">Bootstrap</span>
                        <span class="skill-tag">Tailwind CSS</span>
                    </div>
                </div>
                <div class="skill-category">
                    <h4><i class="fas fa-server"></i> Hosting & Cloud</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">IIS Server</span>
                        <span class="skill-tag">SmartASP.NET</span>
                        <span class="skill-tag">AWS (Learning)</span>
                        <span class="skill-tag">Azure (Learning)</span>
                        <span class="skill-tag">Git</span>
                        <span class="skill-tag">GitHub</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Current Learning -->
        <div class="content-section">
            <h2 class="section-title">
                <i class="fas fa-graduation-cap"></i>
                Currently Learning & Growing
            </h2>
            <ul class="learning-list">
                <li><i class="fas fa-angle-right"></i> Advanced Angular features and best practices</li>
                <li><i class="fas fa-angle-right"></i> Microservices architecture in .NET Core</li>
                <li><i class="fas fa-angle-right"></i> Integrating Cloud services like Azure Functions and App Services</li>
                <li><i class="fas fa-angle-right"></i> Performance tuning in .NET Core and SQL Server</li>
                <li><i class="fas fa-angle-right"></i> Hosting and deployment using IIS and SmartASP.NET</li>
                <li><i class="fas fa-angle-right"></i> Using SignalR for real-time communication in .NET apps</li>
                <li><i class="fas fa-angle-right"></i> Securing web APIs with JWT, OAuth2, and IdentityServer</li>
            </ul>
        </div>

        <!-- What I'm Working On -->
        <div class="content-section">
            <h2 class="section-title">
                <i class="fas fa-lightbulb"></i>
                What I'm Working On
            </h2>
            <p style="font-size: 1.1rem; line-height: 1.8; color: #555;">
                I'm currently focusing on developing full-stack applications using .NET, including .NET Core, ASP.NET Web API, and ASP.NET MVC for the backend. I'm actively learning Angular to strengthen my frontend development skills and aiming to build more dynamic, responsive user interfaces. I'm also exploring cloud technologies like Azure and deepening my understanding of microservices architecture to design scalable, distributed systems.
            </p>
        </div>

        <!-- Connect Section -->
        <div class="content-section">
            <h2 class="section-title">
                <i class="fas fa-handshake"></i>
                Let's Connect
            </h2>
            <p style="font-size: 1.1rem; line-height: 1.8; color: #555; text-align: center; margin-bottom: 30px;">
                I'm always open to collaboration, learning, and new opportunities. Whether you want to work together, share ideas, or just have a developer-to-developer chat — feel free to reach out!
            </p>
            <div class="social-links">
                <a href="https://linkedin.com/in/sahil-sojitra-370bbb22a" target="_blank" class="social-link" title="LinkedIn">
                    <i class="fab fa-linkedin-in"></i>
                </a>
                <a href="mailto:23sahilsojitra@gmail.com" class="social-link" title="Email">
                    <i class="fas fa-envelope"></i>
                </a>
                <a href="#" class="social-link" title="GitHub">
                    <i class="fab fa-github"></i>
                </a>
            </div>
        </div>
    </div>

    <script>
        // Add smooth scrolling and interactive animations
        document.addEventListener('DOMContentLoaded', function() {
            // Animate skill tags on scroll
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };

            const observer = new IntersectionObserver(function(entries) {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.animationDelay = Math.random() * 0.5 + 's';
                        entry.target.classList.add('animate-in');
                    }
                });
            }, observerOptions);

            // Observe all skill tags
            document.querySelectorAll('.skill-tag').forEach(tag => {
                observer.observe(tag);
            });

            // Add hover effects to stat cards
            document.querySelectorAll('.stat-card').forEach(card => {
                card.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-10px) scale(1.02)';
                });
                
                card.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });
        });
    </script>

    <style>
        .animate-in {
            animation: slideInUp 0.6s ease-out forwards;
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</body>
</html>
