<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Iron Men Moving - Вывоз пианино</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #c41330;
            --secondary: #1a1a1a;
            --accent: #ffd700;
            --light: #f5f5f5;
            --dark: #2c2c2c;
        }

        body {
            font-family: 'Roboto', sans-serif;
            background: var(--secondary);
            color: var(--light);
            margin: 0;
            padding: 0;
        }

        /* Кнопка быстрой связи */
        .quick-contact {
            position: fixed;
            right: 30px;
            bottom: 30px;
            background: var(--primary);
            color: white;
            padding: 15px 25px;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
            transition: all 0.3s;
            z-index: 1000;
        }

        .quick-contact:hover {
            transform: rotate(-5deg) scale(1.1);
            box-shadow: 0 10px 20px rgba(0,0,0,0.4);
        }

        /* Секция Герой */
        .hero {
            background: url('https://images.unsplash.com/photo-1554224155-68c07d6d54e0?ixid=M3wzNjM5Nzd8MHwxfHNlYXJjaHwxfHxpbnN1cmFuY2UlMjBzdGlja3xlbnwwfHx8fDE3MTc5NjQxNjF8MA&ixlib=rb-4.0.3&w=1920') no-repeat center;
            background-size: cover;
            height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
        }

        .hero-content {
            padding: 20px;
            background: rgba(0,0,0,0.7);
            border-radius: 15px;
            margin-left: 50px;
        }

        .hero h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 48px;
            color: var(--accent);
            text-shadow: 2px 2px 5px rgba(0,0,0,0.5);
        }

        /* Иконки услуг */
        .service-icon {
            width: 64px;
            height: 64px;
            background: var(--primary);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 20px;
            transition: all 0.3s;
        }

        .service-icon:hover {
            transform: rotate(15deg);
            background: var(--accent);
        }

        /* Калькулятор */
        .calculator {
            background: var(--dark);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 0 20px rgba(0,0,0,0.5);
        }

        .calc-display {
            background: var(--primary);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        /* Модальное окно */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
        }

        .modal-content {
            background: var(--secondary);
            margin: 15% auto;
            padding: 20px;
            width: 80%;
            border-radius: 15px;
        }

        /* Анимации */
        @keyframes glow {
            0% { text-shadow: 0 0 5px var(--accent); }
            50% { text-shadow: 0 0 20px var(--accent); }
            100% { text-shadow: 0 0 5px var(--accent); }
        }

        .glow-text {
            animation: glow 2s infinite;
        }
    </style>
</head>
<body>
    <!-- Кнопка быстрой связи -->
    <div class="quick-contact" onclick="openModal()">
        📞 Быстрая связь
    </div>

    <!-- Модальное окно -->
    <div id="contactModal" class="modal">
        <div class="modal-content">
            <span onclick="closeModal()" style="float: right; cursor: pointer;">&times;</span>
            <h2>Оставьте заявку</h2>
            <input type="text" placeholder="Ваше имя" class="modal-input">
            <input type="tel" placeholder="Телефон" class="modal-input">
            <button class="button">Отправить</button>
        </div>
    </div>

    <!-- Основной контент -->
    <section class="hero">
        <div class="hero-content">
            <h1 class="glow-text">Вывоз пианино<br>с технологией Iron Man</h1>
            <p style="font-size: 24px; margin: 20px 0;">Профессионально. Аккуратно. С гарантией.</p>
            <button class="button" onclick="scrollToCalculator()">Рассчитать стоимость</button>
        </div>
    </section>

    <section class="services">
        <div class="service-card">
            <div class="service-icon">.PIANO</div>
            <h3>Пианино/Рояль</h3>
            <p>Специальное оборудование для транспортировки</p>
        </div>
        <div class="service-card">
            <div class="service-icon">🚚</div>
            <h3>Грузчики</h3>
            <p>Команда профессионалов с опытом</p>
        </div>
        <div class="service-card">
            <div class="service-icon">🛡️</div>
            <h3>Страховка</h3>
            <p>Полная защита вашего инструмента</p>
        </div>
    </section>

    <section class="calculator">
        <h2>Калькулятор стоимости</h2>
        <div class="calc-display">
            <div>Расстояние: <span id="distanceVal">50 км</span></div>
            <div>Этаж: <span id="floorVal">1</span></div>
            <div>Тип инструмента: <span id="typeVal">Пианино</span></div>
            <div class="total">Итого: <strong id="totalVal">$0</strong></div>
        </div>
        <div class="calc-controls">
            <input type="range" min="1" max="100" value="50" oninput="updateCalc()">
            <select onchange="updateCalc()">
                <option>Пианино</option>
                <option>Рояль</option>
                <option>Синтезатор</option>
            </select>
        </div>
    </section>

    <script>
        function openModal() {
            document.getElementById('contactModal').style.display = 'block';
        }

        function closeModal() {
            document.getElementById('contactModal').style.display = 'none';
        }

        function updateCalc() {
            // Логика расчета стоимости
        }

        function scrollToCalculator() {
            document.querySelector('.calculator').scrollIntoView({ 
                behavior: 'smooth' 
            });
        }
    </script>
</body>
</html>
