
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sundas Saleem - Portfolio</title>
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
            overflow-x: hidden;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 1rem 2rem;
            z-index: 1000;
            transition: all 0.3s ease;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #e67e22;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #e67e22;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(45deg, #f39c12, #e67e22);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, #f9e79f 0%, #f39c12 50%, #e67e22 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            z-index: 2;
            max-width: 800px;
            padding: 0 2rem;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.5s forwards;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero .subtitle {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.7s forwards;
        }

        .hero .description {
            font-size: 1.1rem;
            margin-bottom: 2rem;
            opacity: 0;
            animation: fadeInUp 1s ease 0.9s forwards;
        }

        .cta-button {
            display: inline-block;
            padding: 15px 35px;
            background: rgba(255, 255, 255, 0.2);
            border: 2px solid white;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            opacity: 0;
            animation: fadeInUp 1s ease 1.1s forwards;
            margin: 0 10px;
        }

        .cta-button:hover {
            background: white;
            color: #e67e22;
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .floating-shapes {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 1;
        }

        .shape {
            position: absolute;
            opacity: 0.1;
            animation: float 6s ease-in-out infinite;
        }

        .shape:nth-child(1) {
            top: 20%;
            left: 10%;
            width: 80px;
            height: 80px;
            background: white;
            border-radius: 50%;
            animation-delay: 0s;
        }

        .shape:nth-child(2) {
            top: 60%;
            right: 15%;
            width: 60px;
            height: 60px;
            background: white;
            transform: rotate(45deg);
            animation-delay: 2s;
        }

        .shape:nth-child(3) {
            bottom: 20%;
            left: 20%;
            width: 100px;
            height: 100px;
            background: white;
            clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
            animation-delay: 4s;
        }

        /* Sections */
        .section {
            padding: 80px 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            color: #2c3e50;
            position: relative;
        }

        .section h2::after {
            content: '';
            width: 60px;
            height: 4px;
            background: linear-gradient(45deg, #f39c12, #e67e22);
            display: block;
            margin: 1rem auto;
            border-radius: 2px;
        }

        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 4rem;
            align-items: center;
        }

        .profile-image {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(135deg, #f9e79f 0%, #f39c12 50%, #e67e22 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            margin: 0 auto;
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .about-text h3 {
            color: #e67e22;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
            border-left: 4px solid #f39c12;
        }

        .skill-card:hover {
            transform: translateY(-5px);
        }

        .skill-card h3 {
            color: #e67e22;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .skill-card p {
            color: #666;
            line-height: 1.6;
        }

        /* Experience Section */
        .experience-item {
            background: white;
            padding: 2.5rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
            border-left: 4px solid #e67e22;
        }

        .experience-item h3 {
            color: #2c3e50;
            margin-bottom: 0.5rem;
            font-size: 1.4rem;
        }

        .experience-item .role {
            color: #e67e22;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .experience-item p {
            color: #666;
            line-height: 1.6;
        }

        /* Education Section */
        .education-card {
            background: linear-gradient(135deg, #f9e79f 0%, #f39c12 100%);
            padding: 2.5rem;
            border-radius: 15px;
            color: white;
            text-align: center;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
        }

        .education-card h3 {
            font-size: 1.8rem;
            margin-bottom: 1rem;
        }

        .education-card p {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        /* Contact Section */
        .contact {
            background: linear-gradient(135deg, #f9e79f 0%, #f39c12 50%, #e67e22 100%);
            color: white;
            text-align: center;
        }

        .contact h2 {
            color: white;
        }

        .contact h2::after {
            background: white;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 1rem;
            background: rgba(255,255,255,0.1);
            padding: 1rem 2rem;
            border-radius: 50px;
            backdrop-filter: blur(10px);
        }

        .contact-item i {
            font-size: 1.5rem;
        }

        .contact-item a {
            color: white;
            text-decoration: none;
            font-weight: 500;
        }

        /* Animations */
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
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .profile-image {
                width: 200px;
                height: 200px;
                font-size: 3rem;
            }

            .contact-info {
                flex-direction: column;
                align-items: center;
            }

            .cta-button {
                display: block;
                margin: 10px auto;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">Sundas Saleem</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#education">Education</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="floating-shapes">
            <div class="shape"></div>
            <div class="shape"></div>
            <div class="shape"></div>
        </div>
        <div class="hero-content">
            <h1>Sundas Saleem</h1>
            <p class="subtitle">BDS Student & Graphic Designer</p>
            <p class="description">Passionate about preventive dentistry and creative design</p>
            <a href="#about" class="cta-button">Discover My Work</a>
            <a href="#contact" class="cta-button">Get In Touch</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
        <h2>About Me</h2>
        <div class="about-content">
            <div class="profile-image">
                <i class="fas fa-user"></i>
            </div>
            <div class="about-text">
                <h3>Hello, I'm Sundas!</h3>
                <p>I'm a dedicated 3rd year BDS student with a passion for both dentistry and creative design. My journey combines the precision of dental science with the creativity of graphic design, allowing me to bring a unique perspective to both fields.</p>
                <p>I specialize in preventive dentistry research and have experience creating visual designs for medical conferences. My goal is to contribute to dental health awareness through both clinical practice and effective visual communication.</p>
                <p>When I'm not studying or designing, I enjoy exploring new research methodologies and staying updated with the latest trends in both dentistry and design.</p>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section">
        <h2>My Skills & Expertise</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <h3><i class="fas fa-tooth"></i> Preventive Dentistry Research</h3>
                <p>Conducting comprehensive research on preventive dental care methods, oral health promotion strategies, and community dental health initiatives.</p>
            </div>
            <div class="skill-card">
                <h3><i class="fas fa-palette"></i> Graphic Design</h3>
                <p>Creating visual content for medical conferences, educational materials, and professional presentations with a focus on healthcare communication.</p>
            </div>
            <div class="skill-card">
                <h3><i class="fas fa-heart-pulse"></i> Basic Life Support</h3>
                <p>Certified in Basic Life Support techniques, ensuring preparedness for emergency medical situations in clinical settings.</p>
            </div>
            <div class="skill-card">
                <h3><i class="fas fa-database"></i> Research Tools</h3>
                <p>Proficient in Zotero for reference management and SPSS for statistical analysis, essential tools for academic research and data interpretation.</p>
            </div>
            <div class="skill-card">
                <h3><i class="fas fa-users"></i> Leadership & Community Service</h3>
                <p>Active involvement in student societies and social welfare initiatives, demonstrating leadership skills and commitment to community health.</p>
            </div>
            <div class="skill-card">
                <h3><i class="fas fa-droplet"></i> Blood Donation Advocacy</h3>
                <p>Leading blood donation campaigns and health awareness programs as class representative of the blood wing in social welfare society.</p>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="section">
        <h2>Experience & Leadership</h2>
        <div class="experience-item">
            <h3>Undergraduate Medical Research (UMR)</h3>
            <div class="role">Graphic Designer</div>
            <p>Served as graphic designer and designed the official mascot for the undergraduate medical research conference in 2023, creating a memorable visual identity for the event.</p>
        </div>
        <div class="experience-item">
            <h3>Social Welfare Society - Peshawar Medical College</h3>
            <div class="role">Class Representative - Blood Wing (Current) | Member (2023)</div>
            <p>Currently serving as class representative for the blood wing of the social welfare society. Previously served as a member in 2023, contributing to community health initiatives and blood donation campaigns.</p>
        </div>
        <div class="experience-item">
            <h3>Young Intellects Society - Peshawar</h3>
            <div class="role">Member (2 Years)</div>
            <p>Active member of this student-based society in Peshawar for 2 years, participating in intellectual discussions, academic events, and knowledge-sharing initiatives within the student community.</p>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="section">
        <h2>Education</h2>
        <div class="education-card">
            <h3><i class="fas fa-graduation-cap"></i> Bachelor of Dental Surgery (BDS)</h3>
            <p>Currently in 3rd Year</p>
            <p>Specializing in comprehensive dental care with a focus on preventive dentistry and oral health research</p>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact section">
        <h2>Get In Touch</h2>
        <p>Let's connect and explore opportunities in dentistry, research, or design</p>
        <div class="contact-info">
            <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <a href="mailto:sundassaleem3232@gmail.com">sundassaleem3232@gmail.com</a>
            </div>
            <div class="contact-item">
                <i class="fas fa-user-md"></i>
                <span>BDS Student & Designer</span>
            </div>
        </div>
    </section>

    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Navbar background change on scroll
        window.addEventListener('scroll', function() {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(255, 255, 255, 0.98)';
                navbar.style.boxShadow = '0 2px 20px rgba(0,0,0,0.1)';
            } else {
                navbar.style.background = 'rgba(255, 255, 255, 0.95)';
                navbar.style.boxShadow = 'none';
            }
        });

        // Add animation to skill cards on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // Observe skill cards and experience items
        document.querySelectorAll('.skill-card, .experience-item').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
