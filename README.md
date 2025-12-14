<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>iCircuit - شبیه‌سازی حرفه‌ای مدارهای الکترونیکی</title>
    
    <!-- Google Fonts - Vazirmatn -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <style>
        /* ===== CSS Variables ===== */
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --primary-light: #3b82f6;
            --secondary: #0ea5e9;
            --accent: #06b6d4;
            --dark: #0f172a;
            --dark-light: #1e293b;
            --gray: #64748b;
            --gray-light: #94a3b8;
            --light: #f1f5f9;
            --white: #ffffff;
            --gradient-primary: linear-gradient(135deg, #2563eb 0%, #0ea5e9 100%);
            --gradient-dark: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            --shadow-sm: 0 1px 2px rgba(0,0,0,0.05);
            --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -1px rgba(0,0,0,0.06);
            --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -2px rgba(0,0,0,0.05);
            --shadow-xl: 0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px -5px rgba(0,0,0,0.04);
        }

        /* ===== Reset & Base Styles ===== */
        *, *::before, *::after {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Vazirmatn', sans-serif;
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.8;
            overflow-x: hidden;
        }

        /* ===== Container ===== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* ===== Header Section ===== */
        header {
            background: var(--gradient-dark);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        /* Animated Background Pattern */
        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: 
                radial-gradient(circle at 20% 80%, rgba(37, 99, 235, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(14, 165, 233, 0.15) 0%, transparent 50%),
                radial-gradient(circle at 40% 40%, rgba(6, 182, 212, 0.1) 0%, transparent 40%);
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        /* Circuit Pattern Overlay */
        header::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%232563eb' fill-opacity='0.05'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
            opacity: 0.5;
        }

        .header-content {
            text-align: center;
            position: relative;
            z-index: 10;
            padding: 40px 20px;
        }

        /* Logo Icon */
        .logo-icon {
            width: 100px;
            height: 100px;
            margin: 0 auto 30px;
            background: var(--gradient-primary);
            border-radius: 24px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 20px 40px rgba(37, 99, 235, 0.4);
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .logo-icon svg {
            width: 60px;
            height: 60px;
            fill: var(--white);
        }

        .header-title {
            font-size: clamp(3rem, 8vw, 5rem);
            font-weight: 800;
            color: var(--white);
            margin-bottom: 15px;
            letter-spacing: -2px;
        }

        .header-title span {
            background: var(--gradient-primary);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .header-subtitle {
            font-size: clamp(1.1rem, 3vw, 1.5rem);
            color: var(--gray-light);
            font-weight: 400;
            margin-bottom: 40px;
        }

        /* CTA Buttons */
        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 16px 32px;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            text-decoration: none;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            font-family: inherit;
        }

        .btn-primary {
            background: var(--gradient-primary);
            color: var(--white);
            box-shadow: 0 10px 30px rgba(37, 99, 235, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(37, 99, 235, 0.5);
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: var(--white);
            border: 2px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
            border-color: rgba(255, 255, 255, 0.4);
            transform: translateY(-3px);
        }

        .btn svg {
            width: 22px;
            height: 22px;
            fill: currentColor;
        }

        /* Scroll Indicator */
        .scroll-indicator {
            position: absolute;
            bottom: 40px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
            40% { transform: translateX(-50%) translateY(-10px); }
            60% { transform: translateX(-50%) translateY(-5px); }
        }

        .scroll-indicator svg {
            width: 30px;
            height: 30px;
            fill: var(--gray-light);
        }

        /* ===== Section Styles ===== */
        section {
            padding: 100px 0;
        }

        .section-title {
            font-size: clamp(1.8rem, 4vw, 2.5rem);
            font-weight: 700;
            color: var(--dark);
            text-align: center;
            margin-bottom: 20px;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: var(--gradient-primary);
            margin: 20px auto 0;
            border-radius: 2px;
        }

        .section-subtitle {
            text-align: center;
            color: var(--gray);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto 60px;
        }

        /* ===== About Section ===== */
        .about-section {
            background: var(--white);
        }

        .about-content {
            max-width: 900px;
            margin: 0 auto;
            background: linear-gradient(135deg, #f8fafc 0%, #e2e8f0 100%);
            padding: 50px;
            border-radius: 24px;
            box-shadow: var(--shadow-xl);
            position: relative;
            overflow: hidden;
        }

        .about-content::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 200px;
            height: 200px;
            background: var(--gradient-primary);
            opacity: 0.05;
            border-radius: 50%;
            transform: translate(50%, -50%);
        }

        .about-content p {
            font-size: 1.15rem;
            line-height: 2;
            color: var(--dark-light);
            margin-bottom: 25px;
            text-align: justify;
        }

        .about-content p:last-child {
            margin-bottom: 0;
        }

        /* ===== Features Section ===== */
        .features-section {
            background: linear-gradient(180deg, var(--light) 0%, var(--white) 100%);
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: var(--white);
            padding: 40px 30px;
            border-radius: 20px;
            box-shadow: var(--shadow-md);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .feature-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: var(--gradient-primary);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: var(--shadow-xl);
        }

        .feature-card:hover::before {
            transform: scaleX(1);
        }

        .feature-icon {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, rgba(37, 99, 235, 0.1) 0%, rgba(14, 165, 233, 0.1) 100%);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 25px;
        }

        .feature-icon svg {
            width: 35px;
            height: 35px;
            fill: var(--primary);
        }

        .feature-card h3 {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 15px;
        }

        .feature-card p {
            color: var(--gray);
            font-size: 1rem;
            line-height: 1.8;
        }

        /* ===== Components Section ===== */
        .components-section {
            background: var(--gradient-dark);
            color: var(--white);
        }

        .components-section .section-title {
            color: var(--white);
        }

        .components-section .section-subtitle {
            color: var(--gray-light);
        }

        .components-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .component-item {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            padding: 25px;
            border-radius: 16px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            display: flex;
            align-items: center;
            gap: 15px;
            transition: all 0.3s ease;
        }

        .component-item:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: rgba(255, 255, 255, 0.2);
            transform: translateX(-5px);
        }

        .component-icon {
            width: 50px;
            height: 50px;
            background: var(--gradient-primary);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-shrink: 0;
        }

        .component-icon svg {
            width: 24px;
            height: 24px;
            fill: var(--white);
        }

        .component-item span {
            font-size: 1.1rem;
            font-weight: 500;
        }

        /* ===== Target Audience Section ===== */
        .audience-section {
            background: var(--white);
        }

        .audience-box {
            max-width: 800px;
            margin: 0 auto;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            padding: 60px 50px;
            border-radius: 24px;
            text-align: center;
            box-shadow: 0 20px 60px rgba(37, 99, 235, 0.3);
            position: relative;
            overflow: hidden;
        }

        .audience-box::before,
        .audience-box::after {
            content: '';
            position: absolute;
            width: 200px;
            height: 200px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
        }

        .audience-box::before {
            top: -100px;
            right: -100px;
        }

        .audience-box::after {
            bottom: -100px;
            left: -100px;
        }

        .audience-box h3 {
            font-size: 1.5rem;
            color: var(--white);
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }

        .audience-box p {
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.95);
            line-height: 2;
            position: relative;
            z-index: 1;
        }

        /* ===== Contact Section ===== */
        .contact-section {
            background: linear-gradient(180deg, var(--light) 0%, var(--white) 100%);
        }

        .contact-buttons {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
        }

        .contact-btn {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 25px 40px;
            border-radius: 16px;
            text-decoration: none;
            font-size: 1.2rem;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .contact-btn.telegram {
            background: linear-gradient(135deg, #0088cc 0%, #00a2e3 100%);
            color: var(--white);
            box-shadow: 0 10px 30px rgba(0, 136, 204, 0.4);
        }

        .contact-btn.telegram:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 15px 40px rgba(0, 136, 204, 0.5);
        }

        .contact-btn.email {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
            color: var(--white);
            box-shadow: 0 10px 30px rgba(37, 99, 235, 0.4);
        }

        .contact-btn.email:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 15px 40px rgba(37, 99, 235, 0.5);
        }

        .contact-btn svg {
            width: 28px;
            height: 28px;
            fill: currentColor;
        }

        /* ===== Footer ===== */
        footer {
            background: var(--dark);
            padding: 40px 20px;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .footer-logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--white);
        }

        .footer-email {
            display: flex;
            align-items: center;
            gap: 10px;
            color: var(--gray-light);
            font-size: 1rem;
        }

        .footer-email svg {
            width: 20px;
            height: 20px;
            fill: var(--gray-light);
        }

        .footer-email a {
            color: var(--gray-light);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-email a:hover {
            color: var(--primary-light);
        }

        .footer-copyright {
            color: var(--gray);
            font-size: 0.9rem;
            margin-top: 10px;
        }

        /* ===== Responsive Styles ===== */
        @media (max-width: 768px) {
            section {
                padding: 70px 0;
            }

            .about-content {
                padding: 30px 25px;
            }

            .about-content p {
                font-size: 1rem;
            }

            .feature-card {
                padding: 30px 25px;
            }

            .audience-box {
                padding: 40px 30px;
            }

            .contact-btn {
                padding: 20px 30px;
                font-size: 1.1rem;
                width: 100%;
                justify-content: center;
            }

            .btn {
                padding: 14px 24px;
                font-size: 1rem;
            }

            .features-grid {
                grid-template-columns: 1fr;
            }

            .components-grid {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .header-content {
                padding: 30px 15px;
            }

            .logo-icon {
                width: 80px;
                height: 80px;
            }

            .logo-icon svg {
                width: 45px;
                height: 45px;
            }

            .cta-buttons {
                flex-direction: column;
                width: 100%;
                padding: 0 20px;
            }

            .btn {
                width: 100%;
                justify-content: center;
            }

            .contact-buttons {
                flex-direction: column;
                padding: 0 20px;
            }
        }
    </style>
</head>
<body>

    <!-- ===== Header Section ===== -->
    <header>
        <div class="header-content">
            <!-- Logo Icon -->
            <div class="logo-icon">
                <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                    <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                </svg>
            </div>
            
            <!-- Main Title -->
            <h1 class="header-title"><span>i</span>Circuit</h1>
            
            <!-- Subtitle -->
            <p class="header-subtitle">شبیه‌سازی حرفه‌ای مدارهای الکترونیکی</p>
            
            <!-- CTA Buttons -->
            <div class="cta-buttons">
                <a href="https://t.me/Mohammadjavad1390M" target="_blank" rel="noopener" class="btn btn-primary">
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>
                    </svg>
                    عضویت در تلگرام
                </a>
                <a href="mailto:m48511032@gmail.com" class="btn btn-secondary">
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                    </svg>
                    تماس با ایمیل
                </a>
            </div>
        </div>
        
        <!-- Scroll Indicator -->
        <div class="scroll-indicator">
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                <path d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6-6-6 1.41-1.41z"/>
            </svg>
        </div>
    </header>

    <!-- ===== About Section ===== -->
    <section class="about-section">
        <div class="container">
            <h2 class="section-title">معرفی برنامه</h2>
            <p class="section-subtitle">آشنایی با قابلیت‌های منحصربه‌فرد iCircuit</p>
            
            <div class="about-content">
                <p>
                    iCircuit یک برنامه‌ی آموزشی و سرگرم‌کننده برای طراحی، شبیه‌سازی و آزمایش مدارهای الکترونیکی است. این برنامه با بهره‌گیری از موتور شبیه‌سازی پیشرفته، امکان تحلیل هم‌زمان مدارهای آنالوگ و دیجیتال را به‌صورت بی‌درنگ (Real-Time) فراهم می‌کند.
                </p>
                <p>
                    در iCircuit شبیه‌سازی همیشه فعال است؛ به این معنا که با هر تغییر در مدار، نتیجه بلافاصله قابل مشاهده خواهد بود. این ویژگی تجربه‌ای مشابه کار با مدار واقعی را ایجاد می‌کند و نیاز به اجرای دستی شبیه‌سازی یا تنظیمات پیچیده را از بین می‌برد.
                </p>
                <p>
                    کار با برنامه بسیار ساده است. کاربران می‌توانند قطعات مختلف را به مدار اضافه کرده، آن‌ها را به هم متصل کنند و مقادیرشان را تغییر دهند و هم‌زمان رفتار مدار را مشاهده کنند.
                </p>
            </div>
        </div>
    </section>

    <!-- ===== Features Section ===== -->
    <section class="features-section">
        <div class="container">
            <h2 class="section-title">امکانات و ویژگی‌ها</h2>
            <p class="section-subtitle">ابزارهای قدرتمند برای یادگیری و طراحی مدار</p>
            
            <div class="features-grid">
                <!-- Feature 1 -->
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M13 2.05v2.02c3.95.49 7 3.85 7 7.93 0 3.21-1.92 6-4.72 7.28L13 17v5h5l-1.22-1.22C19.91 19.07 22 15.76 22 12c0-5.18-3.95-9.45-9-9.95zM11 2.05C5.94 2.55 2 6.81 2 12c0 3.76 2.09 7.07 5.22 8.78L6 22h5v-5l-2.28 2.28C6.92 18 5 15.21 5 12c0-4.08 3.05-7.44 7-7.93V2.05z"/>
                        </svg>
                    </div>
                    <h3>شبیه‌سازی بی‌درنگ</h3>
                    <p>شبیه‌سازی بی‌درنگ مدارهای آنالوگ و دیجیتال با مشاهده لحظه‌ای تغییرات</p>
                </div>
                
                <!-- Feature 2 -->
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M12 3L1 9l4 2.18v6L12 21l7-3.82v-6l2-1.09V17h2V9L12 3zm6.82 6L12 12.72 5.18 9 12 5.28 18.82 9zM17 15.99l-5 2.73-5-2.73v-3.72L12 15l5-2.73v3.72z"/>
                        </svg>
                    </div>
                    <h3>رابط کاربری آموزشی</h3>
                    <p>رابط کاربری ساده و آموزشی مناسب برای همه سطوح</p>
                </div>
                
                <!-- Feature 3 -->
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M19.5 6c-1.31 0-2.37 1.01-2.48 2.3L15.5 8c-.75-.5-1.55-.9-2.4-1.2-.05-.91-.96-1.8-2.1-1.8s-2.05.89-2.1 1.8c-.85.3-1.65.7-2.4 1.2l-1.52.3C4.87 7.01 3.81 6 2.5 6 1.12 6 0 7.12 0 8.5S1.12 11 2.5 11c.83 0 1.56-.42 2-1.06l2.14-.42c-.25.64-.41 1.31-.49 2h-.65c-1.38 0-2.5 1.12-2.5 2.5s1.12 2.5 2.5 2.5h.65c.08.69.24 1.36.49 2l-2.14-.42c-.44-.64-1.17-1.06-2-1.06C1.12 17 0 18.12 0 19.5S1.12 22 2.5 22c1.31 0 2.37-1.01 2.48-2.3l1.52.3c.75.5 1.55.9 2.4 1.2.05.91.96 1.8 2.1 1.8s2.05-.89 2.1-1.8c.85-.3 1.65-.7 2.4-1.2l1.52-.3c.11 1.29 1.17 2.3 2.48 2.3 1.38 0 2.5-1.12 2.5-2.5s-1.12-2.5-2.5-2.5c-.83 0-1.56.42-2 1.06l-2.14.42c.25-.64.41-1.31.49-2h.65c1.38 0 2.5-1.12 2.5-2.5s-1.12-2.5-2.5-2.5h-.65c-.08-.69-.24-1.36-.49-2l2.14.42c.44.64 1.17 1.06 2 1.06 1.38 0 2.5-1.12 2.5-2.5S20.88 6 19.5 6zM11 14.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
                        </svg>
                    </div>
                    <h3>مولتی‌متر داخلی</h3>
                    <p>اندازه‌گیری دقیق ولتاژ، جریان و مقاومت در هر نقطه از مدار</p>
                </div>
                
                <!-- Feature 4 -->
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M3 13h2v-2H3v2zm0 4h2v-2H3v2zm0-8h2V7H3v2zm4 4h14v-2H7v2zm0 4h14v-2H7v2zM7 7v2h14V7H7z"/>
                        </svg>
                    </div>
                    <h3>اسیلوسکوپ داخلی</h3>
                    <p>نمایش گرافیکی سیگنال‌ها با قابلیت تنظیم مقیاس و زمان</p>
                </div>
                
                <!-- Feature 5 -->
                <div class="feature-card">
                    <div class="feature-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M16 6l2.29 2.29-4.88 4.88-4-4L2 16.59 3.41 18l6-6 4 4 6.3-6.29L22 12V6z"/>
                        </svg>
                    </div>
                    <h3>مشاهده چند سیگنال</h3>
                    <p>مشاهده هم‌زمان چند سیگنال برای مقایسه و تحلیل بهتر</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== Components Section ===== -->
    <section class="components-section">
        <div class="container">
            <h2 class="section-title">قطعات پشتیبانی‌شده</h2>
            <p class="section-subtitle">کتابخانه گسترده از قطعات الکترونیکی</p>
            
            <div class="components-grid">
                <!-- Component Items -->
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M15.67 4H14V2h-4v2H8.33C7.6 4 7 4.6 7 5.33v15.34C7 21.4 7.6 22 8.33 22h7.34c.73 0 1.33-.6 1.33-1.33V5.33C17 4.6 16.4 4 15.67 4z"/>
                        </svg>
                    </div>
                    <span>منابع ولتاژ و جریان</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm0 18c-4.42 0-8-3.58-8-8s3.58-8 8-8 8 3.58 8 8-3.58 8-8 8z"/>
                        </svg>
                    </div>
                    <span>مقاومت، خازن، سلف</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M13 3h-2v10h2V3zm4.83 2.17l-1.42 1.42C17.99 7.86 19 9.81 19 12c0 3.87-3.13 7-7 7s-7-3.13-7-7c0-2.19 1.01-4.14 2.58-5.42L6.17 5.17C4.23 6.82 3 9.26 3 12c0 4.97 4.03 9 9 9s9-4.03 9-9c0-2.74-1.23-5.18-3.17-6.83z"/>
                        </svg>
                    </div>
                    <span>کلیدها و رله</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M7 2v11h3v9l7-12h-4l4-8z"/>
                        </svg>
                    </div>
                    <span>دیود، BJT، MOSFET</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M9 21c0 .55.45 1 1 1h4c.55 0 1-.45 1-1v-1H9v1zm3-19C8.14 2 5 5.14 5 9c0 2.38 1.19 4.47 3 5.74V17c0 .55.45 1 1 1h6c.55 0 1-.45 1-1v-2.26c1.81-1.27 3-3.36 3-5.74 0-3.86-3.14-7-7-7zm2.85 11.1l-.85.6V16h-4v-2.3l-.85-.6C7.8 12.16 7 10.63 7 9c0-2.76 2.24-5 5-5s5 2.24 5 5c0 1.63-.8 3.16-2.15 4.1z"/>
                        </svg>
                    </div>
                    <span>LED، موتور DC، بلندگو، میکروفون</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M4 6h18V4H4c-1.1 0-2 .9-2 2v11H0v3h14v-3H4V6zm19 2h-6c-.55 0-1 .45-1 1v10c0 .55.45 1 1 1h6c.55 0 1-.45 1-1V9c0-.55-.45-1-1-1zm-1 9h-4v-7h4v7z"/>
                        </svg>
                    </div>
                    <span>ADC و DAC</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M22 9V7h-2V5c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2v-2h2v-2h-2v-2h2v-2h-2V9h2zm-4 10H4V5h14v14zM6 13h5v4H6zm6-6h4v3h-4zM6 7h5v5H6zm6 4h4v6h-4z"/>
                        </svg>
                    </div>
                    <span>گیت‌های منطقی</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 16H5V5h14v14z"/>
                        </svg>
                    </div>
                    <span>فلیپ‌فلاپ JK و D</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M20 2H4c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zM8 20H4v-4h4v4zm0-6H4v-4h4v4zm0-6H4V4h4v4zm6 12h-4v-4h4v4zm0-6h-4v-4h4v4zm0-6h-4V4h4v4zm6 12h-4v-4h4v4zm0-6h-4v-4h4v4zm0-6h-4V4h4v4z"/>
                        </svg>
                    </div>
                    <span>آی‌سی‌های سری 7400</span>
                </div>
                
                <div class="component-item">
                    <div class="component-icon">
                        <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path d="M5 2c0-.55-.45-1-1-1s-1 .45-1 1v4H2c-.55 0-1 .45-1 1v10c0 .55.45 1 1 1h1v4c0 .55.45 1 1 1s1-.45 1-1v-4h1c.55 0 1-.45 1-1V7c0-.55-.45-1-1-1H5V2z"/>
                        </svg>
                    </div>
                    <span>سون‌سگمنت</span>
                </div>
            </div>
        </div>
    </section>

    <!-- ===== Target Audience Section ===== -->
    <section class="audience-section">
        <div class="container">
            <h2 class="section-title">مناسب برای</h2>
            <p class="section-subtitle">چه کسانی از iCircuit بهره‌مند می‌شوند؟</p>
            
            <div class="audience-box">
                <h3>🎓 یادگیری ساده و عملی</h3>
                <p>
                    دانش‌آموزان، هنرجویان، علاقه‌مندان به الکترونیک و افرادی که قصد یادگیری و آزمایش مدارهای الکترونیکی را به‌صورت ساده و عملی دارند.
                </p>
            </div>
        </div>
    </section>

    <!-- ===== Contact Section ===== -->
    <section class="contact-section">
        <div class="container">
            <h2 class="section-title">ارتباط با ما</h2>
            <p class="section-subtitle">سوالی دارید؟ با ما در تماس باشید</p>
            
            <div class="contact-buttons">
                <a href="https://t.me/Mohammadjavad1390M" target="_blank" rel="noopener" class="contact-btn telegram">
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>
                    </svg>
                 ارسال پیام در تلگرام
                </a>
                
                <a href="mailto:m48511032@gmail.com" class="contact-btn email">
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                    </svg>
                    ارسال ایمیل
                </a>
            </div>
        </div>
    </section>

    <!-- ===== Footer ===== -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">iCircuit</div>
                <div class="footer-email">
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                    </svg>
                    <a href="mailto:m48511032@gmail.com">m48511032@gmail.com</a>
                </div>
                <p class="footer-copyright">© کلیه حقوق این سایت متعلق به محمد جواد اسماعیلی می باشد</p>
            </div>
        </div>
    </footer>

</body>
</html>
