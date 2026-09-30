<!DOCTYPE html>
<html lang="ru" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- SEO-мета-теги -->
    <title>TechPulse — Главное издание о высоких технологиях, ИИ и гаджетах</title>
    <meta name="description" content="Ведущий IT-портал: свежие новости искусственного интеллекта, обзоры смартфонов, кибербезопасность и аналитика стартапов. Разработано группой ПО-245.">
    <meta name="keywords" content="IT новости, технологии, искусственный интеллект, гаджеты, смартфоны, программирование, стартапы">
    <meta name="author" content="ПО-245">

    <style>
        /* CSS Переменные для Светлой и Тёмной тем */
        :root {
            --bg-color: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #1e293b;
            --text-muted: #64748b;
            --accent-color: #3b82f6;
            --accent-hover: #2563eb;
            --border-color: #e2e8f0;
            --header-bg: rgba(255, 255, 255, 0.85);
            --badge-bg: #eff6ff;
            --badge-text: #1d4ed8;
            --shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.05);
            --hover-shadow: 0 10px 25px -5px rgba(59, 130, 246, 0.15);
            --ticker-bg: #0f172a;
            --ticker-text: #f8fafc;
        }

        [data-theme="dark"] {
            --bg-color: #0b0f19;
            --card-bg: #111827;
            --text-main: #f3f4f6;
            --text-muted: #9ca3af;
            --accent-color: #60a5fa;
            --accent-hover: #3b82f6;
            --border-color: #1f2937;
            --header-bg: rgba(17, 24, 39, 0.85);
            --badge-bg: #1e3a8a;
            --badge-text: #93c5fd;
            --shadow: 0 4px 20px -2px rgba(0, 0, 0, 0.3);
            --hover-shadow: 0 10px 25px -5px rgba(96, 165, 250, 0.2);
            --ticker-bg: #1f2937;
            --ticker-text: #e5e7eb;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-main);
            line-height: 1.6;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        /* 🚀 Бегущая строка срочных новостей (Breaking News) */
        .breaking-ticker {
            background-color: var(--ticker-bg);
            color: var(--ticker-text);
            padding: 8px 20px;
            font-size: 13px;
            display: flex;
            align-items: center;
            gap: 15px;
            overflow: hidden;
            white-space: nowrap;
        }

        .ticker-badge {
            background: #ef4444;
            color: white;
            padding: 2px 8px;
            border-radius: 4px;
            font-weight: 700;
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .ticker-content {
            display: inline-block;
            animation: marquee 25s linear infinite;
        }

        @keyframes marquee {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* 🏛 Шапка сайта */
        .header {
            background-color: var(--header-bg);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .header-container {
            max-width: 1300px;
            margin: 0 auto;
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo-box {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 24px;
            font-weight: 800;
            color: var(--accent-color);
            cursor: pointer;
            letter-spacing: -0.5px;
        }

        .logo-icon {
            background: linear-gradient(135deg, #3b82f6, #8b5cf6);
            color: white;
            width: 38px;
            height: 38px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
            font-size: 20px;
        }

        .nav-menu {
            display: flex;
            gap: 25px;
        }

        .nav-menu a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 600;
            font-size: 14px;
            transition: color 0.2s;
        }

        .nav-menu a:hover, .nav-menu a.active {
            color: var(--accent-color);
        }

        .header-actions {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .search-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }

        .search-input {
            padding: 8px 14px 8px 36px;
            border: 1px solid var(--border-color);
            background-color: var(--card-bg);
            color: var(--text-main);
            border-radius: 8px;
            outline: none;
            font-size: 13px;
            width: 220px;
            transition: all 0.3s;
        }

        .search-input:focus {
            border-color: var(--accent-color);
            box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.15);
            width: 260px;
        }

        .search-icon-abs {
            position: absolute;
            left: 12px;
            font-size: 14px;
            color: var(--text-muted);
            pointer-events: none;
        }

        .theme-toggle-btn {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            width: 38px;
            height: 38px;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            transition: background 0.2s, border-color 0.2s;
        }

        .theme-toggle-btn:hover {
            border-color: var(--accent-color);
        }

        /* Теги быстрого выбора тем */
        .sub-header-tags {
            max-width: 1300px;
            margin: 15px auto 0;
            padding: 0 20px;
            display: flex;
            gap: 8px;
            overflow-x: auto;
            scrollbar-width: none;
        }
        .sub-header-tags::-webkit-scrollbar { display: none; }

        .tag-chip {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            color: var(--text-muted);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
            cursor: pointer;
            white-space: nowrap;
            transition: all 0.2s;
        }

        .tag-chip:hover, .tag-chip.active {
            background-color: var(--accent-color);
            color: white;
            border-color: var(--accent-color);
        }

        /* 📰 Основная сетка контента */
        .main-content {
            max-width: 1300px;
            margin: 25px auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 2.8fr 1fr;
            gap: 30px;
            flex-grow: 1;
            width: 100%;
        }

        .section-header-title {
            font-size: 20px;
            font-weight: 700;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section-header-title::before {
            content: '';
            width: 4px;
            height: 20px;
            background-color: var(--accent-color);
            border-radius: 2px;
        }

        /* Сетка новостных карточек */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .news-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, box-shadow 0.3s ease, border-color 0.3s;
            display: flex;
            flex-direction: column;
            cursor: pointer;
        }

        .news-card:hover {
            transform: translateY(-4px);
            box-shadow: var(--hover-shadow);
            border-color: var(--accent-color);
        }

        /* Главная новость сетки */
        .news-card.featured {
            grid-column: span 2;
            grid-row: span 2;
        }

        .card-img-wrap {
            position: relative;
            width: 100%;
            height: 180px;
            overflow: hidden;
            background-color: var(--border-color);
        }

        .news-card.featured .card-img-wrap {
            height: 280px;
        }

        .card-img-wrap img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .news-card:hover .card-img-wrap img {
            transform: scale(1.04);
        }

        .badge-category {
            position: absolute;
            top: 12px;
            left: 12px;
            background-color: var(--badge-bg);
            color: var(--badge-text);
            padding: 4px 10px;
            font-size: 11px;
            font-weight: 700;
            border-radius: 6px;
            backdrop-filter: blur(4px);
        }

        .card-details {
            padding: 16px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .card-meta-info {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--text-muted);
            margin-bottom: 8px;
        }

        .card-title {
            font-size: 16px;
            font-weight: 700;
            color: var(--text-main);
            margin-bottom: 10px;
            line-height: 1.4;
        }

        .news-card.featured .card-title {
            font-size: 22px;
        }

        .card-desc {
            font-size: 13px;
            color: var(--text-muted);
            margin-bottom: 16px;
            flex-grow: 1;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;
        }

        .card-footer-action {
            font-size: 13px;
            font-weight: 600;
            color: var(--accent-color);
            display: flex;
            align-items: center;
            gap: 5px;
        }

        /* 📌 Боковая панель */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 25px;
        }

        .sidebar-widget {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 14px;
            padding: 20px;
            box-shadow: var(--shadow);
        }

        .widget-title {
            font-size: 16px;
            font-weight: 700;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 8px;
            color: var(--text-main);
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 10px;
        }

        .trending-list {
            list-style: none;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .trending-item {
            display: flex;
            gap: 12px;
            align-items: flex-start;
            cursor: pointer;
            padding-bottom: 12px;
            border-bottom: 1px dashed var(--border-color);
            transition: opacity 0.2s;
        }

        .trending-item:last-child {
            border-bottom: none;
            padding-bottom: 0;
        }

        .trending-item:hover {
            opacity: 0.8;
        }

        .trending-index {
            font-size: 18px;
            font-weight: 800;
            color: var(--accent-color);
            min-width: 22px;
        }

        .trending-content h4 {
            font-size: 13px;
            font-weight: 600;
            color: var(--text-main);
            line-height: 1.35;
            margin-bottom: 4px;
        }

        .trending-meta {
            font-size: 11px;
            color: var(--text-muted);
        }

        /* Блок подписки в сайдбаре */
        .newsletter-box p {
            font-size: 13px;
            color: var(--text-muted);
            margin-bottom: 12px;
        }

        .newsletter-input {
            width: 100%;
            padding: 10px;
            border: 1px solid var(--border-color);
            background-color: var(--bg-color);
            color: var(--text-main);
            border-radius: 8px;
            font-size: 13px;
            margin-bottom: 8px;
            outline: none;
        }

        .newsletter-btn {
            width: 100%;
            padding: 10px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            border-radius: 8px;
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
            transition: background 0.2s;
        }

        .newsletter-btn:hover {
            background-color: var(--accent-hover);
        }

        /* 🪟 Модальное окно полной статьи */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(5px);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s, visibility 0.3s;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-container {
            background-color: var(--card-bg);
            color: var(--text-main);
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            border-radius: 16px;
            overflow-y: auto;
            padding: 40px;
            position: relative;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            transform: translateY(20px);
            transition: transform 0.3s ease;
        }

        .modal-overlay.active .modal-container {
            transform: translateY(0);
        }

        .modal-close-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            color: var(--text-main);
            width: 36px;
            height: 36px;
            border-radius: 50%;
            font-size: 18px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.2s;
        }

        .modal-close-btn:hover {
            background-color: #ef4444;
            color: white;
            border-color: #ef4444;
        }

        .modal-banner {
            width: 100%;
            height: 320px;
            object-fit: cover;
            border-radius: 12px;
            margin-bottom: 20px;
        }

        .modal-category-badge {
            display: inline-block;
            background-color: var(--badge-bg);
            color: var(--badge-text);
            padding: 4px 10px;
            font-size: 12px;
            font-weight: 700;
            border-radius: 6px;
            margin-bottom: 12px;
        }

        .modal-title-text {
            font-size: 26px;
            font-weight: 800;
            line-height: 1.3;
            margin-bottom: 10px;
        }

        .modal-meta-row {
            font-size: 13px;
            color: var(--text-muted);
            margin-bottom: 25px;
            display: flex;
            gap: 20px;
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 15px;
        }

        .modal-body-content {
            font-size: 15px;
            color: var(--text-main);
            line-height: 1.8;
            display: flex;
            flex-direction: column;
            gap: 16px;
        }

        .modal-body-content h3 {
            font-size: 18px;
            font-weight: 700;
            margin-top: 10px;
            color: var(--accent-color);
        }

        .modal-body-content ul {
            padding-left: 20px;
            color: var(--text-main);
        }

        .modal-body-content li {
            margin-bottom: 6px;
        }

        .article-reactions {
            display: flex;
            gap: 15px;
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px solid var(--border-color);
        }

        .reaction-btn {
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            padding: 8px 14px;
            border-radius: 8px;
            font-size: 13px;
            color: var(--text-main);
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 6px;
            transition: transform 0.1s, border-color 0.2s;
        }

        .reaction-btn:hover {
            border-color: var(--accent-color);
            transform: scale(1.05);
        }

        /* 🔻 Футер */
        .footer {
            background-color: var(--ticker-bg);
            color: var(--ticker-text);
            padding: 50px 0 20px;
            margin-top: auto;
            border-top: 1px solid var(--border-color);
        }

        .footer-grid {
            max-width: 1300px;
            margin: 0 auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 2fr 1fr 1fr;
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-col h4 {
            font-size: 16px;
            margin-bottom: 15px;
            color: var(--accent-color);
        }

        .footer-col p, .footer-col ul {
            font-size: 13px;
            color: #94a3b8;
            list-style: none;
        }

        .footer-col ul li {
            margin-bottom: 8px;
        }

        .footer-col ul li a {
            color: #94a3b8;
            text-decoration: none;
            transition: color 0.2s;
        }

        .footer-col ul li a:hover {
            color: white;
        }

        .footer-bottom {
            max-width: 1300px;
            margin: 0 auto;
            padding: 20px 20px 0;
            border-top: 1px solid rgba(255,255,255,0.1);
            text-align: center;
            font-size: 12px;
            color: #64748b;
        }

        /* Кнопка «Наверх» */
        .scroll-top {
            position: fixed;
            bottom: 25px;
            right: 25px;
            background-color: var(--accent-color);
            color: white;
            border: none;
            width: 44px;
            height: 44px;
            border-radius: 12px;
            font-size: 18px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(59, 130, 246, 0.3);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 99;
            transition: background 0.2s;
        }

        .scroll-top.visible {
            display: flex;
        }

        .scroll-top:hover {
            background-color: var(--accent-hover);
        }

        @media (max-width: 1024px) {
            .main-content { grid-template-columns: 1fr; }
            .news-grid { grid-template-columns: repeat(2, 1fr); }
            .news-card.featured { grid-column: span 2; }
            .footer-grid { grid-template-columns: 1fr; }
        }

        @media (max-width: 768px) {
            .nav-menu { display: none; }
            .news-grid { grid-template-columns: 1fr; }
            .news-card.featured { grid-column: span 1; grid-row: span 1; }
            .search-input { width: 150px; }
        }
    </style>
</head>
<body>

    <!-- ⚡ Бегущая строка -->
    <div class="breaking-ticker">
        <span class="ticker-badge">Live</span>
        <div class="ticker-content">
            ⚡ Релиз флагманских чипов нового поколения • 🚀 Рост инвестиций в квантовые вычисления на 45% • 💡 OpenAI анонсировала масштабное обновление языковой модели • 🔒 Новые стандарты кибербезопасности для облачных хранилищ
        </div>
    </div>

    <!-- 🏛 Шапка сайта -->
    <header class="header">
        <div class="header-container">
            <div class="logo-box" onclick="location.reload();">
                <div class="logo-icon">⚡</div>
                <span>TechPulse</span>
            </div>
            <nav class="nav-menu">
                <a href="#" class="active" onclick="filterCategory('all', this); return false;">Все новости</a>
                <a href="#" onclick="filterCategory('Искусственный интеллект', this); return false;">ИИ</a>
                <a href="#" onclick="filterCategory('Гаджеты', this); return false;">Гаджеты</a>
                <a href="#" onclick="filterCategory('Софт', this); return false;">Софт</a>
                <a href="#" onclick="filterCategory('Стартапы', this); return false;">Стартапы</a>
            </nav>
            <div class="header-actions">
                <div class="search-wrapper">
                    <span class="search-icon-abs">🔍</span>
                    <input type="text" id="searchInput" class="search-input" placeholder="Поиск по статьям..." oninput="searchNews()">
                </div>
                <button class="theme-toggle-btn" id="themeToggleBtn" onclick="toggleTheme()" title="Сменить тему">🌙</button>
            </div>
        </div>

        <div class="sub-header-tags">
            <span class="tag-chip active" onclick="filterCategory('all', this)">Все</span>
            <span class="tag-chip" onclick="filterCategory('Искусственный интеллект', this)">🧠 Искусственный интеллект</span>
            <span class="tag-chip" onclick="filterCategory('Гаджеты', this)">📱 Гаджеты и железо</span>
            <span class="tag-chip" onclick="filterCategory('Безопасность', this)">🛡️ Безопасность</span>
            <span class="tag-chip" onclick="filterCategory('Игры', this)">🎮 Игровые технологии</span>
            <span class="tag-chip" onclick="filterCategory('Стартапы', this)">🚀 Стартапы</span>
            <span class="tag-chip" onclick="filterCategory('Облака', this)">☁️ Облачные решения</span>
        </div>
    </header>

    <!-- 📰 Основная сетка контента -->
    <main class="main-content">
        <section class="news-column">
            <h2 class="section-header-title" id="sectionHeading">Лента публикаций</h2>
            
            <div class="news-grid" id="newsContainer">
                
                <!-- 1. Главная карточка -->
                <article class="news-card featured" data-category="Искусственный интеллект" onclick="openArticle(this)">
                    <div class="card-img-wrap">
                        <img src="https://images.unsplash.com/photo-1618005182384-a83a8bd57fbe?auto=format&fit=crop&w=900&q=80" alt="ИИ">
                        <span class="badge-category">Искусственный интеллект</span>
                    </div>
                    <div class="card-details">
                        <div class="card-meta-info">
                            <span>📅 30 сентября 2026</span>
                            <span>⏱ 4 мин чтения</span>
                        </div>
                        <h2 class="card-title">Революция в мире ИИ: представлена первая мультимодальная модель с полным контекстным пониманием</h2>
                        <p class="card-desc">Новая разработка способна в реальном времени анализировать сложнейшие инженерные чертежи, писать код без багов и оптимизировать энергопотребление дата-центров.</p>
                        <div class="card-footer-action">Читать полную версию &rarr;</div>
                    </div>
                </article>

                <!-- 2. Карточка -->
                <article class="news-card" data-category="Гаджеты" onclick="openArticle(this)">
                    <div class="card-img-wrap">
                        <img src="https://images.unsplash.com/photo-1519389950473-47ba0277781c?auto=format&fit=crop&w=600&q=80" alt="Смартфоны">
                        <span class="badge-category">Гаджеты</span>
                    </div>
                    <div class="card-details">
                        <div class="card-meta-info">
                            <span>📅 30 сен</span>
                            <span>⏱ 3 мин</span>
                        </div>
                        <h3 class="card-title">Большой обзор осенних флагманских смартфонов</h3>
                        <p class="card-desc">Тестируем автономность, качество ночной съемки и производительность процессоров.</p>
                        <div class="card-footer-action">Читать &rarr;</div>
                    </div>
                </article>

                <!-- 3. Карточка -->
                <article class="news-card" data-category="Безопасность" onclick="openArticle(this)">
                    <div class="card-img-wrap">
                        <img src="https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?auto=format&fit=crop&w=600&q=80" alt="Безопасность">
                        <span class="badge-category">Безопасность</span>
                    </div>
                    <div class="card-details">
                        <div class="card-meta-info">
                            <span>📅 29 сен</span>
                            <span>⏱ 5 мин</span>
                        </div>
                        <h3 class="card-title">Кибербезопасность в эпоху квантовых вычислений</h3>
                        <p class="card-desc">Как крупные корпорации перестраивают защиту конфиденциальных баз данных.</p>
                        <div class="card-footer-action">Читать &rarr;</div>
                    </div>
                </article>

                <!-- 4. Карточка -->
                <article class="news-card" data-category="Игры" onclick="openArticle(this)">
                    <div class="card-img-wrap">
                        <img src="https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&w=600&q=80" alt="Игры">
                        <span class="badge-category">Игры</span>
                    </div>
                    <div class="card-details">
                        <div class="card-meta-info">
                            <span>📅 29 сен</span>
                            <span>⏱ 2 мин</span>
                        </div>
                        <h3 class="card-title">Анонс новой графической архитектуры для геймеров</h3>
                        <p class="card-desc">Трассировка лучей нового поколения и улучшенные алгоритмы масштабирования.</p>
                        <div class="card-footer-action">Читать &rarr;</div>
                    </div>
                </article>

                <!-- 5. Карточка -->
                <article class="news-card" data-category="Стартапы" onclick="openArticle(this)">
                    <div class="card-img-wrap">
                        <img src="https://images.unsplash.com/photo-1531482615713-2afd69097998?auto=format&fit=crop&w=600&q=80" alt="Стартапы">
                        <span class="badge-category">Стартапы</span>
                    </div>
                    <div class="card-details">
                        <div class="card-meta-info">
                            <span>📅 28 сен</span>
                            <span>⏱ 3 мин</span>
                        </div>
                        <h3 class="card-title">Инвестиции в зеленую энергетику выросли на 40%</h3>
                        <p class="card-desc">Какие технологические стартапы получили венчурное финансирование.</p>
                        <div class="card-footer-action">Читать &rarr;</div>
                    </div>
                </article>

                <!-- 6. Карточка -->
                <article class="news-card" data-category="Софт" onclick="openArticle(this)">
                    <div class="card-img-wrap">
                        <img src="https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=600&q=80" alt="Софт">
                        <span class="badge-category">Софт</span>
                    </div>
                    <div class="card-details">
                        <div class="card-meta-info">
                            <span>📅 28 сен</span>
                            <span>⏱ 4 мин</span>
                        </div>
                        <h3 class="card-title">Вышел крупный релиз популярной IDE</h3>
                        <p class="card-desc">Встроенный локальный ИИ-ассистент и двукратное ускорение индексации кода.</p>
                        <div class="card-footer-action">Читать &rarr;</div>
                    </div>
                </article>

            </div>
        </section>

        <!-- 📌 Сайдбар -->
        <aside class="sidebar">
            <div class="sidebar-widget">
                <h3 class="widget-title">🔥 Популярное за неделю</h3>
                <ul class="trending-list">
                    <li class="trending-item" onclick="openTrendingArticle('ТОП-10 расширений для разработчиков', 'Разработка', 'https://images.unsplash.com/photo-1461749280684-dccba630e2f6?auto=format&fit=crop&w=600&q=80')">
                        <span class="trending-index">1</span>
                        <div class="trending-content">
                            <h4>ТОП-10 расширений для разработчиков</h4>
                            <span class="trending-meta">👁 14.2 тыс. просмотров</span>
                        </div>
                    </li>
                    <li class="trending-item" onclick="openTrendingArticle('Как пройти интервью на Senior-позицию', 'Карьера', 'https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=600&q=80')">
                        <span class="trending-index">2</span>
                        <div class="trending-content">
                            <h4>Как пройти интервью на Senior-позицию</h4>
                            <span class="trending-meta">👁 11.8 тыс. просмотров</span>
                        </div>
                    </li>
                    <li class="trending-item" onclick="openTrendingArticle('Обзор новых процессоров: стоит ли переходить', 'Железо', 'https://images.unsplash.com/photo-1591799264318-7e6ef8ddb7ea?auto=format&fit=crop&w=600&q=80')">
                        <span class="trending-index">3</span>
                        <div class="trending-content">
                            <h4>Обзор новых процессоров: стоит ли переходить</h4>
                            <span class="trending-meta">👁 9.5 тыс. просмотров</span>
                        </div>
                    </li>
                </ul>
            </div>

            <div class="sidebar-widget newsletter-box">
                <h3 class="widget-title">📬 Рассылка TechPulse</h3>
                <p>Получайте подборку главных IT-новостей прямо на почту раз в неделю.</p>
                <input type="email" class="newsletter-input" placeholder="Ваш email...">
                <button class="newsletter-btn" onclick="alert('Спасибо за подписку!')">Подписаться</button>
            </div>
        </aside>
    </main>

    <!-- 🪟 Модальное окно полной статьи -->
    <div class="modal-overlay" id="articleModal" onclick="closeModalOnOutside(event)">
        <div class="modal-container">
            <button class="modal-close-btn" onclick="closeArticle()">&times;</button>
            <img src="" alt="" class="modal-banner" id="modalImg">
            <span class="modal-category-badge" id="modalCategory">Категория</span>
            <h2 class="modal-title-text" id="modalTitle">Заголовок статьи</h2>
            <div class="modal-meta-row">
                <span id="modalDate">📅 Дата</span>
                <span id="modalTime">⏱ Время чтения</span>
            </div>
            <div class="modal-body-content" id="modalBody">
                <!-- Полный текст статьи подставляется динамически через JS -->
            </div>
            <div class="article-reactions">
                <button class="reaction-btn" onclick="likeArticle(this)">👍 Полезно (<span id="likeCount">42</span>)</button>
                <button class="reaction-btn" onclick="shareArticle()">🔗 Поделиться</button>
            </div>
        </div>
    </div>

    <!-- 🔻 Футер -->
    <footer class="footer">
        <div class="footer-grid">
            <div class="footer-col">
                <h4>TechPulse</h4>
                <p>Главное независимое издание о высоких технологиях, искусственном интеллекте, гаджетах и современной разработке программного обеспечения. Проект группы ПО-245.</p>
            </div>
            <div class="footer-col">
                <h4>Разделы</h4>
                <ul>
                    <li><a href="#" onclick="filterCategory('Искусственный интеллект', document.querySelector('.sub-header-tags')); return false;">Искусственный интеллект</a></li>
                    <li><a href="#" onclick="filterCategory('Гаджеты', document.querySelector('.sub-header-tags')); return false;">Гаджеты и железо</a></li>
                    <li><a href="#" onclick="filterCategory('Безопасность', document.querySelector('.sub-header-tags')); return false;">Кибербезопасность</a></li>
                    <li><a href="#" onclick="filterCategory('Стартапы', document.querySelector('.sub-header-tags')); return false;">Стартапы и бизнес</a></li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>Контакты</h4>
                <ul>
                    <li>Email: contact@techpulse.ru</li>
                    <li>Пресс-служба: press@techpulse.ru</li>
                    <li>GitHub проекта: ПО-245</li>
                </ul>
            </div>
        </div>
        <div class="footer-bottom">
            &copy; 2026 TechPulse. Все права защищены. Разработано учебной группой ПО-245.
        </div>
    </footer>

    <button class="scroll-top" id="scrollTopBtn" onclick="scrollToTop()">&#8593;</button>

    <!-- Скрипты -->
    <script>
        // База данных полных текстов статей по их заголовкам
        const fullArticlesContent = {
            "Революция в мире ИИ: представлена первая мультимодальная модель с полным контекстным пониманием": `
                <p><strong>Новая разработка способна в реальном времени анализировать сложнейшие инженерные чертежи, писать код без багов и оптимизировать энергопотребление дата-центров.</strong></p>
                <p>Мировая IT-индустрия обсуждает громкий анонс лаборатории передовых исследований. Инженерам удалось создать мультимодальную архитектуру, которая не просто распознает текстовые и визуальные запросы, но и строит причинно-следственные связи между ними на уровне человеческого эксперта.</p>
                <h3>Ключевые особенности новой системы</h3>
                <ul>
                    <li>Полная интеграция мультимодального ввода: обработка видеопотока, аудио, графиков и исходного кода программ в одном контекстном окне.</li>
                    <li>Снижение энергопотребления инференса на 35% благодаря инновационной структуре разреженных сетей (Sparse Mixture of Experts).</li>
                    <li>Встроенные верификаторы кода, автоматически находящие уязвимости безопасности еще на этапе написания логики.</li>
                </ul>
                <p>По словам ведущих разработчиков проекта, внедрение технологии в коммерческий сектор начнется уже в следующем квартале. Ожидается, что первыми новинку опробуют инженеры-авиастроители и крупные облачные провайдеры для автоматизации рутинных процессов.</p>
                <p><em>Проект разработан при поддержке академического сообщества и группы исследователей ПО-245.</em></p>
            `,
            "Большой обзор осенних флагманских смартфонов": `
                <p><strong>Тестируем автономность, качество ночной съемки и производительность процессоров.</strong></p>
                <p>Осенний сезон традиционно приносит волну премьер на рынке мобильных устройств. В этом обзоре мы собрали три главных флагмана текущего года, чтобы столкнуть их в честной битве за кошельки покупателей.</p>
                <h3>Производительность и троттлинг</h3>
                <p>Новые 3-нанометровые чипсеты показали впечатляющие результаты в синтетических тестах, однако в реальных играх с открытым миром нагрев корпуса у некоторых моделей достигает 45 градусов. Системы пассивного охлаждения в этом году претерпели изменения, но законы физики пока обходить удается не всем.</p>
                <h3>Камеры и ночной режим</h3>
                <ul>
                    <li>Модель А лидирует по детализации и естественной цветопередаче.</li>
                    <li>Модель Б предлагает лучший в классе стабилизированный зум до 10х.</li>
                    <li>Модель В выигрывает за счет быстрой обработки кадров с помощью встроенного нейрочипа.</li>
                </ul>
                <p>Итоговый вердикт: выбор зависит от ваших приоритетов. Если вам важна максимальная автономность — присмотритесь ко второму претенденту, а если вы мобильный фотограф — первый вариант вне конкуренции.</p>
            `,
            "Кибербезопасность в эпоху квантовых вычислений": `
                <p><strong>Как крупные корпорации перестраивают защиту конфиденциальных баз данных.</strong></p>
                <p>Стремительное развитие квантовых компьютеров ставит под угрозу существующие стандарты шифрования данных. Классические алгоритмы RSA и ECC, на которых держится современный интернет, могут быть взломаны с помощью алгоритма Шора на квантовых машинах достаточной мощности.</p>
                <h3>Постквантовая криптография</h3>
                <p>Институты стандартизации уже завершают утверждение новых алгоритмов, устойчивых к квантовому взлому. Банки, финтех-компании и государственные структуры начинают миграцию критической инфраструктуры на защищенные решетчатые коды.</p>
                <p>Процесс перехода займет от трех до пяти лет, и эксперты по безопасности призывают компании не откладывать аудит защищенности корпоративных сетей на последний момент.</p>
            `,
            "Анонс новой графической архитектуры для геймеров": `
                <p><strong>Трассировка лучей нового поколения и улучшенные алгоритмы масштабирования.</strong></p>
                <p>Ведущий производитель графических чипов анонсировал микроархитектуру следующего поколения. Главным фокусом презентации стало аппаратное ускорение трассировки лучей и внедрение интеллектуальных нейрофильтров текстур.</p>
                <h3>Что изменится для игроков?</h3>
                <p>Благодаря новым тензорным ядрам частота кадров в играх с максимальными настройками графики вырастет почти на 60% при сохранении нативной четкости изображения. Первые видеокарты на базе новой архитектуры поступят в продажу в ноябре.</p>
            `,
            "Инвестиции в зеленую энергетику выросли на 40%": `
                <p><strong>Какие технологические стартапы получили венчурное финансирование.</strong></p>
                <p>Рынок венчурного капитала демонстрирует рекордный интерес к проектам в сфере возобновляемой энергетики и умных энергосетей (Smart Grid). За последний квартал общий объем инвестиций преодолел отметку в несколько миллиардов долларов.</p>
                <p>Особое внимание фондов привлекают стартапы, разрабатывающие высокоэффективные перовскитные солнечные панели и компактные накопители энергии на основе альтернативных химических элементов.</p>
            `,
            "Вышел крупный релиз популярной IDE": `
                <p><strong>Встроенный локальный ИИ-ассистент и двукратное ускорение индексации кода.</strong></p>
                <p>Состоялся долгожданный релиз среды разработки, популярной среди инженеров по всему миру. Ключевым нововведением стала полностью автономная локальная языковая модель, работающая прямо на машине разработчика без отправки кода на внешние серверы.</p>
                <h3>Главные фичи релиза</h3>
                <ul>
                    <li>Индексация крупных монорепозиториев ускорилась в 2.1 раза.</li>
                    <li>Добавлен продвинутый инструмент рефакторинга с поддержкой многопоточного анализа.</li>
                    <li>Исправлено свыше 140 мелких багов, улучшена отзывчивость интерфейса.</li>
                </ul>
            `
        };

        // Переключение тем
        function toggleTheme() {
            const html = document.documentElement;
            const btn = document.getElementById('themeToggleBtn');
            if (html.getAttribute('data-theme') === 'light') {
                html.setAttribute('data-theme', 'dark');
                btn.textContent = '☀️';
            } else {
                html.setAttribute('data-theme', 'light');
                btn.textContent = '🌙';
            }
        }

        // Фильтрация новостей
        function filterCategory(category, element) {
            document.querySelectorAll('.tag-chip').forEach(chip => chip.classList.remove('active'));
            document.querySelectorAll('.nav-menu a').forEach(link => link.classList.remove('active'));
            if (element) element.classList.add('active');

            const cards = document.querySelectorAll('.news-card');
            cards.forEach(card => {
                const cardCategory = card.getAttribute('data-category');
                if (category === 'all' || cardCategory === category) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });

            document.getElementById('sectionHeading').textContent = 
                category === 'all' ? 'Лента публикаций' : `Категория: ${category}`;
        }

        // Поиск
        function searchNews() {
            const query = document.getElementById('searchInput').value.toLowerCase();
            const cards = document.querySelectorAll('.news-card');
            cards.forEach(card => {
                const title = card.querySelector('.card-title').textContent.toLowerCase();
                const desc = card.querySelector('.card-desc').textContent.toLowerCase();
                if (title.includes(query) || desc.includes(query)) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
        }

        // Открытие полной статьи из сетки
        function openArticle(card) {
            const img = card.querySelector('img').src;
            const category = card.querySelector('.badge-category').textContent;
            const title = card.querySelector('.card-title').textContent;
            const date = card.querySelector('.card-meta-info span:first-child').textContent;
            const time = card.querySelector('.card-meta-info span:last-child').textContent;

            document.getElementById('modalImg').src = img;
            document.getElementById('modalCategory').textContent = category;
            document.getElementById('modalTitle').textContent = title;
            document.getElementById('modalDate').textContent = date;
            document.getElementById('modalTime').textContent = time;
            
            // Загружаем полный текст статьи из словаря, либо выводим дефолтный текст
            const fullText = fullArticlesContent[title] || `
                <p><strong>Подробный материал от редакции TechPulse.</strong></p>
                <p>Современный технологический сектор демонстрирует невероятные темпы трансформации. Каждый день появляются новые инструменты, стандарты и подходы к проектированию систем.</p>
                <p>Мы продолжаем следить за развитием событий и готовим для вас глубокие аналитические материалы. Оставайтесь с нами и следите за обновлениями на портале.</p>
            `;
            document.getElementById('modalBody').innerHTML = fullText;

            document.getElementById('articleModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        // Открытие популярных статей из сайдбара
        function openTrendingArticle(title, category, img) {
            document.getElementById('modalImg').src = img;
            document.getElementById('modalCategory').textContent = category;
            document.getElementById('modalTitle').textContent = title;
            document.getElementById('modalDate').textContent = '📅 30 сентября 2026';
            document.getElementById('modalTime').textContent = '⏱ 5 мин чтения';
            
            document.getElementById('modalBody').innerHTML = `
                <p><strong>Полный разбор актуальной темы от редакции TechPulse.</strong></p>
                <p>В этом материале мы подробно рассмотрели главные тренды, собрали статистику и подготовили пошаговые рекомендации для практикующих специалистов.</p>
                <p>Разработка ведется силами группы ПО-245 с учетом актуальных стандартов веб-разработки и безопасности данных.</p>
            `;

            document.getElementById('articleModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        // Закрытие модального окна
        function closeArticle() {
            document.getElementById('articleModal').classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        function closeModalOnOutside(event) {
            if (event.target.id === 'articleModal') {
                closeArticle();
            }
        }

        // Лайки и шаринг
        function likeArticle(btn) {
            const countSpan = btn.querySelector('span');
            countSpan.textContent = parseInt(countSpan.textContent) + 1;
            btn.style.color = 'var(--accent-color)';
        }

        function shareArticle() {
            navigator.clipboard.writeText(window.location.href);
            alert('Ссылка на статью скопирована в буфер обмена!');
        }

        // Кнопка «Наверх»
        window.onscroll = function() {
            const scrollBtn = document.getElementById('scrollTopBtn');
            if (document.body.scrollTop > 300 || document.documentElement.scrollTop > 300) {
                scrollBtn.classList.add('visible');
            } else {
                scrollBtn.classList.remove('visible');
            }
        };

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html>
