```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Для тебя, моя лучшая подруга</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;700&family=Montserrat:wght@300;400&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background: linear-gradient(135deg, #fce4ec, #f8bbd0, #f48fb1);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            cursor: pointer;
            user-select: none;
        }

        /* Плавающие сердечки на фоне */
        .hearts {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
            z-index: 1;
        }

        .heart {
            position: absolute;
            font-size: 20px;
            color: rgba(255, 255, 255, 0.6);
            animation: floatUp 8s linear infinite;
            bottom: -50px;
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-110vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Контейнер страниц */
        .book {
            position: relative;
            width: 90%;
            max-width: 600px;
            height: 70vh;
            min-height: 450px;
            z-index: 2;
        }

        .page {
            position: absolute;
            inset: 0;
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            border-radius: 30px;
            box-shadow: 0 20px 50px rgba(214, 51, 108, 0.25);
            padding: 50px 40px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            opacity: 0;
            transform: scale(0.95) rotateY(-10deg);
            transition: opacity 0.8s ease, transform 0.8s ease;
            pointer-events: none;
            border: 1px solid rgba(255, 255, 255, 0.7);
        }

        .page.active {
            opacity: 1;
            transform: scale(1) rotateY(0deg);
            pointer-events: auto;
        }

        .page .emoji {
            font-size: 2.8rem;
            margin-bottom: 25px;
            animation: pulse 2.5s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.15); }
        }

        .page h2 {
            font-family: 'Caveat', cursive;
            font-size: 2rem;
            color: #d6336c;
            margin-bottom: 25px;
            line-height: 1.2;
        }

        .page p {
            font-size: 1.05rem;
            color: #5a3a45;
            line-height: 1.8;
            font-weight: 300;
            max-width: 450px;
        }

        .page .signature {
            margin-top: 30px;
            font-family: 'Caveat', cursive;
            font-size: 1.5rem;
            color: #d6336c;
        }

        .hint {
            position: fixed;
            bottom: 25px;
            left: 50%;
            transform: translateX(-50%);
            color: rgba(214, 51, 108, 0.7);
            font-size: 0.85rem;
            letter-spacing: 2px;
            text-transform: uppercase;
            z-index: 10;
            animation: hintPulse 2s ease-in-out infinite;
            font-weight: 400;
        }

        @keyframes hintPulse {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        /* Прогресс-точки */
        .dots {
            position: fixed;
            bottom: 60px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 10px;
            z-index: 10;
        }

        .dot {
            width: 8px;
            height: 8px;
            border-radius: 50%;
            background: rgba(214, 51, 108, 0.3);
            transition: all 0.4s ease;
        }

        .dot.active {
            background: #d6336c;
            transform: scale(1.3);
        }

        @media (max-width: 480px) {
            .page {
                padding: 35px 25px;
            }
            .page h2 {
                font-size: 1.6rem;
            }
            .page p {
                font-size: 0.95rem;
            }
            .page .emoji {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <div class="hearts" id="hearts"></div>

    <div class="book">
        <!-- Страница 1 -->
        <div class="page active">
            <div class="emoji">🌸</div>
            <h2>Моей лучшей подруге</h2>
            <p>Есть люди, которые приходят в жизнь и остаются в сердце навсегда. Ты — одна из них. Самая важная, самая родная, самая любимая.</p>
            <div class="signature">нажми, чтобы листать →</div>
        </div>

        <!-- Страница 2 -->
        <div class="page">
            <div class="emoji">☕</div>
            <h2>Помнишь?</h2>
            <p>Наши ночные разговоры, слёзы и смех вперемешку, глупые шутки, которые понимаем только мы. Всё это — моё самое большое богатство. Спасибо, что ты есть.</p>
            <div class="signature">нажми, чтобы листать →</div>
        </div>

        <!-- Страница 3 -->
        <div class="page">
            <div class="emoji">🌧️</div>
            <h2>Если тебе грустно</h2>
            <p>Если ты плачешь — я рядом. Не будет слов «всё пройдёт», я просто обниму тебя и буду держать за руку. Потому что твоя боль — это и моя боль тоже.</p>
            <div class="signature">нажми, чтобы листать →</div>
        </div>

        <!-- Страница 4 -->
        <div class="page">
            <div class="emoji">🕯️</div>
            <h2>Спасибо тебе</h2>
            <p>Спасибо за то, что видишь во мне хорошее, когда я сама в это не верю. За то, что остаёшься, когда я бываю невыносимой. За то, что ты — мой человек.</p>
            <div class="signature">нажми, чтобы листать →</div>
        </div>

        <!-- Страница 5 -->
        <div class="page">
            <div class="emoji">💔</div>
            <h2>Прости меня</h2>
            <p>Прости за резкие слова, за моменты, когда я была занята собой. Ты заслуживаешь всего самого лучшего, и я обещаю быть достойной тебя. Ты — мой дом.</p>
            <div class="signature">нажми, чтобы листать →</div>
        </div>

        <!-- Страница 6 -->
        <div class="page">
            <div class="emoji">🌻</div>
            <h2>Даже если...</h2>
            <p>Даже если мы будем далеко, даже если жизнь нас потреплет, знай: ты всегда в моём сердце. Навсегда. Это не просто слова. Это клятва.</p>
            <div class="signature">нажми, чтобы листать →</div>
        </div>

        <!-- Страница 7 -->
        <div class="page">
            <div class="emoji">💕</div>
            <h2>Я тебя люблю</h2>
            <p>Не как-то по-особенному, а просто всей душой. Ты — моя сестра по сердцу. Спасибо, что выбрала меня. Спасибо, что ты моя лучшая подруга.</p>
            <div class="signature">← нажми, чтобы начать заново</div>
        </div>
    </div>

    <div class="dots" id="dots"></div>
    <div class="hint">нажми на экран</div>

    <script>
        const pages = document.querySelectorAll('.page');
        const dotsContainer = document.getElementById('dots');
        let currentPage = 0;
        const totalPages = pages.length;

        // Создание точек прогресса
        for (let i = 0; i < totalPages; i++) {
            const dot = document.createElement('div');
            dot.classList.add('dot');
            if (i === 0) dot.classList.add('active');
            dotsContainer.appendChild(dot);
        }
        const dots = document.querySelectorAll('.dot');

        // Фоновые сердечки
        function createHeart() {
            const heartsContainer = document.getElementById('hearts');
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = ['💗', '🌸', '💕', '✨', '🌷', '💖'][Math.floor(Math.random() * 6)];
            heart.style.left = Math.random() * 100 + '%';
            heart.style.fontSize = (Math.random() * 20 + 15) + 'px';
            heart.style.animationDuration = (Math.random() * 4 + 6) + 's';
            heart.style.animationDelay = Math.random() * 2 + 's';
            heartsContainer.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 10000);
        }

        setInterval(createHeart, 800);
        // Первые сердечки сразу
        for (let i = 0; i < 5; i++) {
            setTimeout(createHeart, i * 300);
        }

        // Смена страниц
        function nextPage() {
            pages[currentPage].classList.remove('active');
            dots[currentPage].classList.remove('active');
            
            currentPage = (currentPage + 1) % totalPages;
            
            pages[currentPage].classList.add('active');
            dots[currentPage].classList.add('active');
        }

        // Обработчик клика по всему документу
        document.addEventListener('click', nextPage);

        // Поддержка свайпа на мобильных
        let touchStartX = 0;
        let touchEndX = 0;

        document.addEventListener('touchstart', (e) => {
            touchStartX = e.changedTouches[0].screenX;
        }, { passive: true });

        document.addEventListener('touchend', (e) => {
            touchEndX = e.changedTouches[0].screenX;
            // Свайп не обязателен, но клик всё равно сработает
        }, { passive: true });
    </script>
</body>
</html>
```