<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Professional Portfolio</title>
    <style>
        /* Global Styles */
        :root {
            --primary-color: #3498db;
            --secondary-color: #2c3e50;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --text-color: #333;
            --text-light: #7f8c8d;
            --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-color);
            background-color: #f9f9f9;
        }

        a {
            text-decoration: none;
            color: var(--primary-color);
            transition: var(--transition);
        }

        a:hover {
            color: var(--accent-color);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--secondary-color);
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--primary-color);
            margin: 15px auto;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-size: 0.9rem;
        }

        .btn:hover {
            background: var(--accent-color);
            color: white;
            transform: translateY(-3px);
            box-shadow: var(--box-shadow);
        }

        /* Header & Navigation */
        header {
            background-color: white;
            box-shadow: var(--box-shadow);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--secondary-color);
        }

        .logo span {
            color: var(--primary-color);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: var(--dark-color);
            font-weight: 600;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--primary-color);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        /* Hero Section */
        #hero {
            height: 100vh;
            display: flex;
            align-items: center;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            color: white;
            text-align: center;
            padding-top: 80px;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero-content p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: rgba(255, 255, 255, 0.8);
        }

        .hero-btns {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .hero-btns .btn {
            margin: 0 10px;
        }

        .hero-btns .btn-outline {
            background: transparent;
            border: 2px solid white;
        }

        .hero-btns .btn-outline:hover {
            background: white;
            color: var(--dark-color);
        }

        /* About Section */
        #about {
            background-color: white;
        }

        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .about-img {
            flex: 1;
            text-align: center;
        }

        .about-img img {
            width: 100%;
            max-width: 400px;
            border-radius: 10px;
            box-shadow: var(--box-shadow);
        }

        .about-text {
            flex: 1;
        }

        .about-text h3 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: var(--secondary-color);
        }

        .about-text p {
            margin-bottom: 15px;
            color: var(--text-light);
        }

        .personal-info {
            margin-top: 30px;
        }

        .info-item {
            display: flex;
            margin-bottom: 10px;
        }

        .info-item span:first-child {
            font-weight: 600;
            width: 120px;
            display: inline-block;
            color: var(--secondary-color);
        }

        .hobbies {
            margin-top: 30px;
        }

        .hobbies h4 {
            margin-bottom: 15px;
            color: var(--secondary-color);
        }

        .hobbies-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .hobby-item {
            background: var(--light-color);
            padding: 8px 15px;
            border-radius: 30px;
            font-size: 0.9rem;
        }

        /* Skills Section */
        #skills {
            background-color: var(--light-color);
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: var(--box-shadow);
        }

        .skill-category h3 {
            margin-bottom: 20px;
            color: var(--secondary-color);
            text-align: center;
        }

        .skill-item {
            margin-bottom: 15px;
        }

        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }

        .skill-bar {
            height: 10px;
            background: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: var(--primary-color);
            border-radius: 5px;
            transition: width 1s ease-in-out;
        }

        /* Projects Section */
        #projects {
            background-color: white;
        }

        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .project-img {
            height: 200px;
            overflow: hidden;
        }

        .project-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-img img {
            transform: scale(1.1);
        }

        .project-content {
            padding: 20px;
        }

        .project-content h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }

        .project-content p {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 15px;
        }

        .project-tag {
            background: var(--light-color);
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 0.8rem;
            color: var(--text-light);
        }

        .project-links {
            display: flex;
            gap: 15px;
        }

        .project-links a {
            font-size: 0.9rem;
            font-weight: 600;
        }

        /* Certifications Section */
        #certifications {
            background-color: var(--light-color);
        }

        .certifications-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .certification-card {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
        }

        .certification-card:hover {
            transform: translateY(-5px);
        }

        .certification-card h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }

        .certification-card p {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .certification-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.9rem;
            color: var(--text-light);
            margin-bottom: 15px;
        }

        .certification-card .btn {
            padding: 8px 20px;
            font-size: 0.8rem;
        }

        /* Experience Section */
        #experience {
            background-color: white;
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background: var(--primary-color);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            box-sizing: border-box;
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: white;
            border: 4px solid var(--primary-color);
            border-radius: 50%;
            top: 15px;
            z-index: 1;
        }

        .left {
            left: 0;
        }

        .right {
            left: 50%;
        }

        .left::after {
            right: -12px;
        }

        .right::after {
            left: -12px;
        }

        .timeline-content {
            padding: 20px;
            background: var(--light-color);
            border-radius: 10px;
            box-shadow: var(--box-shadow);
        }

        .timeline-content h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }

        .timeline-content h4 {
            margin-bottom: 10px;
            color: var(--primary-color);
            font-size: 1rem;
        }

        .timeline-content p {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .timeline-date {
            color: var(--accent-color);
            font-weight: 600;
            font-size: 0.9rem;
        }

        /* Competitive Programming Section */
        #competitive-programming {
            background-color: var(--light-color);
        }

        .cp-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
        }

        .cp-card {
            background: white;
            border-radius: 10px;
            padding: 30px;
            box-shadow: var(--box-shadow);
            text-align: center;
            transition: var(--transition);
        }

        .cp-card:hover {
            transform: translateY(-5px);
        }

        .cp-card i {
            font-size: 3rem;
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        .cp-card h3 {
            margin-bottom: 15px;
            color: var(--secondary-color);
        }

        .cp-card p {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .cp-stats {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
        }

        .cp-stat {
            text-align: center;
        }

        .cp-stat h4 {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 5px;
        }

        .cp-stat p {
            font-size: 0.8rem;
            color: var(--text-light);
        }

        /* Open Source Section */
        #open-source {
            background-color: white;
        }

        .os-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .os-item {
            background: var(--light-color);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
            box-shadow: var(--box-shadow);
        }

        .os-item h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }

        .os-item p {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .os-meta {
            display: flex;
            gap: 15px;
            font-size: 0.9rem;
            color: var(--text-light);
        }

        /* Blog Section */
        #blog {
            background-color: var(--light-color);
        }

        .blog-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .blog-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
        }

        .blog-card:hover {
            transform: translateY(-5px);
        }

        .blog-img {
            height: 200px;
            overflow: hidden;
        }

        .blog-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .blog-card:hover .blog-img img {
            transform: scale(1.1);
        }

        .blog-content {
            padding: 20px;
        }

        .blog-content h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }

        .blog-content p {
            color: var(--text-light);
            margin-bottom: 15px;
            font-size: 0.9rem;
        }

        .blog-meta {
            display: flex;
            justify-content: space-between;
            font-size: 0.8rem;
            color: var(--text-light);
            margin-bottom: 15px;
        }

        /* Research Section */
        #research {
            background-color: white;
        }

        .research-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .research-item {
            background: var(--light-color);
            padding: 30px;
            border-radius: 10px;
            margin-bottom: 30px;
            box-shadow: var(--box-shadow);
        }

        .research-item h3 {
            margin-bottom: 15px;
            color: var(--secondary-color);
        }

        .research-item p {
            color: var(--text-light);
            margin-bottom: 15px;
        }

        .research-meta {
            display: flex;
            gap: 20px;
            font-size: 0.9rem;
            color: var(--text-light);
            margin-bottom: 15px;
        }

        /* Contact Section */
        #contact {
            background-color: var(--light-color);
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 50px;
        }

        .contact-info {
            margin-bottom: 30px;
        }

        .contact-info h3 {
            margin-bottom: 20px;
            color: var(--secondary-color);
        }

        .contact-details {
            margin-bottom: 30px;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }

        .contact-icon {
            margin-right: 15px;
            color: var(--primary-color);
            font-size: 1.2rem;
        }

        .contact-text h4 {
            margin-bottom: 5px;
            color: var(--secondary-color);
        }

        .contact-text p, .contact-text a {
            color: var(--text-light);
            font-size: 0.9rem;
        }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-link {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--primary-color);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .social-link:hover {
            background: var(--accent-color);
            transform: translateY(-3px);
        }

        .contact-form .form-group {
            margin-bottom: 20px;
        }

        .contact-form label {
            display: block;
            margin-bottom: 5px;
            color: var(--secondary-color);
            font-weight: 600;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-family: inherit;
            transition: var(--transition);
        }

        .contact-form input:focus,
        .contact-form textarea:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
        }

        .contact-form textarea {
            height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background: var(--secondary-color);
            color: white;
            text-align: center;
            padding: 30px 0;
        }

        .footer-content p {
            margin-bottom: 20px;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            list-style: none;
            margin-bottom: 20px;
        }

        .footer-links li {
            margin: 0 15px;
        }

        .footer-links a {
            color: white;
        }

        .footer-links a:hover {
            color: var(--primary-color);
        }

        .copyright {
            font-size: 0.9rem;
            color: rgba(255, 255, 255, 0.7);
        }

        /* Back to Top Button */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            width: 50px;
            height: 50px;
            background: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2rem;
            cursor: pointer;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
            z-index: 999;
        }

        .back-to-top.active {
            opacity: 1;
            visibility: visible;
        }

        .back-to-top:hover {
            background: var(--accent-color);
            transform: translateY(-5px);
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .about-content {
                flex-direction: column;
            }

            .about-img, .about-text {
                flex: none;
                width: 100%;
            }

            .about-img {
                margin-bottom: 30px;
            }

            .timeline::after {
                left: 31px;
            }

            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }

            .timeline-item::after {
                left: 21px;
            }

            .left::after, .right::after {
                left: 21px;
            }

            .right {
                left: 0;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 80px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 80px);
                background: white;
                flex-direction: column;
                align-items: center;
                padding: 50px 0;
                transition: var(--transition);
            }

            .nav-links.active {
                left: 0;
            }

            .nav-links li {
                margin: 15px 0;
            }

            .hamburger {
                display: block;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-btns {
                flex-direction: column;
                align-items: center;
            }

            .hero-btns .btn {
                margin: 10px 0;
                width: 80%;
            }

            .section-title h2 {
                font-size: 2rem;
            }

            .contact-container {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 576px) {
            .projects-container, .certifications-container, .blog-container {
                grid-template-columns: 1fr;
            }

            .cp-stats {
                flex-direction: column;
                gap: 15px;
            }

            .footer-links {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">Port<span>folio</span></div>
                <ul class="nav-links">
                    <li><a href="#hero">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#experience">Experience</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="hero">
        <div class="container">
            <div class="hero-content">
                <h1>Hi, I'm Bipeen kumar<span id="typed-name"></span></h1>
                <p id="typed-text"></p>
                <div class="hero-btns">
                    
                    <a href="#about" class="btn btn-outline">About Me</a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <div class="container">
            <div class="section-title">
                <h2>About Me</h2>
            </div>
            <div class="about-content">
                <div class="about-img">
                    <img src="profilecv1.jpeg" alt="Profile Picture" id="profile-pic">
                </div>
                <div class="about-text">
                    <h3>Introduction & Summary</h3>
                    <p>I am a passionate and dedicated professional with expertise in web development, software engineering, and problem-solving. With a strong foundation in computer science and hands-on experience in various technologies, I strive to create innovative solutions to complex problems.</p>
                    <p>My journey in technology began during my college years, and since then, I've been constantly learning and growing. I believe in the power of technology to transform lives and businesses, and I'm committed to being part of that transformation.</p>
                    
                    <div class="personal-info">
                        <div class="info-item">
                            <span>Name:</span>
                            <span id="info-name">Bipeen Kumar</span>
                        </div>
                        <div class="info-item">
                            <span>Email:</span>
                            <span id="info-email">Bipeenswaraj@gmail.com</span>
                        </div>
                        <div class="info-item">
                            <span>Phone:</span>
                            <span id="info-phone">+91 7992334744</span>
                        </div>
                        <div class="info-item">
                            <span>Education:</span>
                            <span id="info-education">B.TECH. in Computer Science</span>
                        </div>
                        <div class="info-item">
                            <span>Location:</span>
                            <span id="info-location">Patna, Bihar </span>
                        </div>
                    </div>
                    
                    <div class="hobbies">
                        <h4>Hobbies & Interests</h4>
                        <div class="hobbies-list" id="hobbies-list">
                            <!-- Hobbies will be added by JavaScript -->
                        </div>
                    </div>
                    
                    <a href="bipeencv.pdf" class="btn" downloadtarget="_blank" id="resume-download">View Resume</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="container">
            <div class="section-title">
                <h2>Skills & Technologies</h2>
            </div>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>Frontend Development</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>HTML5</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>CSS3</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>Backend Development</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Node.js</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Kotlin</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>C++</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>SQL</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>Other Skills</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Git</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Tableau</span>
                            <span>70%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 70%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>AWS</span>
                            <span>65%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 65%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Big Data</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
	<section id="projects">
                    <div class="certification-card">
                    <h3>Introduction to Large Language Model</h3>
                    <div class="certification-meta">
                        <span><i class="fas fa-university"></i> Google Cloud</span>
                        <span><i class="far fa-calendar-alt"></i> 2023</span>
                    </div>
                    <p>Developed practical skills in leveraging LLMs for real-world tasks such as summarization, classification, and question-answering.</p>
                    <a href="certificate4.pdf" class="btn">View Certificate</a>
                </div>
				<div class="certification-card">
                    <h3>Generative Ai Primer</h3>
                    <div class="certification-meta">
                        <span><i class="fas fa-university"></i>Vanderbilt University</span>
                        <span><i class="far fa-calendar-alt"></i> 2023</span>
                    </div>
                    <p>gained foundational knowledge of generative AI concepts, models, and ethical considerations.</p>
                    <a href="certificate5.pdf" class="btn">View Certificate</a>
                </div>
				
            </div>
        </div>
    </section>

    

    <!-- Competitive Programming Section -->
    <section id="competitive-programming">
        <div class="container">
            <div class="section-title">
                <h2>Competitive Programming & Hackathons</h2>
            </div>
            <div class="cp-container">
                
                <div class="cp-card">
                    <i class="fas fa-laptop-code"></i>
                    <h3>LeetCode</h3>
                    <p>Solved 100+ problems across various difficulty levels with focus on algorithms and data structures.</p>
                    <div class="cp-stats">
                        <div class="cp-stat">
                            <h4>100+</h4>
                            <p>Problems Solved</p>
                        </div>
                        <div class="cp-stat">
                            <h4>60%</h4>
                            <p>Contest Attendance</p>
                        </div>
                    </div>
                </div>
                
                <div class="cp-card">
                    <i class="fas fa-users"></i>
                    <h3>Hackathons</h3>
                    <p>Participated in 5+ hackathons, winning 1 awards for innovative technical solutions.</p>
                    <div class="cp-stats">
                        <div class="cp-stat">
                            <h4>1</h4>
                            <p>Wins</p>
                        </div>
                        <div class="cp-stat">
                            <h4>5+</h4>
                            <p>Participations</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

 

  

    <!-- Research Section -->
    <section id="research">
        <div class="container">
            <div class="section-title">
                <h2>Extra Curriculum Activities</h2>
            </div>
            <div class="research-container">
                <div class="research-item">
                    <h3>Runner up in Nukkad natak competition </h3>
                    <div class="research-meta">
                        <span><i class="fas fa-book"></i> Play on social issues</span>
                        <span><i class="far fa-calendar-alt"></i> 2023</span>
                        <span><i class="fas fa-link"></i> DOE: 10/05/2023</span>
                    </div>
                    <p></p>
                    
                </div>
                
                <div class="research-item">
                    <h3> Best Speaker Award</h3>
                    <div class="research-meta">
                        <span><i class="fas fa-book"></i>got best speaker award in public debate on social topics. </span>
                        <span><i class="far fa-calendar-alt"></i> 2023</span>
                        <span><i class="fas fa-link"></i> DOE: 10/09/2023</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contact Me</h2>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Get In Touch</h3>
                    <div class="contact-details">
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-map-marker-alt"></i>
                            </div>
                            <div class="contact-text">
                                <h4>Location</h4>
                                <p>Patna, Bihar</p>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-envelope"></i>
                            </div>
                            <div class="contact-text">
                                <h4>Email</h4>
                                <a href="bipeenswaraj@gmail.com">bipeenswaraj@gmail.com</a>
                            </div>
                        </div>
                        
                        <div class="contact-item">
                            <div class="contact-icon">
                                <i class="fas fa-phone-alt"></i>
                            </div>
                            <div class="contact-text">
                                <h4>Phone</h4>
                                <a href="tel:+11234567890">+91 7992334744 </a>
                            </div>
                        </div>
                    </div>
                    
                    <h3>Follow Me</h3>
                    <div class="social-links">
                        <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-medium-m"></i></a>
                        <a href="#" class="social-link"><i class="fab fa-stack-overflow"></i></a>
                    </div>
                </div>
                
                <div class="contact-form">
                    <h3>Send Me a Message</h3>
                    <form id="contactForm">
                        <div class="form-group">
                            <label for="name">Name</label>
                            <input type="text" id="name" name="name" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Email</label>
                            <input type="email" id="email" name="email" required>
                        </div>
                        <div class="form-group">
                            <label for="subject">Subject</label>
                            <input type="text" id="subject" name="subject" required>
                        </div>
                        <div class="form-group">
                            <label for="message">Message</label>
                            <textarea id="message" name="message" required></textarea>
                        </div>
                        <button type="submit" class="btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <p>Let's work together to build something amazing!</p>
                <ul class="footer-links">
                    <li><a href="#hero">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="copyright">
                    <p>&copy; <span id="current-year"></span> bipeenkumar. All rights reserved.</p>
                </div>
            </div>
        </div>
    </footer>

    <!-- Back to Top Button -->
    <div class="back-to-top">
        <i class="fas fa-arrow-up"></i>
    </div>

    <!-- JavaScript -->
    <script>
        // Mobile Navigation
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.innerHTML = navLinks.classList.contains('active') ? 
                '<i class="fas fa-times"></i>' : '<i class="fas fa-bars"></i>';
        });
        
        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.innerHTML = '<i class="fas fa-bars"></i>';
            });
        });
        
        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // Sticky header on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            header.classList.toggle('sticky', window.scrollY > 0);
        });
        
        // Typing animation for hero section
        const typedName = document.getElementById('typed-name');
        const typedText = document.getElementById('typed-text');
        
        const name = 'John Doe';
        const titles = [
            'a Full Stack Developer',
            'a Problem Solver',
            'a Tech Enthusiast',
            'a Continuous Learner'
        ];
        
        let nameIndex = 0;
        let titleIndex = 0;
        let isTyping = true;
        let isDeleting = false;
        let currentText = '';
        
        function typeName() {
            if (nameIndex < name.length) {
                typedName.textContent += name.charAt(nameIndex);
                nameIndex++;
                setTimeout(typeName, 100);
            } else {
                setTimeout(typeTitle, 1000);
            }
        }
        
        function typeTitle() {
            const fullText = titles[titleIndex];
            
            if (isTyping) {
                currentText = fullText.substring(0, currentText.length + 1);
                typedText.textContent = currentText;
                
                if (currentText === fullText) {
                    isTyping = false;
                    setTimeout(typeTitle, 2000);
                } else {
                    setTimeout(typeTitle, 100);
                }
            } else {
                currentText = fullText.substring(0, currentText.length - 1);
                typedText.textContent = currentText;
                
                if (currentText === '') {
                    isTyping = true;
                    titleIndex = (titleIndex + 1) % titles.length;
                    setTimeout(typeTitle, 500);
                } else {
                    setTimeout(typeTitle, 50);
                }
            }
        }
        
        // Initialize typing animation
        setTimeout(typeName, 1000);
        
        // Animate skill bars on scroll
        function animateSkills() {
            const skillBars = document.querySelectorAll('.skill-progress');
            skillBars.forEach(bar => {
                const width = bar.style.width;
                bar.style.width = '0';
                setTimeout(() => {
                    bar.style.width = width;
                }, 100);
            });
        }
        
        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1
        };
        
        const observer = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    if (entry.target.id === 'skills') {
                        animateSkills();
                    }
                    entry.target.classList.add('animated');
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);
        
        // Observe all sections
        document.querySelectorAll('section').forEach(section => {
            observer.observe(section);
        });
        
        // Back to top button
        const backToTopBtn = document.querySelector('.back-to-top');
        
        window.addEventListener('scroll', () => {
            if (window.pageYOffset > 300) {
                backToTopBtn.classList.add('active');
            } else {
                backToTopBtn.classList.remove('active');
            }
        });
        
        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // Current year in footer
        document.getElementById('current-year').textContent = new Date().getFullYear();
        
        // Hobbies list
        const hobbies = [
            'Coding', 'Reading', 'Hiking', 'Photography', 
            'Chess', 'Traveling', 'Music', 'Gaming'
        ];
        
        const hobbiesList = document.getElementById('hobbies-list');
        hobbies.forEach(hobby => {
            const hobbyItem = document.createElement('div');
            hobbyItem.className = 'hobby-item';
            hobbyItem.textContent = hobby;
            hobbiesList.appendChild(hobbyItem);
        });
        
        // Contact form submission
        const contactForm = document.getElementById('contactForm');
        
        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Get form values
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const subject = document.getElementById('subject').value;
            const message = document.getElementById('message').value;
            
            // Here you would typically send the form data to a server
            // For this example, we'll just log it and show an alert
            console.log({ name, email, subject, message });
            
            alert('Thank you for your message! I will get back to you soon.');
            contactForm.reset();
        });
		// Remove all the generateResume() related code and replace with:
document.addEventListener('DOMContentLoaded', function() {
    // Set current year in footer
    document.getElementById('current-year').textContent = new Date().getFullYear();
    
    // Add hobbies
    const hobbies = [
        'Coding', 'Reading Tech Blogs', 'Open Source Contributions',
        'Photography', 'Hiking', 'Chess', 'Music Production'
    ];
    
    const hobbiesList = document.getElementById('hobbies-list');
    hobbies.forEach(hobby => {
        const hobbyItem = document.createElement('div');
        hobbyItem.className = 'hobby-item';
        hobbyItem.textContent = hobby;
        hobbiesList.appendChild(hobbyItem);
    });
    
    // Skill bar animations
    const skillBars = document.querySelectorAll('.skill-progress');
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                const width = entry.target.style.width;
                entry.target.style.width = '0';
                setTimeout(() => {
                    entry.target.style.width = width;
                }, 100);
                observer.unobserve(entry.target);
            }
        });
    }, { threshold: 0.5 });
    
    skillBars.forEach(bar => observer.observe(bar));
});
        
        // Generate a dummy resume PDF (in a real scenario, this would be an actual PDF file)
</html>
	   
