<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Iron Men Moving - Профессиональный переезд</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Базовые стили */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Roboto', sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f5f5f5;
        }
        
        /* Шапка */
        .header {
            background: #2c3e50;
            color: white;
            padding: 20px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .logo { font-size: 24px; font-weight: 700; color: #ff6b35; }
        .nav-links { list-style: none; display: flex; gap: 20px; }
        .nav-links a { color: white; text-decoration: none; }
        .cta-button {
            background: #ff6b35;
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
        }

        /* Секция Герой */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)),
                        url('https://images.unsplash.com/photo-1542744095-291d1f63b44d?ixid=M3wzNjM5Nzd8MHwxfHNlYXJjaHwxfHxpbnN1cmFuY2UlMjBzdGlja3xlbnwwfHx8fDE3MTc5NjQxNjF8MA&ixlib=rb-4.0.3&w=1920') no-repeat center;
            background-size: cover;
            height: 60vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
        }
        .hero h1 { font-size: 48px; margin-bottom: 20px; }
        .hero p { font-size: 24px; margin-bottom: 30px; }

        /* Услуги */
        .services {
            padding: 50px 20px;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .service-card {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .service-card h3 { color: #ff6b35; margin-bottom: 15px; }

        /* Калькулятор */
        .calculator {
            background: #2c3e50;
            color: white;
            padding: 40px 20px;
        }
        .calc-form { max-width: 600px; margin: 0 auto; }
        .calc-form input, .calc-form select {
            width: 100%;
            padding: 10px;
            margin: 15px 0;
            border: none;
            border-radius: 5px;
        }
        .calc-result { font-size: 24px; text-align: center; }

        /* Отзывы */
        .reviews {
            padding: 50px 20px;
            background: #f5f5f5;
        }
        .review-slider {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }
        .review-card {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }
        .review-card blockquote { font-style: italic; }

        /* Футер */
        .footer {
            background: #2c3e50;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .footer a { color: #ff6b35; margin: 0 10px; }

        /* Адаптивность */
        @media (max-width: 768px) {
            .header { flex-direction: column; text-align: center; gap: 15px; }
            .hero h1 { font-size: 36px; }
            .hero p { font-size: 18px; }
        }
    </style>
</head>
<body>
    <!-- Шапка -->
    <header class="header">
        <div class="logo">Iron Men Moving</div>
        <nav>
            <ul class="nav-links">
                <li><a href="#">Услуги</a></li>
                <li><a href="#">Цены</a></li>
                <li><a href="#">Отзывы</a></li>
                <li><a href="#">Контакты</a></li>
            </ul>
        </nav>
        <a href="#" class="cta-button">Бесплатная оценка</a>
    </header>

    <!-- Секция Герой -->
    <section class="hero">
        <h1>Переезд без стресса</h1>
        <p>Профессиональные грузчики и транспорт в вашем городе</p>
        <a href="#" class="cta-button">Рассчитать стоимость →</a>
    </section>

    <!-- Услуги -->
    <section class="services">
        <div class="service-card">
            <h3>Переезды</h3>
            <p>Квартирные, офисные и дачные переезды любой сложности</p>
        </div>
        <div class="service-card">
            <h3>Упаковка</h3>
            <p>Профессиональная упаковка вещей и мебели</p>
        </div>
        <div class="service-card">
            <h3>Хранение</h3>
            <p>Безопасное хранение вещей до 6 месяцев</p>
        </div>
    </section>

    <!-- Калькулятор -->
    <section class="calculator">
        <div class="calc-form">
            <h2>Рассчитайте стоимость</h2>
            <input type="range" min="1" max="100" value="50" id="distance">
            <p>Расстояние: <span id="distance-value">50 км</span></p>
            
            <select id="items">
                <option value="10">1-10 вещей</option>
                <option value="20">11-20 вещей</option>
                <option value="30">21-30 вещей</option>
            </select>
            
            <button onclick="calculate()">Рассчитать</button>
            <div class="calc-result">Итого: <strong id="total">$0</strong></div>
        </div>
    </section>

    <!-- Отзывы -->
    <section class="reviews">
        <div class="review-slider">
            <div class="review-card">
                <blockquote>"Быстро, аккуратно и недорого! Спасибо команде за помощь с переездом!"</blockquote>
                <p>- Иван Петров</p>
            </div>
            <div class="review-card">
                <blockquote>"Профессионалы своего дела! Упаковали всё за 2 часа"</blockquote>
                <p>- Анна Сидорова</p>
            </div>
        </div>
    </section>

    <!-- Футер -->
    <footer class="footer">
        <p>© 2024 Iron Men Moving | 
            <a href="#">Политика конфиденциальности</a> | 
            <a href="#">+123-456-7890</a>
        </p>
    </footer>

    <script>
        // Калькулятор
        const distance = document.getElementById('distance');
        const distanceValue = document.getElementById('distance-value');
        
        distance.addEventListener('input', () => {
            distanceValue.textContent = `${distance.value} км`;
        });

        function calculate() {
            const km = parseInt(distance.value);
            const items = parseInt(document.getElementById('items').value);
            const total = km * 2 + items * 5;
            document.getElementById('total').textContent = `$${total}`;
        }
    </script>
</body>
</html>
