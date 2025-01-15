<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Шоу-матч по CS2: Кишки vs Чмогатыри</title>
    <style>
        /* Основные стили */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #0d1117;
            color: #ffffff;
            margin: 0;
            padding: 0;
            text-align: center;
        }

        header {
            background-color: #161b22;
            padding: 20px;
            border-bottom: 2px solid #ff5722;
        }

        h1 {
            margin: 0;
            font-size: 2.5em;
            color: #ff5722;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .container {
            padding: 20px;
        }

        /* Стили для блоков команд */
        .teams {
            display: flex;
            justify-content: space-around;
            margin: 40px 0;
        }

        .team {
            background-color: #161b22;
            padding: 20px;
            border-radius: 10px;
            width: 40%;
            border: 1px solid #ff5722;
        }

        .team img {
            width: 100px;
            height: 100px;
            margin-bottom: 10px;
        }

        .team h2 {
            color: #ff5722;
            margin: 10px 0;
        }

        .team p {
            color: #c9d1d9;
        }

        /* Таймер обратного отсчета */
        .countdown {
            font-size: 2em;
            margin: 40px 0;
            color: #ff5722;
            font-weight: bold;
        }

        /* Голосование за карту */
        .voting {
            background-color: #161b22;
            padding: 20px;
            border-radius: 10px;
            margin: 40px auto;
            width: 60%;
            border: 1px solid #ff5722;
        }

        .voting h2 {
            color: #ff5722;
            margin-bottom: 20px;
        }

        .voting label {
            display: block;
            margin: 10px 0;
            color: #c9d1d9;
        }

        .voting input[type="radio"] {
            margin-right: 10px;
        }

        .voting button {
            background-color: #ff5722;
            color: #ffffff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
            margin-top: 20px;
        }

        .voting button:hover {
            background-color: #e64a19;
        }

        /* Футер */
        footer {
            background-color: #161b22;
            padding: 10px;
            position: fixed;
            bottom: 0;
            width: 100%;
            border-top: 1px solid #ff5722;
        }

        footer p {
            margin: 0;
            color: #c9d1d9;
        }

        footer a {
            color: #ff5722;
            text-decoration: none;
        }

        footer a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <header>
        <h1>Шоу-матч по ПЖ ЗАРЕГАЙ 2: Кишки vs 4м0гатыри </h1>
    </header>
    <div class="container">
        <!-- Таймер обратного отсчета -->
        <div class="countdown" id="countdown">До начала матча: 03:05:00</div>

        <!-- Блоки команд -->
        <div class="teams">
            <div class="team">
                <img src="img/2.png" alt="Логотип Команды 1">
                <h2>Кишки</h2>
                <p>Состав: Сасалыч, Хуёк, Антонио, Шишак, Что за лев этот тигр</p>
            </div>
            <div class="team">
                <img src="img/1.png" alt="Логотип Команды 2">
                <h2>4м0гатыри</h2>
                <p>Состав: Максим, Жирная тварь, Тимур джан, Горшок, 1 мегафон вам или 2 другому</p>
            </div>
        </div>

        <!-- Голосование за карту -->
        <div class="voting">
            <h2>Голосование за карту</h2>
            <p>Выберите карту, на которой сыграют команды:</p>
            <form>
                <label for="dust2"><input type="radio" id="dust2" name="map" value="Dust II"> Dust II</label>
                <label for="mirage"><input type="radio" id="mirage" name="map" value="Mirage"> Mirage</label>
                <label for="inferno"><input type="radio" id="inferno" name="map" value="Inferno"> Inferno</label>
                <label for="nuke"><input type="radio" id="nuke" name="map" value="Nuke"> Nuke</label>
                <label for="overpass"><input type="radio" id="overpass" name="map" value="Overpass"> Overpass</label>
                <button type="submit">Проголосовать</button>
            </form>
        </div>
    </div>
    <footer>
        <p>© 2025 Шоу-матч по CS2. Все права защищены. | <a href="#">Правила участия</a></p>
    </footer>
    <script>
        // Установите время 15 января 2025 года, 20:00
        const countdownDate = new Date("2025-01-15T20:00:00").getTime();

        function updateCountdown() {
            const now = new Date().getTime();
            const distance = countdownDate - now;

            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            // Используем padStart или альтернативу для старых браузеров
            const formatTime = (time) => (time < 10 ? '0' : '') + time;

            document.getElementById("countdown").innerHTML = `До начала матча: ${formatTime(hours)}:${formatTime(minutes)}:${formatTime(seconds)}`;

            if (distance < 0) {
                clearInterval(interval);
                document.getElementById("countdown").innerHTML = "Матч начался!";
            }
        }

        const interval = setInterval(updateCountdown, 1000);
        updateCountdown();
    </script>
</body>
</html>
