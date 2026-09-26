<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Two S Cars | تجربة الفخامة المطلقة</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;800;900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root {
            --bg-color: #050505;
            --card-bg: #121212;
            --gold: #d4af37;
            --gold-light: #f3e5ab;
            --text-main: #ffffff;
            --text-muted: #999999;
            --transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            overflow-x: hidden;
        }

        /* Navbar */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(5, 5, 5, 0.8);
            backdrop-filter: blur(15px);
            border-bottom: 1px solid rgba(212, 175, 55, 0.1);
        }

        .logo {
            font-size: 26px;
            font-weight: 900;
            color: var(--text-main);
            letter-spacing: 2px;
            text-decoration: none;
        }

        .logo span {
            color: var(--gold);
        }

        .nav-links {
            display: flex;
            gap: 30px;
            list-style: none;
        }

        .nav-links a {
            color: var(--text-muted);
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--gold);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            padding: 0 8%;
            background: linear-gradient(135deg, rgba(5,5,5,0.95) 30%, rgba(5,5,5,0.6) 100%), url('https://images.unsplash.com/photo-1617531653332-bd46c24f2068?auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            position: relative;
        }

        .hero-content {
            max-width: 650px;
            animation: fadeInRight 1.2s ease;
        }

        .hero h1 {
            font-size: 4rem;
            font-weight: 900;
            line-height: 1.1;
            margin-bottom: 20px;
        }

        .hero h1 span {
            color: var(--gold);
            text-shadow: 0 0 30px rgba(212, 175, 55, 0.4);
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-muted);
            margin-bottom: 40px;
            line-height: 1.8;
        }

        .btn {
            display: inline-block;
            padding: 15px 35px;
            background: linear-gradient(45deg, var(--gold), #aa8c2c);
            color: #000;
            font-weight: 800;
            font-size: 18px;
            border-radius: 50px;
            text-decoration: none;
            box-shadow: 0 10px 25px rgba(212, 175, 55, 0.3);
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(212, 175, 55, 0.5);
        }

        /* Fleet Section */
        .fleet-section {
            padding: 100px 8%;
        }

        .section-header {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-header h2 {
            font-size: 3rem;
            font-weight: 900;
            margin-bottom: 15px;
        }

        .section-header h2 span {
            color: var(--gold);
        }

        /* Filter Buttons */
        .filter-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 50px;
            flex-wrap: wrap;
        }

        .filter-btn {
            background: var(--card-bg);
            color: var(--text-muted);
            border: 1px solid rgba(255,255,255,0.05);
            padding: 10px 25px;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 600;
            transition: var(--transition);
        }

        .filter-btn.active, .filter-btn:hover {
            background: var(--gold);
            color: #000;
            border-color: var(--gold);
            box-shadow: 0 5px 15px rgba(212, 175, 55, 0.3);
        }

        /* Cars Grid & 3D Cards */
        .cars-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 35px;
        }

        .car-card {
            background: var(--card-bg);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(212, 175, 55, 0.1);
            transition: var(--transition);
            transform-style: preserve-3d;
            perspective: 1000px;
            position: relative;
        }

        .car-card:hover {
            transform: translateY(-10px) rotateX(2deg) rotateY(-2deg);
            border-color: var(--gold);
            box-shadow: 0 20px 40px rgba(0,0,0,0.8), 0 0 20px rgba(212, 175, 55, 0.15);
        }

        .car-img-box {
            width: 100%;
            height: 240px;
            overflow: hidden;
            position: relative;
        }

        .car-img-box img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .car-card:hover .car-img-box img {
            transform: scale(1.1);
        }

        .car-badge {
            position: absolute;
            top: 15px;
            left: 15px;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(5px);
            color: var(--gold);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 14px;
            font-weight: 700;
            border: 1px solid var(--gold);
        }

        .car-content {
            padding: 25px;
        }

        .car-title {
            font-size: 22px;
            font-weight: 800;
            margin-bottom: 10px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .car-price {
            color: var(--gold);
            font-size: 20px;
        }

        .car-specs {
            display: flex;
            justify-content: space-between;
            margin: 20px 0;
            padding: 15px 0;
            border-top: 1px solid rgba(255,255,255,0.05);
            border-bottom: 1px solid rgba(255,255,255,0.05);
            color: var(--text-muted);
            font-size: 14px;
        }

        .car-specs span i {
            color: var(--gold);
            margin-left: 5px;
        }

        .details-btn {
            width: 100%;
            padding: 12px;
            background: transparent;
            color: var(--text-main);
            border: 2px solid var(--gold);
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            transition: var(--transition);
        }

        .details-btn:hover {
            background: var(--gold);
            color: #000;
        }

        /* Popup Modal 3D Details */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.85);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition);
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background: #161616;
            width: 90%;
            max-width: 800px;
            border-radius: 20px;
            border: 1px solid var(--gold);
            overflow: hidden;
            transform: scale(0.8);
            transition: var(--transition);
            position: relative;
        }

        .modal-overlay.active .modal-content {
            transform: scale(1);
        }

        .modal-header {
            padding: 20px;
            background: #1f1f1f;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }

        .close-modal {
            background: none;
            border: none;
            color: var(--text-main);
            font-size: 24px;
            cursor: pointer;
            transition: var(--transition);
        }

        .close-modal:hover {
            color: var(--gold);
        }

        .modal-body {
            padding: 30px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }

        @media(max-width: 768px) {
            .modal-body { grid-template-columns: 1fr; }
            .hero h1 { font-size: 2.8rem; }
            .nav-links { display: none; }
        }

        .modal-img {
            width: 100%;
            height: 300px;
            object-fit: cover;
            border-radius: 10px;
        }

        .modal-info h3 {
            font-size: 28px;
            color: var(--gold);
            margin-bottom: 10px;
        }

        .modal-info p {
            color: var(--text-muted);
            margin-bottom: 20px;
            line-height: 1.6;
        }

        .modal-features {
            list-style: none;
            margin-bottom: 25px;
        }

        .modal-features li {
            margin-bottom: 8px;
            color: var(--text-main);
            font-size: 15px;
        }

        .modal-features li i {
            color: var(--gold);
            margin-left: 8px;
        }

        /* Floating WhatsApp */
        .whatsapp-float {
            position: fixed;
            bottom: 30px;
            left: 30px;
            background: #25d366;
            color: #fff;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
            box-shadow: 0 10px 25px rgba(37, 211, 102, 0.4);
            z-index: 1000;
            text-decoration: none;
            transition: var(--transition);
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
        }

        footer {
            text-align: center;
            padding: 40px;
            background: #080808;
            color: var(--text-muted);
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        @keyframes fadeInRight {
            from { opacity: 0; transform: translateX(50px); }
            to { opacity: 1; transform: translateX(0); }
        }
    </style>
</head>
<body>

    <!-- الهيدر -->
    <header>
        <a href="#" class="logo">TWO S <span>CARS</span></a>
        <ul class="nav-links">
            <li><a href="#">الرئيسية</a></li>
            <li><a href="#fleet">الأسطول الفاخر</a></li>
            <li><a href="https://wa.me/212762398737" target="_blank">تواصل معنا</a></li>
        </ul>
    </header>

    <!-- الواجهة الرئيسية -->
    <section class="hero">
        <div class="hero-content">
            <h1>عالم من <span>الفخامة</span> تحت تصرفك بسلا</h1>
            <p>اختر سيارة أحلامك من أحدث أسطول سيارات الأداء العالي والرفاهية المطلقة، مع خدمة استلام فورية على مدار الساعة.</p>
            <a href="#fleet" class="btn">استكشف الأسطول الآن</a>
        </div>
    </section>

    <!-- قسم الأسطول مع نظام الفلترة -->
    <section class="fleet-section" id="fleet">
        <div class="section-header">
            <h2>أسطول <span>السيارات المتاحة</span></h2>
            <p style="color: var(--text-muted);">انقر على أي سيارة لمعرفة التفاصيل الكاملة والمميزات</p>
        </div>

        <div class="filter-container">
            <button class="filter-btn active" onclick="filterCars('all')">الكل</button>
            <button class="filter-btn" onclick="filterCars('luxury')">سيارات فخمة</button>
            <button class="filter-btn" onclick="filterCars('sport')">رياضية خارقة</button>
            <button class="filter-btn" onclick="filterCars('suv')">عائلية SUV</button>
        </div>

        <div class="cars-grid" id="carsGrid">
            <!-- سيارة 1 -->
            <div class="car-card" data-category="luxury">
                <div class="car-img-box">
                    <span class="car-badge">VIP فخامة</span>
                    <img src="https://images.unsplash.com/photo-1555215695-3004980ad54e?auto=format&fit=crop&w=600&q=80" alt="Mercedes">
                </div>
                <div class="car-content">
                    <div class="car-title">
                        <span>مرسيدس بنز الفئة S</span>
                        <span class="car-price">800 درهم</span>
                    </div>
                    <div class="car-specs">
                        <span><i class="fa-solid fa-gauge-high"></i> 3.0L V6</span>
                        <span><i class="fa-solid fa-gear"></i> أوتوماتيك</span>
                        <span><i class="fa-solid fa-user-shield"></i> تأمين شامل</span>
                    </div>
                    <button class="details-btn" onclick="openModal('مرسيدس بنز الفئة S', '800 درهم/يوم', 'https://images.unsplash.com/photo-1555215695-3004980ad54e?auto=format&fit=crop&w=600&q=80', 'تعتبر مرسيدس الفئة S العنوان الأبرز للفخامة المطلقة على الطرقات، مجهزة بمقصورة جلدية فاخرة، نظام صوتي محيطي عالي الجودة، وتقنيات قيادة ذاتية متطورة لضمان أقصى درجات الراحة لك ولعائلتك.', ['مقصورة جلدية ملكية مع تكييف مستقل', 'سقف بانورامي واسع', 'كاميرات 360 درجة ونظام ركن ذكي', 'حساسات الاصطدام ومثبت السرعة التكيفي'])">عرض التفاصيل</button>
                </div>
            </div>

            <!-- سيارة 2 -->
            <div class="car-card" data-category="sport">
                <div class="car-img-box">
                    <span class="car-badge">أداء عالي</span>
                    <img src="https://images.unsplash.com/photo-1605559424843-9e4c228bf1c2?auto=format&fit=crop&w=600&q=80" alt="BMW">
                </div>
                <div class="car-content">
                    <div class="car-title">
                        <span>بي إم دبليو M4 كوبيه</span>
                        <span class="car-price">950 درهم</span>
                    </div>
                    <div class="car-specs">
                        <span><i class="fa-solid fa-gauge-high"></i> 510 حصان</span>
                        <span><i class="fa-solid fa-gear"></i> رياضي</span>
                        <span><i class="fa-solid fa-bolt"></i> تسارع خيالي</span>
                    </div>
                    <button class="details-btn" onclick="openModal('بي إم دبليو M4 كوبيه', '950 درهم/يوم', 'https://images.unsplash.com/photo-1605559424843-9e4c228bf1c2?auto=format&fit=crop&w=600&q=80', 'لعشاق السرعة والأداء الرياضي الشرس، تمنحك BMW M4 تجربة قيادة مكهربة ومثير للأعصاب بفضل محركها القوي وتصميمها الديناميكي الجريء.', ['محرك TwinPower Turbo بقوة 510 حصان', 'مقاعد رياضية مخصصة للسرعات العالية', 'نظام عادم رياضي بصوت هادر', 'أنظمة تحكم متطورة بالثبات الانجرافى'])">عرض التفاصيل</button>
                </div>
            </div>

            <!-- سيارة 3 -->
            <div class="car-card" data-category="suv">
                <div class="car-img-box">
                    <span class="car-badge">دفع رباعي</span>
                    <img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?auto=format&fit=crop&w=600&q=80" alt="Range Rover">
                </div>
                <div class="car-content">
                    <div class="car-title">
                        <span>رانج روفر إيفوك</span>
                        <span class="car-price">900 درهم</span>
                    </div>
                    <div class="car-specs">
                        <span><i class="fa-solid fa-gauge-high"></i> 4x4 دفع رباعي</span>
                        <span><i class="fa-solid fa-gear"></i> أوتوماتيك</span>
                        <span><i class="fa-solid fa-suitcase"></i> مساحة واسعة</span>
                    </div>
                    <button class="details-btn" onclick="openModal('رانج روفر إيفوك', '900 درهم/يوم', 'https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?auto=format&fit=crop&w=600&q=80', 'السيارة المثالية للرحلات الطويلة والمغامرات داخل وخارج المدينة، تجمع بين هيبة الدفع الرباعي وفخامة الصالونات البريطانية العريقة.', ['نظام دفع رباعي ذكي لجميع التضاريس', 'شاشات تعمل باللمس بتقنية Pivi Pro', 'إضاءة محيطية متعددة الألوان', 'مساحة تخزين خلفية واسعة جدا'])">عرض التفاصيل</button>
                </div>
            </div>
        </div>
    </section>

    <!-- نافذة تفاصيل السيارة (Modal) -->
    <div class="modal-overlay" id="carModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 id="modalTitle" style="color: var(--gold); font-size: 22px;">معلومات السيارة</h3>
                <button class="close-modal" onclick="closeModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div>
                    <img id="modalImg" src="" alt="" class="modal-img">
                </div>
                <div class="modal-info">
                    <h3 id="modalName"></h3>
                    <p id="modalPrice" style="font-size: 20px; font-weight: 800; color: var(--gold); margin-bottom: 15px;"></p>
                    <p id="modalDesc"></p>
                    <ul class="modal-features" id="modalFeaturesList"></ul>
                    <a id="whatsappLink" href="#" target="_blank" class="btn" style="width: 100%; text-align: center; margin-top: 10px;">
                        <i class="fa-brands fa-whatsapp"></i> احجز هذه السيارة الآن
                    </a>
                </div>
            </div>
        </div>
    </div>

    <!-- زر الواتساب العائم -->
    <a href="https://wa.me/212762398737" class="whatsapp-float" target="_blank">
        <i class="fa-brands fa-whatsapp"></i>
    </a>

    <footer>
        <p>&copy; 2026 Two S Cars بسلا. جميع الحقوق محفوظة.</p>
    </footer>

    <!-- سكربت التفاعل والفلترة والـ Modal -->
    <script>
        function openModal(name, price, img, desc, features) {
            document.getElementById('modalName').innerText = name;
            document.getElementById('modalPrice').innerText = price;
            document.getElementById('modalImg').src = img;
            document.getElementById('modalDesc').innerText = desc;
            
            const featuresList = document.getElementById('modalFeaturesList');
            featuresList.innerHTML = '';
            features.forEach(feat => {
                featuresList.innerHTML += `<li><i class="fa-solid fa-check-circle"></i> ${feat}</li>`;
            });

            // ربط زر الحجز بالواتساب مع رسالة تلقائية تتضمن اسم السيارة
            const waMsg = encodeURIComponent(`سلام عليكم، بغيت نسأل على كراء سيارة: ${name} (${price}) اللي شفيتها فالموقع.`);
            document.getElementById('whatsappLink').href = `https://wa.me/212762398737?text=${waMsg}`;

            document.getElementById('carModal').classList.add('active');
        }

        function closeModal() {
            document.getElementById('carModal').classList.remove('active');
        }

        // نظام الفلترة
        function filterCars(category) {
            const cards = document.querySelectorAll('.car-card');
            const buttons = document.querySelectorAll('.filter-btn');

            buttons.forEach(btn => btn.classList.remove('active'));
            event.target.classList.add('active');

            cards.variable = cards.forEach(card => {
                if (category === 'all' || card.dataset.category === category) {
                    card.style.display = 'block';
                } else {
                    card.style.display = 'none';
                }
            });
        }
    </script>
</body>
</html>
# Two-s-cars
