<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>sadece ömrüme özell ehehe🤍💋</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Dancing+Script:wght@700&display=swap');

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            height: 100vh;
            overflow: hidden;
            font-family: 'Playfair Display', serif;
            color: white;
            background: linear-gradient(135deg, #2a0033, #4b0082, #8a2be2, #ff69b4);
            background-size: 400% 400%;
            animation: gradientShift 18s ease infinite;
            position: relative;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .hearts { position: fixed; top: 0; left: 0; width: 100%; height: 100%; pointer-events: none; z-index: 1; }
        .heart {
            position: absolute; font-size: 30px; color: #ff1493;
            text-shadow: 0 0 20px #ff69b4, 0 0 40px #ff00ff;
            animation: heartFall linear infinite; opacity: 0.85;
        }
        @keyframes heartFall {
            0% { transform: translateY(-100vh) rotate(0deg); opacity: 1; }
            100% { transform: translateY(130vh) rotate(720deg); opacity: 0; }
        }

        .login-container {
            position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);
            background: rgba(20, 0, 40, 0.9); padding: 55px 45px; border-radius: 28px;
            box-shadow: 0 0 70px rgba(255, 105, 180, 0.8); text-align: center;
            z-index: 20; border: 3px solid rgba(255, 20, 147, 0.5); max-width: 390px; width: 92%;
        }
        .login-container h1 {
            font-family: 'Dancing Script', cursive; font-size: 46px;
            background: linear-gradient(to right, #ff69b4, #da70d6, #ff1493);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        input, button { width: 100%; padding: 16px; margin: 15px 0; border: none; border-radius: 14px; }
        input { background: rgba(255,255,255,0.13); color: white; font-size: 17px; text-align: center; }
        button { background: linear-gradient(to right, #ff1493, #8a2be2); color: white; font-size: 19px; font-weight: bold; cursor: pointer; }
        button:hover { transform: scale(1.06); box-shadow: 0 0 30px #ff69b4; }
        .error { color: #ff6b6b; margin-top: 12px; font-size: 15px; }

        .main-content { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: 10; padding: 30px 25px; overflow-y: auto; }
        .main-content.show { display: block; }

        .header { text-align: center; margin-bottom: 40px; }
        .header h1 { font-family: 'Dancing Script', cursive; font-size: 54px; color: #ff69b4; text-shadow: 0 0 20px rgba(255,105,180,0.6); }

        .counter {
            background: rgba(255,255,255,0.09); padding: 35px; border-radius: 24px;
            margin: 30px auto; max-width: 620px; text-align: center;
            box-shadow: 0 0 50px rgba(255, 105, 180, 0.5);
        }
        .counter h2 { font-size: 29px; margin-bottom: 16px; }
        .time { font-size: 35px; font-weight: bold; color: #ff69b4; letter-spacing: 2px; }

        .music-player {
            margin: 40px auto; max-width: 540px; 
            background: linear-gradient(145deg, rgba(255,255,255,0.12), rgba(255,105,180,0.08));
            padding: 38px 30px; border-radius: 28px; 
            box-shadow: 0 0 60px rgba(255, 20, 147, 0.5);
            text-align: center;
        }
        .music-player h3 {
            font-family: 'Dancing Script', cursive; font-size: 36px; color: #ff69b4; margin-bottom: 8px;
        }
        .music-player .artist { font-size: 19px; opacity: 0.9; margin-bottom: 25px; }
        .lyrics {
            background: rgba(0,0,0,0.35); padding: 25px; border-radius: 18px; 
            margin: 25px 0; font-size: 18px; line-height: 1.8; color: #ffe4f0;
        }

        .surprise-box {
            margin: 50px auto; max-width: 420px; text-align: center;
        }
        .surprise-btn {
            background: linear-gradient(45deg, #ff1493, #c71585);
            color: white; padding: 19px 45px; border: none; border-radius: 50px;
            font-size: 21px; font-weight: bold; cursor: pointer;
            box-shadow: 0 0 45px rgba(255, 20, 147, 0.75);
            transition: all 0.4s;
        }
        .surprise-btn:hover {
            transform: scale(1.1) rotate(4deg);
            box-shadow: 0 0 70px rgba(255, 20, 147, 0.95);
        }
        .surprise-content {
            display: none; margin-top: 25px; padding: 28px; background: rgba(255,255,255,0.1);
            border-radius: 22px; font-size: 18.5px; line-height: 1.85;
            box-shadow: 0 0 35px rgba(255,105,180,0.5);
        }
        .surprise-content.show { display: block; animation: surprisePop 0.6s ease; }
        @keyframes surprisePop {
            0% { transform: scale(0.5); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
    </style>
</head>
<body>

    <div class="hearts" id="hearts"></div>

    <div class="login-container" id="loginScreen">
        <h1>🤍 Bizim Dünyamız 🤍</h1>
        <p>Şifreyi tahmin et bakalımm 💋</p>
        <input type="password" id="password" placeholder="örnek: ilk olduğumuz gün">
        <button onclick="checkPassword()">Giriş Yap</button>
        <div class="error" id="error"></div>
    </div>

    <div class="main-content" id="mainContent">
        <div class="header">
            <h1>Hoş geldin gönlümün sultanı 🫠🤍</h1>
            <p>Sadece ikimize özel gizli dünyamız</p>
        </div>

        <div class="counter">
            <h2>16 Nisan 2026'dan beri birlikteyiz 💕</h2>
            <div class="time" id="loveCounter">0 gün 0 saat 0 dakika 0 saniye</div>
        </div>

        <div class="music-player">
            <h3>🎵 Sözüm Şiirlerin Mükemmeldir 🎵</h3>
            <div class="artist">Mustafa Kaya • Sabahattin Ali</div>
            <div class="lyrics">
                Sözün şiirlerin mükemmeldir<br>
                Senden başkasını seven delidir<br><br>
                Yüzün çiçeklerin en güzelidir<br>
                Gözlerin bilinmez bir diyar gibi<br><br>
                Başını göğsüme sakla sevgilim...
            </div>
            <iframe src="https://www.youtube.com/embed/3lcUIPU9kqQ?autoplay=1&loop=1&playlist=3lcUIPU9kqQ&modestbranding=1" 
                    frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
        </div>

        <div class="surprise-box">
            <button class="surprise-btn" onclick="openSurprise()">😚 Sürprizimi Aç ömrüm💋</button>
            <div class="surprise-content" id="surpriseContent">
                Gönlümün sultanı ben seni çoooooookkk seviyommmm sen benim biricik hayatımın aşkı biricik eşimsinn (ama daha evlenmedik işte) 🥹<br><br>
                Özür dilerimmm ömrümmmm Allah belamı versin Allah'ım kafamı Kıraydı da seni kırmayayım özür dilerimm 🥹 iyiki varsınnn demek isterdim ama sen bana iyiki yarsın sevdiğimm 🫠🤍<br>
               Sen benim hayatımın aşkı gelecekteki çocuklarımın annesi olacaksın 🫠🤍<br><br>
                Sonsuza kadar seninle... 💕
            </div>
        </div>

        <div style="text-align:center; margin-top:60px; font-size:19px; opacity:0.92;">
           Sadece karımaa özelll 💋💋
        </div>
    </div>

    <script>
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.textContent = ['❤️','💖','💗','💓','💞'][Math.floor(Math.random()*5)];
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 9 + 8) + 's';
            heart.style.fontSize = (Math.random() * 24 + 26) + 'px';
            document.getElementById('hearts').appendChild(heart);
            setTimeout(() => heart.remove(), 22000);
        }
        setInterval(createHeart, 160);
        for (let i = 0; i < 15; i++) setTimeout(createHeart, i * 110);

        function checkPassword() {
            const pass = document.getElementById('password').value.trim();
            const error = document.getElementById('error');
            error.textContent = '';

            if (!pass) { error.textContent = "Lütfen şifreyi gir!"; return; }

            if (pass === "14.04.2026") {
                document.getElementById('loginScreen').style.display = 'none';
                document.getElementById('mainContent').classList.add('show');
                startLoveCounter();
            } else {
                error.textContent = "Yanlış şifre tekrar dene ömrümmm🫠";
            }
        }

        document.getElementById('password').addEventListener('keypress', e => {
            if (e.key === 'Enter') checkPassword();
        });

        const startDate = new Date(2026, 3, 16);
        function startLoveCounter() {
            setInterval(() => {
                const now = new Date();
                let diff = Math.floor((now - startDate) / 1000);
                const days = Math.floor(diff / (3600 * 24));
                diff %= 3600 * 24;
                const hours = Math.floor(diff / 3600);
                diff %= 3600;
                const minutes = Math.floor(diff / 60);
                const seconds = diff % 60;

                document.getElementById('loveCounter').textContent = 
                    `${days} gün ${hours} saat ${minutes} dakika ${seconds} saniye`;
            }, 1000);
        }

        function openSurprise() {
            const content = document.getElementById('surpriseContent');
            content.classList.toggle('show');
            for (let i = 0; i < 12; i++) setTimeout(createHeart, i * 60);
        }
    </script>
</body>
</html>
