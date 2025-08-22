<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тренировка для живота, ног и ягодиц</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f8f6ff 0%, #fff6fb 100%);
            color: #333;
            line-height: 1.6;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px;
            background: linear-gradient(to right, #ff6b6b, #ff8e8e);
            color: white;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(255, 107, 107, 0.3);
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }
        
        h2 {
            font-size: 1.8rem;
            margin: 25px 0 15px;
            color: #ff6b6b;
            padding-bottom: 8px;
            border-bottom: 2px solid #ff6b6b;
        }
        
        h3 {
            font-size: 1.4rem;
            margin: 20px 0 10px;
            color: #ff6b6b;
        }
        
        p {
            margin-bottom: 15px;
            font-size: 1.1rem;
        }
        
        .intro {
            background-color: white;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            margin-bottom: 30px;
        }
        
        .tabs {
            display: flex;
            margin-bottom: 25px;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.08);
        }
        
        .tab {
            flex: 1;
            padding: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
        }
        
        .tab.active {
            background: linear-gradient(to right, #6a11cb, #2575fc);
            color: white;
        }
        
        .tab:hover:not(.active) {
            background: #f0f0f0;
        }
        
        .program-content {
            display: none;
        }
        
        .program-content.active {
            display: block;
        }
        
        .program-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .program-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease;
        }
        
        .program-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
        }
        
        .card-header {
            background: linear-gradient(to right, #6a11cb, #2575fc);
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        .card-body {
            padding: 20px;
        }
        
        .exercise {
            margin-bottom: 20px;
            padding-bottom: 20px;
            border-bottom: 1px dashed #eee;
            display: flex;
            flex-direction: column;
        }
        
        .exercise:last-child {
            border-bottom: none;
            margin-bottom: 0;
            padding-bottom: 0;
        }
        
        .exercise-title {
            display: flex;
            align-items: center;
            margin-bottom: 10px;
            color: #6a11cb;
        }
        
        .exercise-title i {
            margin-right: 10px;
            font-size: 1.2rem;
        }
        
        .exercise-image {
            width: 100%;
            height: 180px;
            background-color: #f8f9fa;
            border-radius: 10px;
            margin-bottom: 12px;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }
        
        .exercise-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .exercise-placeholder {
            font-size: 3rem;
            color: #dee2e6;
        }
        
        .exercise-content {
            flex: 1;
        }
        
        .schedule {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }
        
        .day-card {
            background: white;
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            text-align: center;
        }
        
        .day-card h3 {
            color: #6a11cb;
            margin-bottom: 15px;
        }
        
        .tips {
            background: linear-gradient(45deg, #6a11cb, #2575fc);
            color: white;
            padding: 30px;
            border-radius: 15px;
            margin-bottom: 40px;
            box-shadow: 0 5px 20px rgba(37, 117, 252, 0.3);
        }
        
        .tips h2 {
            color: white;
            border-bottom: 2px solid rgba(255, 255, 255, 0.3);
        }
        
        .btn {
            display: inline-block;
            background: linear-gradient(to right, #ff6b6b, #ff8e8e);
            color: white;
            padding: 12px 25px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            box-shadow: 0 4px 15px rgba(255, 107, 107, 0.4);
            transition: all 0.3s ease;
            border: none;
            cursor: pointer;
            font-size: 1rem;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(255, 107, 107, 0.5);
        }
        
        .btn-container {
            text-align: center;
            margin: 30px 0;
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: #777;
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2rem;
            }
            
            .program-grid, .schedule {
                grid-template-columns: 1fr;
            }
            
            .tabs {
                flex-direction: column;
            }
            
            .exercise-image {
                height: 150px;
            }
        }
        
        .animation-container {
            text-align: center;
            margin: 30px 0;
        }
        
        .animation-box {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #ff6b6b, #6a11cb);
            border-radius: 15px;
            position: relative;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
            box-shadow: 0 8px 25px rgba(106, 17, 203, 0.3);
        }
        
        .pulse {
            width: 20px;
            height: 20px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            position: absolute;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% {
                transform: scale(1);
                opacity: 0.8;
            }
            70% {
                transform: scale(5);
                opacity: 0;
            }
            100% {
                transform: scale(1);
                opacity: 0;
            }
        }
        
        .equipment {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
        }
        
        .equipment h3 {
            color: #6a11cb;
        }
        
        .image-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .image-item {
            position: relative;
            border-radius: 10px;
            overflow: hidden;
            height: 200px;
            background: #6a11cb;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-weight: bold;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .image-item i {
            font-size: 3rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Фитнес-программа для Любимой</h1>
            <p>Поперечная мышца живота, ноги и ягодицы с гантелями</p>
        </header>
        
        <!-- <div class="intro">
            <h2>Комплексная программа для идеальной формы</h2>
            <p>Эта программа сочетает упражнения для укрепления поперечной мышцы живота, которая действует как естественный корсет, и эффективные упражнения для ног и ягодиц с использованием гантелей.</p>
            
            <div class="animation-container">
                <div class="animation-box">
                    <div class="pulse" style="top: 40%; left: 45%;"></div>
                    Ваш путь к идеальной фигуре
                </div>
            </div> -->
            
            <h3>Галерея упражнений</h3>
            <div class="image-grid">
                <div class="image-item">
                    <i class="fas fa-running"></i>
                </div>
                <div class="image-item">
                    <i class="fas fa-dumbbell"></i>
                </div>
                <div class="image-item">
                    <i class="fas fa-heart"></i>
                </div>
                <div class="image-item">
                    <i class="fas fa-spa"></i>
                </div>
            </div>
        </div>
        
        <div class="tabs">
            <div class="tab active" data-tab="abs">Мышцы живота</div>
            <div class="tab" data-tab="legs">Ноги и ягодицы</div>
            <div class="tab" data-tab="schedule">График</div>
            <div class="tab" data-tab="tips">Советы</div>
        </div>
        
        <div class="program-content active" id="abs-content">
            <h2>Тренировка поперечной мышцы живота</h2>
            <div class="program-grid">
                <div class="program-card">
                    <div class="card-header">
                        <h3>Базовые упражнения</h3>
                    </div>
                    <div class="card-body">
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-lungs"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-fire"></i>
                                    <span>Вакуум живота</span>
                                </div>
                                <p>3 подхода по 10-15 повторений. Задерживайте дыхание на 15-20 секунд.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-vector-square"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-fire"></i>
                                    <span>Планка</span>
                                </div>
                                <p>3 подхода по 30-60 секунд. Следите, чтобы спина была прямой.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-archway"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-fire"></i>
                                    <span>Мостик</span>
                                </div>
                                <p>3 подхода по 15 повторений. Поднимайте таз как можно выше.</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="program-card">
                    <div class="card-header">
                        <h3>Упражнения с оборудованием</h3>
                    </div>
                    <div class="card-body">
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-basketball-ball"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Скручивания с мячом</span>
                                </div>
                                <p>3 подхода по 15 повторений. Используйте фитбол или небольшой мяч.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-balance-scale-right"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Боковая планка</span>
                                </div>
                                <p>3 подхода по 30 секунд на каждую сторону. Укрепляет косые мышцы.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-dumbbell"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Наклоны с гантелями</span>
                                </div>
                                <p>3 подхода по 12 повторений на каждую сторону. Используйте легкие гантели.</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="program-card">
                    <div class="card-header">
                        <h3>Растяжка и расслабление</h3>
                    </div>
                    <div class="card-body">
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-cat"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-spa"></i>
                                    <span>Кошка-корова</span>
                                </div>
                                <p>2 подхода по 10 повторений. Отлично растягивает мышцы пресса и спины.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-wind"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-spa"></i>
                                    <span>Дыхание животом</span>
                                </div>
                                <p>5 минут глубокого дыхания. Концентрируйтесь на расширении живота при вдохе.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-basketball-ball"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-spa"></i>
                                    <span>Растяжка на фитболе</span>
                                </div>
                                <p>3 подхода по 30 секунд. Лягте на фитбол спиной и потянитесь.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="program-content" id="legs-content">
            <h2>Тренировка ног и ягодиц с гантелями</h2>
            
            <div class="equipment">
                <h3>Рекомендуемое оборудование</h3>
                <p>• Гантели 2-5 кг (начальный уровень)</p>
                <p>• Гантели 5-10 кг (продвинутый уровень)</p>
                <p>• Коврик для упражнений</p>
                <p>• Стул для опоры (по необходимости)</p>
            </div>
            
            <div class="program-grid">
                <div class="program-card">
                    <div class="card-header">
                        <h3>Базовые упражнения</h3>
                    </div>
                    <div class="card-body">
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-dumbbell"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Приседания с гантелями</span>
                                </div>
                                <p>4 подхода по 12-15 повторений. Держите гантели у плеч или вдоль тела.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-walking"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Выпады с гантелями</span>
                                </div>
                                <p>3 подхода по 10-12 повторений на каждую ногу. Сохраняйте равновесие.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-hands"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Румынская тяга с гантелями</span>
                                </div>
                                <p>3 подхода по 12-15 повторений. Отлично прорабатывает ягодицы и бицепс бедра.</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="program-card">
                    <div class="card-header">
                        <h3>Изолирующие упражнения</h3>
                    </div>
                    <div class="card-body">
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-archway"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Ягодичный мостик с гантелью</span>
                                </div>
                                <p>4 подхода по 15-20 повторений. Положите гантель на таз для утяжеления.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-shoe-prints"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Подъемы на носки с гантелями</span>
                                </div>
                                <p>3 подхода по 20 повторений. Укрепляет икры.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-undo-alt"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Махи ногой с утяжелителем</span>
                                </div>
                                <p>3 подхода по 15 повторений на каждую ногу. Можно использовать гантель как утяжелитель.</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="program-card">
                    <div class="card-header">
                        <h3>Комплексные движения</h3>
                    </div>
                    <div class="card-body">
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-arrows-alt-v"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Становая тяга с гантелями</span>
                                </div>
                                <p>3 подхода по 10-12 повторений. Укрепляет всю заднюю поверхность бедра.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-hands-helping"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Берпи с гантелями</span>
                                </div>
                                <p>3 подхода по 8-10 повторений. Кардио + силовая нагрузка.</p>
                            </div>
                        </div>
                        
                        <div class="exercise">
                            <div class="exercise-image">
                                <div class="exercise-placeholder">
                                    <i class="fas fa-arrows-alt-h"></i>
                                </div>
                            </div>
                            <div class="exercise-content">
                                <div class="exercise-title">
                                    <i class="fas fa-dumbbell"></i>
                                    <span>Приседания сумо с гантелью</span>
                                </div>
                                <p>4 подхода по 12-15 повторений. Широкие приседания с одной гантелью.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="program-content" id="schedule-content">
            <h2>График тренировок на неделю</h2>
            <div class="schedule">
                <div class="day-card">
                    <h3>Понедельник</h3>
                    <p>Поперечная мышца живота</p>
                    <p>20 минут</p>
                </div>
                
                <div class="day-card">
                    <h3>Вторник</h3>
                    <p>Ноги и ягодицы с гантелями</p>
                    <p>30 минут</p>
                </div>
                
                <div class="day-card">
                    <h3>Среда</h3>
                    <p>Растяжка и восстановление</p>
                    <p>15 минут</p>
                </div>
                
                <div class="day-card">
                    <h3>Четверг</h3>
                    <p>Поперечная мышца живота</p>
                    <p>20 минут</p>
                </div>
                
                <div class="day-card">
                    <h3>Пятница</h3>
                    <p>Ноги и ягодицы с гантелями</p>
                    <p>30 минут</p>
                </div>
                
                <div class="day-card">
                    <h3>Суббота</h3>
                    <p>Активный отдых (прогулка, йога)</p>
                    <p>40 минут</p>
                </div>
                
                <div class="day-card">
                    <h3>Воскресенье</h3>
                    <p>Полный отдых</p>
                </div>
            </div>
        </div>
        
        <div class="program-content" id="tips-content">
            <div class="tips">
                <h2>Советы для эффективных тренировок</h2>
                <p>• Начинайте с разминки 5-7 минут перед каждой тренировкой</p>
                <p>• Выбирайте вес гантелей, который позволяет сохранять правильную технику</p>
                <p>• Следите за дыханием: выдох на усилии, вдох на расслаблении</p>
                <p>• Сочетайте тренировки со здоровым питанием и питьевым режимом</p>
                <p>• Давайте мышцам 48 часов на восстановление между силовыми тренировками</p>
                <p>• Постепенно увеличивайте вес гантелей для прогресса</p>
                <p>• Концентрируйтесь на целевых мышцах во время выполнения упражнений</p>
            </div>
        </div>
        
        <div class="btn-container">
            <a href="#" class="btn">Начать тренировку</a>
        </div>
    </div>
    
    <footer>
        <p> Программа тренировок для живота, ног и ягодиц </p>
    </footer>

    <script>
        // Анимация пульсации
        function createPulse() {
            const box = document.querySelector('.animation-box');
            const pulse = document.createElement('div');
            pulse.classList.add('pulse');
            
            // Случайная позиция
            const top = Math.floor(Math.random() * 80) + 10;
            const left = Math.floor(Math.random() * 80) + 10;
            
            pulse.style.top = `${top}%`;
            pulse.style.left = `${left}%`;
            
            box.appendChild(pulse);
            
            // Удаление элемента после завершения анимации
            setTimeout(() => {
                pulse.remove();
            }, 2000);
        }
        
        // Создаем новую пульсацию каждые 0.5 секунд
        setInterval(createPulse, 500);
        
        // Обработчик для кнопки
        document.querySelector('.btn').addEventListener('click', function(e) {
            e.preventDefault();
            alert('Отлично! Начинаем тренировку! Помните о правильной технике и дыхании.');
        });
        
        // Табы
        const tabs = document.querySelectorAll('.tab');
        const contents = document.querySelectorAll('.program-content');
        
        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                const target = tab.getAttribute('data-tab');
                
                // Убираем активный класс у всех табов и контента
                tabs.forEach(t => t.classList.remove('active'));
                contents.forEach(c => c.classList.remove('active'));
                
                // Добавляем активный класс текущему табу и соответствующему контенту
                tab.classList.add('active');
                document.getElementById(`${target}-content`).classList.add('active');
            });
        });
    </script>
</body>
</html>
