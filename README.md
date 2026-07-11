# arkaniyo
<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>آرکانیو | خدمات انشعاب، موبایل و املاک</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;700;900&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #0f766e;
            --primary-dark: #115e59;
            --secondary: #f59e0b;
            --accent: #ef4444;
            --dark: #1e293b;
            --gray: #64748b;
            --light: #f8fafc;
            --white: #ffffff;
            --gradient: linear-gradient(135deg, #0f766e 0%, #f59e0b 50%, #10b981 100%);
            --shadow-sm: 0 1px 3px rgba(0,0,0,0.08);
            --shadow-md: 0 4px 20px rgba(0,0,0,0.1);
            --shadow-lg: 0 20px 50px rgba(0,0,0,0.15);
            --radius: 16px;
            --radius-sm: 10px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        body {
            font-family: 'Vazirmatn', sans-serif;
            background: #f1f5f9;
            color: var(--dark);
            line-height: 1.7;
            overflow-x: hidden;
        }

        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #e2e8f0; }
        ::-webkit-scrollbar-thumb { background: var(--primary); border-radius: 4px; }

        .header {
            background: rgba(255,255,255,0.9);
            backdrop-filter: blur(20px);
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(0,0,0,0.05);
            padding: 0 2rem;
            transition: var(--transition);
        }
        .header.scrolled { box-shadow: var(--shadow-md); }
        .nav-container {
            max-width: 1300px;
            margin: 0 auto;
            display: flex;
            align-items: center;
            justify-content: space-between;
            height: 72px;
        }
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 900;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-decoration: none;
        }
        .logo i { font-size: 2rem; background: var(--gradient); -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text; }
        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
            align-items: center;
        }
        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            font-size: 0.95rem;
            transition: var(--transition);
            position: relative;
            padding: 5px 0;
        }
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: 0; right: 0;
            width: 0; height: 2px;
            background: var(--gradient);
            transition: width 0.3s;
            border-radius: 2px;
        }
        .nav-links a:hover::after { width: 100%; left: 0; right: auto; }
        .nav-links a:hover { color: var(--primary); }
        .btn-nav {
            background: var(--gradient);
            color: white !important;
            padding: 10px 24px !important;
            border-radius: 50px;
            font-weight: 600 !important;
            transition: var(--transition);
            box-shadow: 0 4px 15px rgba(15,118,110,0.3);
        }
        .btn-nav:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(15,118,110,0.4);
        }
        .btn-nav::after { display: none !important; }
        .mobile-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 1.8rem;
            cursor: pointer;
            color: var(--dark);
        }

        .hero {
            background: linear-gradient(180deg, #f0fdf4 0%, #fef3c7 50%, #e2e8f0 100%);
            padding: 4rem 2rem 6rem;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        .hero::before {
            content: '';
            position: absolute;
            top: -100px; right: -200px;
            width: 600px; height: 600px;
            background: radial-gradient(circle, rgba(15,118,110,0.1) 0%, transparent 70%);
            border-radius: 50%;
        }
        .hero::after {
            content: '';
            position: absolute;
            bottom: -150px; left: -150px;
            width: 500px; height: 500px;
            background: radial-gradient(circle, rgba(245,158,11,0.1) 0%, transparent 70%);
            border-radius: 50%;
        }
        .hero-content {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }
        .hero-badge {
            display: inline-block;
            background: rgba(15,118,110,0.1);
            color: var(--primary);
            padding: 8px 20px;
            border-radius: 50px;
            font-weight: 500;
            font-size: 0.9rem;
            margin-bottom: 1.5rem;
            border: 1px solid rgba(15,118,110,0.2);
        }
        .hero h1 {
            font-size: 3.5rem;
            font-weight: 900;
            background: linear-gradient(135deg, #0f766e, #f59e0b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
            line-height: 1.3;
        }
        .hero p {
            font-size: 1.2rem;
            color: var(--gray);
            max-width: 650px;
            margin: 0 auto 2.5rem;
        }
        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }
        .btn {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            padding: 14px 32px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1rem;
            text-decoration: none;
            transition: var(--transition);
            cursor: pointer;
            border: none;
            font-family: 'Vazirmatn', sans-serif;
        }
        .btn-primary {
            background: var(--gradient);
            color: white;
            box-shadow: 0 8px 30px rgba(15,118,110,0.35);
        }
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(15,118,110,0.45);
        }
        .btn-outline {
            border: 2px solid var(--primary);
            color: var(--primary);
            background: transparent;
        }
        .btn-outline:hover {
            background: var(--primary);
            color: white;
        }
        .btn-soroush {
            background: #27ae60;
            color: white;
            box-shadow: 0 4px 15px rgba(39,174,96,0.3);
        }
        .btn-soroush:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(39,174,96,0.4);
        }

        .stats-strip {
            display: flex;
            justify-content: center;
            gap: 3rem;
            flex-wrap: wrap;
            padding: 2rem;
            background: white;
            margin: -40px auto 3rem;
            max-width: 1000px;
            border-radius: var(--radius);
            box-shadow: var(--shadow-lg);
            position: relative;
            z-index: 2;
        }
        .stat-item { text-align: center; }
        .stat-number {
            font-size: 2.5rem;
            font-weight: 900;
            background: var(--gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        .stat-label { color: var(--gray); font-size: 0.9rem; }

        .section {
            padding: 5rem 2rem;
            max-width: 1300px;
            margin: 0 auto;
        }
        .section-title {
            text-align: center;
            margin-bottom: 3.5rem;
        }
        .section-title h2 {
            font-size: 2.5rem;
            font-weight: 900;
            color: var(--dark);
            margin-bottom: 0.5rem;
        }
        .section-title p { color: var(--gray); font-size: 1.1rem; }
        .section-title .title-line {
            width: 80px; height: 4px;
            background: var(--gradient);
            border-radius: 2px;
            margin: 1rem auto 0;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
        }
        .service-card {
            background: white;
            border-radius: var(--radius);
            padding: 2.5rem 2rem;
            text-align: center;
            transition: var(--transition);
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
            box-shadow: var(--shadow-sm);
        }
        .service-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-lg);
            border-color: rgba(15,118,110,0.2);
        }
        .service-card::before {
            content: '';
            position: absolute;
            top: 0; left: 0;
            width: 100%; height: 4px;
            background: var(--gradient);
            transform: scaleX(0);
            transition: transform 0.4s;
        }
        .service-card:hover::before { transform: scaleX(1); }
        .service-icon {
            width: 80px; height: 80px;
            margin: 0 auto 1.5rem;
            background: linear-gradient(135deg, rgba(15,118,110,0.1), rgba(245,158,11,0.1));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.2rem;
            color: var(--primary);
            transition: var(--transition);
        }
        .service-card:hover .service-icon {
            background: var(--gradient);
            color: white;
            transform: rotateY(180deg);
        }
        .service-card h3 {
            font-size: 1.4rem;
            margin-bottom: 0.8rem;
            font-weight: 700;
        }
        .service-card p { color: var(--gray); margin-bottom: 1.5rem; font-size: 0.95rem; }
        .service-features {
            list-style: none;
            text-align: right;
            margin-bottom: 1.5rem;
        }
        .service-features li {
            padding: 8px 0;
            border-bottom: 1px solid #f1f5f9;
            font-size: 0.9rem;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .service-features li i { color: #10b981; font-size: 1rem; }

        .plans-table-wrapper {
            overflow-x: auto;
            background: white;
            border-radius: var(--radius);
            box-shadow: var(--shadow-md);
            padding: 0.5rem;
        }
        .plans-table {
            width: 100%;
            border-collapse: collapse;
            min-width: 800px;
        }
        .plans-table th, .plans-table td {
            padding: 16px 20px;
            text-align: center;
            border-bottom: 1px solid #e2e8f0;
        }
        .plans-table th {
            background: var(--gradient);
            color: white;
            font-weight: 700;
            font-size: 0.95rem;
        }
        .plans-table th:first-child { border-radius: 0 var(--radius-sm) 0 0; }
        .plans-table th:last-child { border-radius: var(--radius-sm) 0 0 0; }
        .plans-table tr:hover td { background: #f8fafc; }
        .highlight-row td { background: #f0fdf4 !important; font-weight: 600; }
        .badge-popular {
            background: var(--secondary);
            color: #000;
            padding: 4px 12px;
            border-radius: 50px;
            font-size: 0.75rem;
            font-weight: 700;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
            align-items: start;
        }
        .contact-form {
            background: white;
            border-radius: var(--radius);
            padding: 2.5rem;
            box-shadow: var(--shadow-md);
        }
        .contact-form h3 { margin-bottom: 1.5rem; font-size: 1.5rem; }
        .form-group { margin-bottom: 1.2rem; }
        .form-group label {
            display: block;
            margin-bottom: 6px;
            font-weight: 500;
            font-size: 0.9rem;
        }
        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid #e2e8f0;
            border-radius: var(--radius-sm);
            font-family: 'Vazirmatn', sans-serif;
            font-size: 0.95rem;
            transition: var(--transition);
            background: #f8fafc;
        }
        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 4px rgba(15,118,110,0.1);
            background: white;
        }
        .contact-info {
            background: linear-gradient(135deg, #0f766e, #115e59);
            color: white;
            border-radius: var(--radius);
            padding: 2.5rem;
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        .contact-info h3 { font-size: 1.5rem; margin-bottom: 0.5rem; }
        .contact-info-item {
            display: flex;
            align-items: flex-start;
            gap: 12px;
        }
        .contact-info-item i { font-size: 1.3rem; margin-top: 4px; }

        .footer {
            background: var(--dark);
            color: #cbd5e1;
            padding: 4rem 2rem 1rem;
            margin-top: 3rem;
        }
        .footer-grid {
            max-width: 1300px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 2.5rem;
            margin-bottom: 3rem;
        }
        .footer-col h4 { color: white; margin-bottom: 1.2rem; font-size: 1.2rem; }
        .footer-col p, .footer-col a {
            color: #94a3b8;
            text-decoration: none;
            display: block;
            margin-bottom: 8px;
            font-size: 0.9rem;
            transition: var(--transition);
        }
        .footer-col a:hover { color: var(--secondary); }
        .footer-bottom {
            border-top: 1px solid #334155;
            padding-top: 1.5rem;
            text-align: center;
            max-width: 1300px;
            margin: 0 auto;
            font-size: 0.85rem;
        }
        .social-links {
            display: flex;
            gap: 12px;
            margin-top: 1rem;
        }
        .social-links a {
            width: 40px; height: 40px;
            background: #334155;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white !important;
            transition: var(--transition);
        }
        .social-links a:hover {
            background: var(--gradient);
            transform: translateY(-3px);
        }

        .toast {
            position: fixed;
            bottom: 30px;
            right: 50%;
            transform: translateX(50%);
            background: #10b981;
            color: white;
            padding: 14px 28px;
            border-radius: 50px;
            font-weight: 600;
            z-index: 9999;
            box-shadow: var(--shadow-lg);
            display: none;
            animation: slideUp 0.4s ease;
        }
        @keyframes slideUp {
            from { opacity: 0; transform: translateX(50%) translateY(30px); }
            to { opacity: 1; transform: translateX(50%) translateY(0); }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 72px;
                right: 0;
                background: white;
                width: 100%;
                padding: 1.5rem;
                box-shadow: var(--shadow-lg);
                border-radius: 0 0 var(--radius) var(--radius);
            }
            .nav-links.active { display: flex; }
            .mobile-toggle { display: block; }
            .hero h1 { font-size: 2.2rem; }
            .stats-strip { gap: 1.5rem; padding: 1.5rem; }
            .stat-number { font-size: 1.8rem; }
            .contact-grid { grid-template-columns: 1fr; }
            .section { padding: 3rem 1rem; }
            .section-title h2 { font-size: 1.8rem; }
        }
    </style>
</head>
<body>

    <header class="header" id="header">
        <div class="nav-container">
            <a href="#" class="logo">
                <i class="fas fa-building"></i> آرکانیو
            </a>
            <button class="mobile-toggle" id="mobileToggle" aria-label="منو">
                <i class="fas fa-bars"></i>
            </button>
            <ul class="nav-links" id="navLinks">
                <li><a href="#services">خدمات</a></li>
                <li><a href="#plans">تعرفه‌ها</a></li>
                <li><a href="#contact">پشتیبانی</a></li>
                <li><a href="#about">درباره ما</a></li>
                <li><a href="https://splus.ir/ARKANEW" target="_blank" class="btn-nav">گروه سروش</a></li>
            </ul>
        </div>
    </header>

    <section class="hero">
        <div class="hero-content">
            <span class="hero-badge">📍 دفتر خدمات آرکانیو | میدان جهاد، جنب بانک ملی</span>
            <h1>خدمات انشعاب، موبایل و قرارداد اجاره</h1>
            <p>انجام کلیه امور انشعاب آب و برق، فروش سیم‌کارت، خدمات تلفن همراه و تنظیم قرارداد خودنویس اجاره متصل به بنگاه. با پشتیبانی ۲۴ ساعته و یک تماس، همه چیز را به ما بسپارید.</p>
            <div class="hero-buttons">
                <a href="#contact" class="btn btn-primary"><i class="fas fa-phone"></i> تماس سریع</a>
                <a href="https://splus.ir/ARKANEW" target="_blank" class="btn btn-soroush"><i class="fas fa-comments"></i> گروه سروش آرکانیو</a>
            </div>
        </div>
    </section>

    <div class="stats-strip">
        <div class="stat-item">
            <div class="stat-number" data-count="5000">0</div>
            <div class="stat-label">قرارداد موفق</div>
        </div>
        <div class="stat-item">
            <div class="stat-number" data-count="1200">0</div>
            <div class="stat-label">انشعاب واگذار شده</div>
        </div>
        <div class="stat-item">
            <div class="stat-number" data-count="99">0</div>
            <div class="stat-label">درصد رضایت</div>
        </div>
        <div class="stat-item">
            <div class="stat-number" data-count="24">0</div>
            <div class="stat-label">پشتیبانی شبانه‌روزی</div>
        </div>
    </div>

    <section class="section" id="services">
        <div class="section-title">
            <h2>خدمات دفتر آرکانیو</h2>
            <p>از ثبت انشعاب تا قرارداد اجاره، همه در یک جا</p>
            <div class="title-line"></div>
        </div>
        <div class="services-grid">
            <div class="service-card">
                <div class="service-icon"><i class="fas fa-water"></i></div>
                <h3>انشعاب آب و برق</h3>
                <p>ثبت، پیگیری و اخذ انشعاب آب و برق به صورت قانونی و سریع</p>
                <ul class="service-features">
                    <li><i class="fas fa-check-circle"></i> تشکیل پرونده در کمترین زمان</li>
                    <li><i class="fas fa-check-circle"></i> بازدید و نقشه‌برداری</li>
                    <li><i class="fas fa-check-circle"></i> اخذ مجوزهای لازم</li>
                    <li><i class="fas fa-check-circle"></i> تحویل قطعی کنتور</li>
                </ul>
                <a href="#contact" class="btn btn-primary" style="width:100%;justify-content:center;">مشاوره و ثبت</a>
            </div>
            <div class="service-card">
                <div class="service-icon"><i class="fas fa-mobile-alt"></i></div>
                <h3>خدمات تلفن همراه و سیم‌کارت</h3>
                <p>فروش انواع سیم‌کارت دائمی و اعتباری، ترابرد خط، رجیستری و خدمات مخابراتی</p>
                <ul class="service-features">
                    <li><i class="fas fa-check-circle"></i> سیم‌کارت اپراتورهای همراه</li>
                    <li><i class="fas fa-check-circle"></i> ترابرد و تغییر مالکیت</li>
                    <li><i class="fas fa-check-circle"></i> رجیستری گوشی</li>
                    <li><i class="fas fa-check-circle"></i> فعال‌سازی بسته‌های اینترنت</li>
                </ul>
                <a href="#contact" class="btn btn-primary" style="width:100%;justify-content:center;">خرید و مشاوره</a>
            </div>
            <div class="service-card">
                <div class="service-icon"><i class="fas fa-file-contract"></i></div>
                <h3>قرارداد خودنویس اجاره</h3>
                <p>تنظیم قرارداد اجاره به صورت خودنویس و متصل به سامانه بنگاه‌های املاک</p>
                <ul class="service-features">
                    <li><i class="fas fa-check-circle"></i> ثبت در سامانه املاک</li>
                    <li><i class="fas fa-check-circle"></i> کد رهگیری رسمی</li>
                    <li><i class="fas fa-check-circle"></i> بررسی مدارک مالک و مستأجر</li>
                    <li><i class="fas fa-check-circle"></i> تحویل فوری قرارداد</li>
                </ul>
                <a href="#contact" class="btn btn-primary" style="width:100%;justify-content:center;">ثبت درخواست</a>
            </div>
        </div>
    </section>

    <section class="section" id="plans">
        <div class="section-title">
            <h2>تعرفه خدمات</h2>
            <p>هزینه‌های شفاف و رقابتی</p>
            <div class="title-line"></div>
        </div>
        <div class="plans-table-wrapper">
            <table class="plans-table">
                <thead>
                    <tr>
                        <th>نوع خدمت</th>
                        <th>جزئیات</th>
                        <th>مدت زمان تقریبی</th>
                        <th>هزینه (تومان)</th>
                        <th>وضعیت</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>انشعاب آب</td>
                        <td>تا قطر یک اینچ</td>
                        <td>۷ الی ۱۴ روز</td>
                        <td>تماس بگیرید</td>
                        <td><span class="badge-popular">فعال</span></td>
                    </tr>
                    <tr class="highlight-row">
                        <td>انشعاب برق</td>
                        <td>تکفاز / سه‌فاز</td>
                        <td>۱۰ الی ۲۰ روز</td>
                        <td>استعلام</td>
                        <td><span class="badge-popular">پرتقاضا</span></td>
                    </tr>
                    <tr>
                        <td>سیم‌کارت دائمی</td>
                        <td>همراه اول و ایرانسل</td>
                        <td>آنی</td>
                        <td>۵۰۰,۰۰۰ الی ۲,۰۰۰,۰۰۰</td>
                        <td><span class="badge-popular">موجود</span></td>
                    </tr>
                    <tr>
                        <td>قرارداد خودنویس</td>
                        <td>اجاره مسکونی</td>
                        <td>همان روز</td>
                        <td>۳۵۰,۰۰۰</td>
                        <td><span class="badge-popular">ویژه</span></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </section>

    <section class="section" id="contact">
        <div class="section-title">
            <h2>تماس با دفتر آرکانیو</h2>
            <p>میدان جهاد، جنب بانک ملی | شماره تماس: 09945133360</p>
            <div class="title-line"></div>
        </div>
        <div class="contact-grid">
            <form class="contact-form" id="contactForm">
                <h3>📝 فرم درخواست (رایگان)</h3>
                <div class="form-group">
                    <label>نام و نام خانوادگی</label>
                    <input type="text" placeholder="مثال: علی محمدی" required>
                </div>
                <div class="form-group">
                    <label>شماره تماس</label>
                    <input type="tel" placeholder="۰۹۹۴۵۱۳۳۳۶۰" required>
                </div>
                <div class="form-group">
                    <label>نوع خدمت</label>
                    <select required>
                        <option value="">-- انتخاب کنید --</option>
                        <option>انشعاب آب و برق</option>
                        <option>خدمات تلفن همراه / سیم‌کارت</option>
                        <option>قرارداد خودنویس اجاره</option>
                        <option>سایر / مشاوره</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>توضیحات</label>
                    <textarea rows="3" placeholder="توضیحات خود را وارد کنید..."></textarea>
                </div>
                <button type="submit" class="btn btn-primary" style="width:100%;justify-content:center;">
                    <i class="fas fa-paper-plane"></i> ارسال درخواست
                </button>
            </form>
            <div class="contact-info">
                <h3>📞 ارتباط مستقیم</h3>
                <div class="contact-info-item">
                    <i class="fas fa-phone"></i>
                    <div><strong>شماره تماس:</strong><br>09945133360</div>
                </div>
                <div class="contact-info-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <div><strong>آدرس دفتر:</strong><br>میدان جهاد، جنب بانک ملی</div>
                </div>
                <div class="contact-info-item">
                    <i class="fas fa-clock"></i>
                    <div><strong>ساعت کاری:</strong><br>شنبه تا پنجشنبه ۹ تا ۲۰</div>
                </div>
                <div style="margin-top:1rem;">
                    <p style="margin-bottom:8px;"><strong>گروه سروش:</strong></p>
                    <a href="https://splus.ir/ARKANEW" target="_blank" class="btn btn-soroush" style="display:inline-flex;align-items:center;gap:8px;">
                        <i class="fas fa-users"></i> عضویت در گروه آرکانیو
                    </a>
                </div>
            </div>
        </div>
    </section>

    <footer class="footer" id="about">
        <div class="footer-grid">
            <div class="footer-col">
                <h4>دفتر آرکانیو</h4>
                <p>ارائه خدمات انشعاب آب و برق، تلفن همراه و تنظیم قرارداد اجاره. پشتیبانی سریع و مطمئن در میدان جهاد.</p>
            </div>
            <div class="footer-col">
                <h4>خدمات</h4>
                <a href="#">انشعاب آب و برق</a>
                <a href="#">فروش سیم‌کارت</a>
                <a href="#">قرارداد خودنویس</a>
                <a href="#">مشاوره املاک</a>
            </div>
            <div class="footer-col">
                <h4>دسترسی سریع</h4>
                <a href="https://splus.ir/ARKANEW" target="_blank">گروه سروش</a>
                <a href="tel:09945133360">تماس فوری</a>
                <a href="#contact">ثبت درخواست</a>
            </div>
            <div class="footer-col">
                <h4>اطلاعات</h4>
                <p>📞 09945133360</p>
                <p>📍 میدان جهاد، جنب بانک ملی</p>
                <p>🕒 ۹ صبح تا ۸ شب</p>
            </div>
        </div>
        <div class="footer-bottom">
            <p>© ۲۰۲۴ کلیه حقوق برای دفتر آرکانیو محفوظ است | طراحی اختصاصی</p>
        </div>
    </footer>

    <div class="toast" id="toast">✅ درخواست شما با موفقیت ثبت شد! به زودی تماس می‌گیریم.</div>

    <script>
        const mobileToggle = document.getElementById('mobileToggle');
        const navLinks = document.getElementById('navLinks');
        mobileToggle.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });
        navLinks.querySelectorAll('a').forEach(link => {
            link.addEventListener('click', () => navLinks.classList.remove('active'));
        });

        window.addEventListener('scroll', () => {
            document.getElementById('header').classList.toggle('scrolled', window.scrollY > 50);
        });

        const statNumbers = document.querySelectorAll('.stat-number');
        const animateCounter = (el) => {
            const target = parseInt(el.getAttribute('data-count'));
            let count = 0;
            const duration = 2000;
            const step = Math.ceil(target / (duration / 30));
            const timer = setInterval(() => {
                count += step;
                if (count >= target) {
                    el.textContent = target.toLocaleString('fa-IR') + (target === 99 ? '%' : '+');
                    clearInterval(timer);
                } else {
                    el.textContent = count.toLocaleString('fa-IR') + (target === 99 ? '%' : '+');
                }
            }, 30);
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    statNumbers.forEach(n => animateCounter(n));
                    observer.disconnect();
                }
            });
        }, { threshold: 0.5 });
        if (statNumbers.length) observer.observe(statNumbers[0].parentElement.parentElement);

        document.getElementById('contactForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const toast = document.getElementById('toast');
            toast.style.display = 'block';
            setTimeout(() => { toast.style.display = 'none'; }, 3000);
            this.reset();
        });

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });
    </script>
</body>
</html>
