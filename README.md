<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IronGuard Cane Corso | Elite Italian Mastiffs</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700;900&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #c5a059;
            --primary-dark: #a4823f;
            --bg-dark: #121212;
            --bg-card: #1a1a1a;
            --bg-lighter: #222222;
            --text-main: #e0e0e0;
            --text-muted: #999999;
            --white: #ffffff;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background-color: var(--bg-dark);
            color: var(--text-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Cinzel', serif;
            letter-spacing: 1px;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            width: 100%;
        }

        /* Header & Navigation */
        header {
            background-color: rgba(18, 18, 18, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(197, 160, 89, 0.2);
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
        }

        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 80px;
        }

        .logo {
            font-family: 'Cinzel', serif;
            font-size: 20px;
            font-weight: 700;
            color: var(--white);
            display: flex;
            align-items: center;
            gap: 10px;
            letter-spacing: 1px;
        }

        .logo span {
            color: var(--primary);
        }

        .nav-links {
            display: flex;
            gap: 25px;
            align-items: center;
        }

        .nav-links a {
            font-weight: 500;
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: var(--text-main);
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .btn {
            background-color: var(--primary);
            color: var(--bg-dark);
            padding: 10px 24px;
            border-radius: 4px;
            font-weight: 600;
            font-size: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            display: inline-block;
            text-align: center;
        }

        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
        }

        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 24px;
            color: var(--white);
            background: none;
            border: none;
        }

        /* Hero Section */
        .hero {
            padding: 150px 0 100px;
            background: linear-gradient(rgba(18, 18, 18, 0.8), rgba(18, 18, 18, 0.95)), 
                        url('https://images.unsplash.com/photo-1600804340584-c7db2eacf0bf?auto=format&fit=crop&w=1600&q=80') no-repeat center center/cover;
            min-height: 90vh;
            display: flex;
            align-items: center;
        }

        .hero-grid {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 40px;
            align-items: center;
        }

        .hero-content h1 {
            font-size: 44px;
            color: var(--white);
            margin-bottom: 20px;
            line-height: 1.1;
        }

        .hero-content h1 span {
            color: var(--primary);
        }

        .hero-content p {
            color: var(--text-muted);
            font-size: 15px;
            margin-bottom: 30px;
        }

        .hero-btns {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
            padding: 8px 22px;
            border-radius: 4px;
            font-weight: 600;
            font-size: 12px;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: var(--transition);
            display: inline-block;
            text-align: center;
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: var(--bg-dark);
        }

        .hero-badge {
            background: rgba(26, 26, 26, 0.85);
            border: 1px solid rgba(197, 160, 89, 0.3);
            padding: 25px;
            border-radius: 8px;
            backdrop-filter: blur(10px);
        }

        .hero-badge h3 {
            color: var(--primary);
            font-size: 18px;
            margin-bottom: 10px;
        }

        .hero-badge p {
            font-size: 13px;
            color: var(--text-muted);
            margin: 0;
        }

        /* Section Layouts */
        .section-padding {
            padding: 90px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 32px;
            color: var(--white);
            margin-bottom: 15px;
        }

        .section-title p {
            color: var(--text-muted);
            max-width: 600px;
            margin: 0 auto;
            font-size: 14px;
        }

        /* Features / Traits Grid */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .feature-card {
            background: var(--bg-card);
            border: 1px solid rgba(255, 255, 255, 0.05);
            padding: 35px 25px;
            border-radius: 8px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: var(--primary);
            transform: scaleX(0);
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-5px);
            border-color: rgba(197, 160, 89, 0.3);
        }

        .feature-card:hover::before {
            transform: scaleX(1);
        }

        .feature-card i {
            font-size: 32px;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 18px;
            margin-bottom: 12px;
            color: var(--white);
        }

        .feature-card p {
            color: var(--text-muted);
            font-size: 13px;
        }

        /* Bloodline / Gallery */
        .gallery-section {
            background-color: var(--bg-card);
            border-top: 1px solid rgba(255, 255, 255, 0.03);
            border-bottom: 1px solid rgba(255, 255, 255, 0.03);
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .gallery-item {
            background: var(--bg-lighter);
            border-radius: 8px;
            overflow: hidden;
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: var(--transition);
        }

        .gallery-item:hover {
            transform: translateY(-5px);
            border-color: var(--primary);
        }

        .gallery-img {
            height: 260px;
            width: 100%;
            object-fit: cover;
        }

        .gallery-info {
            padding: 20px;
        }

        .gallery-info h3 {
            font-size: 17px;
            color: var(--white);
            margin-bottom: 6px;
        }

        .gallery-info p {
            color: var(--primary);
            font-weight: 500;
            font-size: 12px;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        /* Standards Section */
        .standards-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .standards-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .standard-item {
            display: flex;
            gap: 15px;
            align-items: flex-start;
        }

        .standard-icon {
            background-color: var(--bg-card);
            color: var(--primary);
            border: 1px solid rgba(197, 160, 89, 0.2);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
            font-size: 18px;
        }

        .standard-text h3 {
            font-size: 17px;
            color: var(--white);
            margin-bottom: 4px;
        }

        .standard-text p {
            color: var(--text-muted);
            font-size: 13px;
        }

        .standards-image img {
            width: 100%;
            border-radius: 8px;
            border: 1px solid rgba(197, 160, 89, 0.2);
            box-shadow: 0 15px 30px rgba(0,0,0,0.5);
            height: 400px;
            object-fit: cover;
        }

        /* Contact Section */
        .contact-section {
            background: linear-gradient(135deg, var(--bg-card) 0%, var(--bg-dark) 100%);
        }

        .contact-form {
            max-width: 700px;
            margin: 0 auto;
            background: var(--bg-dark);
            padding: 40px;
            border-radius: 10px;
            border: 1px solid rgba(197, 160, 89, 0.2);
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }

        .form-control {
            width: 100%;
            padding: 14px;
            background: var(--bg-card);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 6px;
            color: var(--white);
            font-family: 'Plus Jakarta Sans', sans-serif;
            font-size: 13px;
            outline: none;
            transition: var(--transition);
        }

        .form-control:focus {
            border-color: var(--primary);
            background: var(--bg-lighter);
        }

        .form-control::placeholder {
            color: #666;
        }

        textarea.form-control {
            resize: vertical;
            height: 120px;
        }

        .contact-form .btn {
            width: 100%;
            padding: 14px;
            font-size: 13px;
        }

        /* Footer */
        footer {
            background-color: var(--bg-dark);
            color: var(--text-muted);
            padding: 30px 0;
            text-align: center;
            font-size: 12px;
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        footer p span {
            color: var(--primary);
        }

        /* Responsive Media Queries */
        @media (max-width: 992px) {
            .hero-grid, .standards-grid {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .hero-btns {
                justify-content: center;
            }

            .features-grid, .gallery-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .standard-item {
                flex-direction: column;
                align-items: center;
                text-align: center;
            }

            .standards-image img {
                height: 300px;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 80px;
                left: 0;
                width: 100%;
                background: var(--bg-dark);
                padding: 25px 0;
                border-bottom: 1px solid rgba(197, 160, 89, 0.2);
                text-align: center;
                gap: 20px;
                box-shadow: 0 10px 20px rgba(0,0,0,0.5);
            }

            .nav-links.active {
                display: flex;
            }

            .hamburger {
                display: block;
            }

            .features-grid, .gallery-grid, .form-row {
                grid-template-columns: 1fr;
            }

            .hero {
                padding: 130px 0 70px;
                min-height: auto;
            }

            .hero-content h1 {
                font-size: 32px;
            }
            
            .contact-form {
                padding: 20px;
            }

            .section-title h2 {
                font-size: 26px;
            }
        }
    </style>
</head>
<body>

    <!-- Header -->
    <header>
        <div class="container nav-container">
            <a href="#" class="logo"><i class="fa-solid fa-shield-dog"></i>IronGuard <span>Cane Corso</span></a>
            <nav>
                <ul class="nav-links" id="navLinks">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#traits">Traits</a></li>
                    <li><a href="#bloodline">Bloodline</a></li>
                    <li><a href="#standards">Standards</a></li>
                    <li><a href="#contact" class="btn">Reserve Puppy</a></li>
                </ul>
            </nav>
            <button class="hamburger" id="hamburger" aria-label="Toggle Navigation">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container hero-grid">
            <div class="hero-content">
                <h1>The Ultimate Guardian: <span>Royalty & Strength</span></h1>
                <p>Welcome to IronGuard Cane Corso. We breed exceptional Italian Mastiffs characterized by unrivaled loyalty, regal stature, and noble protection instincts.</p>
                <div class="hero-btns">
                    <a href="#bloodline" class="btn">View Bloodline</a>
                    <a href="#contact" class="btn-outline">Inquire Now</a>
                </div>
            </div>
            <div class="hero-badge">
                <h3>Elite Italian Bloodlines</h3>
                <p>Meticulously bred for structural soundness, stable temperament, and traditional working conformation.</p>
            </div>
        </div>
    </section>

    <!-- Traits Section -->
    <section class="section-padding" id="traits">
        <div class="container">
            <div class="section-title">
                <h2>The Cane Corso Legacy</h2>
                <p>A powerful apex protector possessing intelligence, confidence, and intense devotion to family.</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <i class="fa-solid fa-shield-halved"></i>
                    <h3>Supreme Protection</h3>
                    <p>Natural guard dogs with an innate sense of territory, offering unmatched security and watchfulness.</p>
                </div>
                <div class="feature-card">
                    <i class="fa-solid fa-brain"></i>
                    <h3>High Intelligence</h3>
                    <p>Highly trainable and eager to work, responding exceptionally well to consistent, confident leadership.</p>
                </div>
                <div class="feature-card">
                    <i class="fa-solid fa-heart"></i>
                    <h3>Family Devotion</h3>
                    <p>Deeply affectionate and gentle with family members, forming an unbreakable bond with their owners.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Bloodline / Gallery -->
    <section class="section-padding gallery-section" id="bloodline">
        <div class="container">
            <div class="section-title">
                <h2>Sire & Dam Showcase</h2>
                <p>Inspect our premier adult lines and upcoming champion litters.</p>
            </div>
            <div class="gallery-grid">
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1629851722915-467aef34d28d?auto=format&fit=crop&w=600&q=80" alt="Cane Corso Sire" class="gallery-img">
                    <div class="gallery-info">
                        <h3>Titan (Sire)</h3>
                        <p>Black Brindle • Champion Line</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1543466835-00a7907e9de1?auto=format&fit=crop&w=600&q=80" alt="Cane Corso Dam" class="gallery-img">
                    <div class="gallery-info">
                        <h3>Athena (Dam)</h3>
                        <p>Formentino • Imported Bloodline</p>
                    </div>
                </div>
                <div class="gallery-item">
                    <img src="https://images.unsplash.com/photo-1583511655857-d19b40a7a54e?auto=format&fit=crop&w=600&q=80" alt="Cane Corso Puppy" class="gallery-img">
                    <div class="gallery-info">
                        <h3>Current Litter</h3>
                        <p>Available for Reservation</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Breed Standards Section -->
    <section class="section-padding" id="standards">
        <div class="container">
            <div class="standards-grid">
                <div class="standards-list">
                    <div class="section-title" style="text-align: left; margin-bottom: 25px;">
                        <h2>Breeding Standards</h2>
                        <p style="margin: 0; text-align: left;">We uphold rigorous health and genetic criteria to preserve the integrity of the breed.</p>
                    </div>
                    <div class="standard-item">
                        <div class="standard-icon"><i class="fa-solid fa-notes-medical"></i></div>
                        <div class="standard-text">
                            <h3>Health Clearances</h3>
                            <p>Rigorous veterinary screenings including hip and elbow evaluations, and cardiac clearances.</p>
                        </div>
                    </div>
                    <div class="standard-item">
                        <div class="standard-icon"><i class="fa-solid fa-users-viewfinder"></i></div>
                        <div class="standard-text">
                            <h3>Early Socialization</h3>
                            <p>Puppies are exposed to various environments, sounds, and stimuli from early weeks for balanced nerves.</p>
                        </div>
                    </div>
                    <div class="standard-item">
                        <div class="standard-icon"><i class="fa-solid fa-file-contract"></i></div>
                        <div class="standard-text">
                            <h3>Pedigree Registration</h3>
                            <p>Full certified pedigree documentation provided with health guarantees for every puppy.</p>
                        </div>
                    </div>
                </div>
                <div class="standards-image">
                    <img src="https://images.unsplash.com/photo-1561585973-206e12488a03?auto=format&fit=crop&w=800&q=80" alt="Cane Corso Guard">
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="section-padding contact-section" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Reservation & Inquiry</h2>
                <p>Secure a spot for our upcoming litters or schedule a kennel consultation.</p>
            </div>
            <form class="contact-form" onsubmit="event.preventDefault(); alert('Your reservation inquiry has been sent successfully. We will contact you soon.');">
                <div class="form-row">
                    <div class="form-group">
                        <input type="text" class="form-control" placeholder="Full Name" required>
                    </div>
                    <div class="form-group">
                        <input type="email" class="form-control" placeholder="Email Address" required>
                    </div>
                </div>
                <div class="form-group">
                    <input type="text" class="form-control" placeholder="Phone Number / Location">
                </div>
                <div class="form-group">
                    <textarea class="form-control" placeholder="Tell us about your experience with large breeds or inquiry details..." required></textarea>
                </div>
                <button type="submit" class="btn">Submit Reservation Request</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p>&copy; 2026 IronGuard Cane Corso. All Rights Reserved. Designed for elite protection by <span>Prime Solutions</span>.</p>
        </div>
    </footer>

    <!-- JavaScript for Mobile Menu -->
    <script>
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });
    </script>
</body>
</html>
