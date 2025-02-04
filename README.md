
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>العد التنازلي لرمضان 🌙</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background: linear-gradient(-45deg, #2c3e50, #3498db, #e74c3c, #9b59b6);
            background-size: 400% 400%;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Arial', sans-serif;
            color: white;
            animation: gradientBG 15s ease infinite;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            text-align: center;
            background: rgba(0, 0, 0, 0.7);
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.7);
            position: relative;
            backdrop-filter: blur(10px);
        }

        h1 {
            font-size: 2.5em;
            margin-bottom: 1.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            animation: titleFloat 3s ease-in-out infinite;
        }

        @keyframes titleFloat {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .countdown {
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        .box {
            background: rgba(255, 255, 255, 0.1);
            padding: 1.5rem;
            border-radius: 10px;
            min-width: 120px;
            position: relative;
            overflow: hidden;
            transition: transform 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.2);
        }

        .box:hover {
            transform: scale(1.1) rotate(3deg);
            background: rgba(255, 255, 255, 0.15);
        }

        .box::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: rotate(45deg) translateX(-200%); }
            100% { transform: rotate(45deg) translateX(200%); }
        }

        .number {
            font-size: 3em;
            font-weight: bold;
            display: block;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
            animation: pulse 1s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        .label {
            font-size: 1.2em;
            color: #ecf0f1;
            text-transform: uppercase;
        }

        .moon {
            position: fixed;
            top: 20px;
            left: 20px;
            width: 80px;
            height: 80px;
            background: #f1c40f;
            border-radius: 50%;
            box-shadow: 0 0 50px rgba(241, 196, 15, 0.5);
            animation: float 4s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        .firework {
            position: absolute;
            width: 10px;
            height: 10px;
            background: #fff;
            border-radius: 50%;
            animation: explode 1.5s infinite;
        }

        @keyframes explode {
            0% { transform: scale(0); opacity: 1; }
            100% { transform: scale(10); opacity: 0; }
        }
    </style>
</head>
<body>
    <div class="moon"></div>
    
    <div class="container">
        <h1>العد التنازلي لرمضان المبارك 🌙✨</h1>
        <div class="countdown">
            <div class="box">
                <span class="number" id="days">0</span>
                <span class="label">أيام</span>
            </div>
            <div class="box">
                <span class="number" id="hours">0</span>
                <span class="label">ساعات</span>
            </div>
            <div class="box">
                <span class="number" id="minutes">0</span>
                <span class="label">دقائق</span>
            </div>
            <div class="box">
                <span class="number" id="seconds">0</span>
                <span class="label">ثواني</span>
            </div>
        </div>
    </div>

    <script>
        function updateCountdown() {
            const ramadanDate = new Date('2025-03-01T00:00:00');
            const now = new Date();
            const diff = ramadanDate - now;

            const days = Math.floor(diff / (1000 * 60 * 60 * 24));
            const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((diff % (1000 * 60)) / 1000);

            document.getElementById('days').textContent = days;
            document.getElementById('hours').textContent = hours;
            document.getElementById('minutes').textContent = minutes;
            document.getElementById('seconds').textContent = seconds;

            // Add pulse animation
            document.querySelectorAll('.number').forEach(el => {
                el.style.animation = 'none';
                void el.offsetHeight; // Trigger reflow
                el.style.animation = 'pulse 0.5s ease-in-out';
            });

            createFirework();
        }

        function createFirework() {
            const firework = document.createElement('div');
            firework.className = 'firework';
            firework.style.left = `${Math.random() * 100}%`;
            firework.style.top = `${Math.random() * 100}%`;
            document.body.appendChild(firework);
            
            setTimeout(() => firework.remove(), 1500);
        }

        // تحديث العداد كل ثانية
        setInterval(updateCountdown, 1000);
        updateCountdown(); // التحديث الأولي
    </script>
</body>
</html>
