# Happy-birthday-Malik
عيد ميلاد مالك
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- اسم الموقع اللي هيظهر في التاب -->
    <title>Happy birthday, Malek 🎂🧸</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&family=Fredoka+One&display=swap" rel="stylesheet">
    <!-- مكتبة القصاصات الملونة -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Cairo', sans-serif;
        }

        body {
            background: linear-gradient(135deg, #ffe6e6 0%, #e6f2ff 100%);
            color: #333;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        /* دباديب وقلوب متحركة في الخلفية */
        .floating-emoji {
            position: absolute;
            font-size: 30px;
            opacity: 0.6;
            animation: floatUp 10s linear infinite;
            z-index: 0;
        }

        @keyframes floatUp {
            0% { transform: translateY(100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.6; }
            90% { opacity: 0.6; }
            100% { transform: translateY(-10vh) rotate(360deg); opacity: 0; }
        }

        /* شاشة البداية (الهدية) */
        .gift-screen {
            text-align: center;
            z-index: 10;
            transition: all 0.8s ease;
            background: rgba(255, 255, 255, 0.8);
            padding: 40px;
            border-radius: 30px;
            box-shadow: 0 10px 30px rgba(255, 182, 193, 0.4);
            border: 2px dashed #ffb6c1;
        }

        .gift-box {
            font-size: 120px;
            cursor: pointer;
            animation: bounce 1.5s infinite;
            filter: drop-shadow(0 10px 10px rgba(0,0,0,0.1));
            transition: transform 0.3s;
        }

        .gift-box:hover {
            transform: scale(1.1);
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .gift-text {
            margin-top: 20px;
            font-size: 22px;
            font-weight: 700;
            color: #ff69b4;
        }

        /* الكارت الرئيسي (المفاجأة) */
        .card-container {
            position: absolute;
            z-index: 5;
            opacity: 0;
            transform: scale(0.5);
            transition: all 1s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            pointer-events: none;
            width: 90%;
            max-width: 420px;
        }

        .card-container.show {
            opacity: 1;
            transform: scale(1);
            pointer-events: auto;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.9);
            backdrop-filter: blur(15px);
            -webkit-backdrop-filter: blur(15px);
            border: 3px solid #fff;
            border-radius: 30px;
            padding: 40px 30px;
            text-align: center;
            box-shadow: 0 15px 40px rgba(255, 105, 180, 0.3);
            position: relative;
            overflow: hidden;
        }

        .bear-img {
            font-size: 100px;
            margin-bottom: 15px;
            animation: wiggle 2s infinite;
            display: inline-block;
        }

        @keyframes wiggle {
            0%, 100% { transform: rotate(-5deg); }
            50% { transform: rotate(5deg); }
        }

        .friend-name {
            font-family: 'Fredoka One', cursive;
            font-size: 40px;
            color: #ff69b4;
            margin-bottom: 10px;
            text-shadow: 2px 2px 0px #ffe6e6;
            line-height: 1.2;
            direction: ltr;
        }

        .bday-title {
            font-size: 22px;
            font-weight: 900;
            color: #8a2be2;
            margin-bottom: 20px;
        }

        .message {
            font-size: 17px;
            line-height: 1.8;
            color: #555;
            margin-bottom: 25px;
            font-weight: 700;
            background: #fff0f5;
            padding: 20px;
            border-radius: 20px;
            border: 1px solid #ffb6c1;
        }

        .hearts {
            font-size: 24px;
            letter-spacing: 5px;
        }

    </style>
</head>
<body>

    <!-- دباديب وقلوب متحركة في الخلفية -->
    <div class="floating-emoji" style="left: 10%; animation-delay: 0s;">🧸</div>
    <div class="floating-emoji" style="left: 30%; animation-delay: 2s;">❤️</div>
    <div class="floating-emoji" style="left: 50%; animation-delay: 4s;">🎈</div>
    <div class="floating-emoji" style="left: 70%; animation-delay: 1s;">🧸</div>
    <div class="floating-emoji" style="left: 85%; animation-delay: 3s;">🎁</div>
    <div class="floating-emoji" style="left: 15%; animation-delay: 5s;">🧸</div>
    <div class="floating-emoji" style="left: 60%; animation-delay: 6s;">💖</div>

    <!-- شاشة الهدية -->
    <div class="gift-screen" id="giftScreen">
        <div class="gift-box" onclick="openGift()">🧸🎁</div>
        <div class="gift-text">دوس على الدبدوب لفتح المفاجأة 👆</div>
    </div>

    <!-- كارت المفاجأة -->
    <div class="card-container" id="cardContainer">
        <div class="glass-card">
            
            <div class="bear-img">🧸</div>
            
            <!-- اسم صاحبك -->
            <div class="friend-name">Malek</div>
            
            <div class="bday-title">كل سنة وأنت طيب يا مالك! 🎂</div>
            
            <div class="message">
                أنا الدبدوب الكيوت بتاعك 🧸..<br>
                بعتلك الهدية دي عشان أقولك إنك أغلى حد عندي، وأتمنى لك سنة سعيدة ومليانة ضحك وحب. ❤️<br>
                <b>عقبال 100 سنة يا رب! 🎈</b>
            </div>
            
            <div class="hearts">💖🧸🎈🎁💖</div>
        </div>
    </div>

    <script>
        function openGift() {
            // اخفاء شاشة الهدية
            const giftScreen = document.getElementById('giftScreen');
            giftScreen.style.opacity = '0';
            giftScreen.style.transform = 'scale(1.5)';
            
            setTimeout(() => {
                giftScreen.style.display = 'none';
            }, 800);

            // اظهار الكارت
            const card = document.getElementById('cardContainer');
            card.classList.add('show');

            // تشغيل القصاصات الملونة بألوان كيوت
            playConfetti();
        }

        function playConfetti() {
            var duration = 4 * 1000;
            var animationEnd = Date.now() + duration;
            // ألوان باستيل (بينك، لبني، أصفر، موف)
            var colors = ['#ffb3ba', '#ffdfba', '#ffffba', '#baffc9', '#bae1ff', '#e0baff'];

            var interval = setInterval(function() {
                var timeLeft = animationEnd - Date.now();

                if (timeLeft <= 0) {
                    return clearInterval(interval);
                }

                var particleCount = 40 * (timeLeft / duration);
                // ضرب القصاصات من النص
                confetti({
                    particleCount: particleCount,
                    spread: 360,
                    origin: { y: 0.6 },
                    colors: colors,
                    ticks: 200
                });
            }, 250);
        }
    </script>
</body>
</html>
