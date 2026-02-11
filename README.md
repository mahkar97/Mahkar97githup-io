index.html<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MK Mart - Aapki Pasandida Dukaan</title>
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

        /* Header & Navigation */
        header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 5%;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            background: white;
            color: #667eea;
            width: 45px;
            height: 45px;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            font-weight: bold;
        }

        nav ul {
            list-style: none;
            display: flex;
            gap: 2rem;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s;
            padding: 8px 16px;
            border-radius: 5px;
        }

        nav ul li a:hover {
            background: rgba(255,255,255,0.2);
        }

        .mobile-menu {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .mobile-menu span {
            width: 25px;
            height: 3px;
            background: white;
            margin: 3px 0;
            border-radius: 3px;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 150px 5% 100px;
            text-align: center;
            margin-top: 70px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg width="100" height="100" xmlns="http://www.w3.org/2000/svg"><circle cx="50" cy="50" r="2" fill="white" opacity="0.1"/></svg>');
            opacity: 0.3;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            animation: fadeInUp 1s ease;
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
            animation: fadeInUp 1s ease 0.2s both;
        }

        .cta-button {
            display: inline-block;
            background: white;
            color: #667eea;
            padding: 15px 40px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            font-size: 1.1rem;
            transition: all 0.3s;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
            animation: fadeInUp 1s ease 0.4s both;
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        /* Features Section */
        .features {
            padding: 80px 5%;
            background: #f8f9fa;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #333;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .feature-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.15);
        }

        .feature-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #667eea;
        }

        /* Products Section */
        .products {
            padding: 80px 5%;
            background: white;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .product-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
        }

        .product-info {
            padding: 1.5rem;
        }

        .product-info h3 {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .product-info p {
            color: #666;
            margin-bottom: 1rem;
        }

        .product-price {
            font-size: 1.5rem;
            color: #667eea;
            font-weight: bold;
        }

        /* About Section */
        .about {
            padding: 80px 5%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
        }

        .about-content {
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
        }

        .about-content h2 {
            font-size: 2.5rem;
            margin-bottom: 2rem;
        }

        .about-content p {
            font-size: 1.2rem;
            line-height: 1.8;
            opacity: 0.95;
        }

        /* Contact Section */
        .contact {
            padding: 80px 5%;
            background: #f8f9fa;
        }

        .contact-container {
            max-width: 800px;
            margin: 0 auto;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .contact-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .contact-card i {
            font-size: 2.5rem;
            color: #667eea;
            margin-bottom: 1rem;
        }

        .contact-card h3 {
            font-size: 1.2rem;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .contact-form {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #333;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #667eea;
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .submit-btn {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px 40px;
            border: none;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s;
            width: 100%;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem 5%;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .social-links {
            margin: 1rem 0;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            margin: 0 1rem;
            transition: all 0.3s;
        }

        .social-links a:hover {
            color: #667eea;
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

        /* Responsive */
        @media (max-width: 768px) {
            nav ul {
                display: none;
                position: absolute;
                top: 70px;
                left: 0;
                right: 0;
                background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
                flex-direction: column;
                padding: 1rem;
                gap: 0;
            }

            nav ul.active {
                display: flex;
            }

            nav ul li {
                margin: 0.5rem 0;
            }

            .mobile-menu {
                display: flex;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }
        }

        /* Scroll Animation */
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">
                <div class="logo-icon">MK</div>
                <span>MK Mart</span>
            </div>
            <ul id="navMenu">
                <li><a href="#home">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="#products">Products</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="mobile-menu" onclick="toggleMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>MK Mart में आपका स्वागत है</h1>
            <p>आपकी हर ज़रूरत का एक ही समाधान - गुणवत्ता, विश्वास और बेहतरीन सेवा</p>
            <a href="#contact" class="cta-button">अभी संपर्क करें</a>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <h2 class="section-title">हमारी विशेषताएं</h2>
        <div class="features-grid">
            <div class="feature-card fade-in">
                <div class="feature-icon">🎯</div>
                <h3>Best Quality</h3>
                <p>हम केवल उच्च गुणवत्ता वाले उत्पाद ही प्रदान करते हैं जो आपकी अपेक्षाओं से बढ़कर हों</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">💰</div>
                <h3>सस्ती कीमतें</h3>
                <p>बाजार में सबसे प्रतिस्पर्धी दरों पर बेहतरीन उत्पाद प्राप्त करें</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">🚚</div>
                <h3>तेज़ डिलीवरी</h3>
                <p>समय पर और सुरक्षित डिलीवरी की गारंटी के साथ</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">🌟</div>
                <h3>विश्वसनीय सेवा</h3>
                <p>हमारे ग्राहकों की संतुष्टि ही हमारी पहली प्राथमिकता है</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">🛡️</div>
                <h3>सुरक्षित खरीदारी</h3>
                <p>100% सुरक्षित और भरोसेमंद लेन-देन की सुविधा</p>
            </div>
            <div class="feature-card fade-in">
                <div class="feature-icon">📞</div>
                <h3>24/7 सपोर्ट</h3>
                <p>किसी भी समय हमसे संपर्क करें, हम हमेशा आपकी मदद के लिए तैयार हैं</p>
            </div>
        </div>
    </section>

    <!-- Products Section -->
    <section class="products" id="products">
        <h2 class="section-title">हमारे प्रोडक्ट्स</h2>
        <div class="products-grid">
            <div class="product-card fade-in">
                <div class="product-image">🛒</div>
                <div class="product-info">
                    <h3>किराना सामान</h3>
                    <p>दैनिक उपयोग की सभी चीज़ें उपलब्ध</p>
                    <div class="product-price">सर्वोत्तम दाम</div>
                </div>
            </div>
            <div class="product-card fade-in">
                <div class="product-image">📱</div>
                <div class="product-info">
                    <h3>इलेक्ट्रॉनिक्स</h3>
                    <p>नवीनतम गैजेट्स और उपकरण</p>
                    <div class="product-price">विशेष छूट</div>
                </div>
            </div>
            <div class="product-card fade-in">
                <div class="product-image">👕</div>
                <div class="product-info">
                    <h3>कपड़े</h3>
                    <p>फैशनेबल और आरामदायक परिधान</p>
                    <div class="product-price">ट्रेंडी कलेक्शन</div>
                </div>
            </div>
            <div class="product-card fade-in">
                <div class="product-image">🏠</div>
                <div class="product-info">
                    <h3>घरेलू सामान</h3>
                    <p>आपके घर को सुंदर बनाने के लिए</p>
                    <div class="product-price">विशाल रेंज</div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="about-content">
            <h2>हमारे बारे में</h2>
            <p>MK Mart एक भरोसेमंद नाम है जो वर्षों से ग्राहकों को उच्च गुणवत्ता के उत्पाद और सेवाएं प्रदान कर रहा है। हमारा उद्देश्य है कि हर ग्राहक को सर्वोत्तम खरीदारी का अनुभव मिले। हम अपने उत्पादों की गुणवत्ता, प्रतिस्पर्धी कीमतों और बेहतरीन ग्राहक सेवा के लिए जाने जाते हैं। आपकी संतुष्टि ही हमारी सफलता है।</p>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2 class="section-title">संपर्क करें</h2>
        <div class="contact-container">
            <div class="contact-info">
                <div class="contact-card fade-in">
                    <div class="feature-icon">📍</div>
                    <h3>पता</h3>
                    <p>मुख्य बाज़ार, शहर<br>पिन कोड: 123456</p>
                </div>
                <div class="contact-card fade-in">
                    <div class="feature-icon">📞</div>
                    <h3>फोन</h3>
                    <p>+91 98765 43210<br>+91 98765 43211</p>
                </div>
                <div class="contact-card fade-in">
                    <div class="feature-icon">✉️</div>
                    <h3>ईमेल</h3>
                    <p>info@mkmart.com<br>support@mkmart.com</p>
                </div>
            </div>

            <div class="contact-form fade-in">
                <form onsubmit="handleSubmit(event)">
                    <div class="form-group">
                        <label for="name">आपका नाम</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-group">
                        <label for="email">ईमेल</label>
                        <input type="email" id="email" name="email" required>
                    </div>
                    <div class="form-group">
                        <label for="phone">फोन नंबर</label>
                        <input type="tel" id="phone" name="phone" required>
                    </div>
                    <div class="form-group">
                        <label for="message">संदेश</label>
                        <textarea id="message" name="message" required></textarea>
                    </div>
                    <button type="submit" class="submit-btn">संदेश भेजें</button>
                </form>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="social-links">
                <a href="#" title="Facebook">📘</a>
                <a href="#" title="Instagram">📷</a>
                <a href="#" title="Twitter">🐦</a>
                <a href="#" title="WhatsApp">💬</a>
            </div>
            <p>&copy; 2026 MK Mart. सर्वाधिकार सुरक्षित।</p>
            <p>Made with ❤️ for our valued customers</p>
        </div>
    </footer>

    <script>
        // Mobile Menu Toggle
        function toggleMenu() {
            const navMenu = document.getElementById('navMenu');
            navMenu.classList.toggle('active');
        }

        // Smooth Scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                    // Close mobile menu if open
                    document.getElementById('navMenu').classList.remove('active');
                }
            });
        });

        // Scroll Animation
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in').forEach(el => {
            observer.observe(el);
        });

        // Form Submission
        function handleSubmit(event) {
            event.preventDefault
