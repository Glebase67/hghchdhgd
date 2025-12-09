<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Музей звезды в пустыне</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Times New Roman', serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
        }
        
        .header {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
                        url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%23333"/><path d="M0,0 L100,100 M100,0 L0,100" stroke="%23555" stroke-width="2"/></svg>');
            color: #fff;
            padding: 30px 0;
            text-align: center;
            position: relative;
        }
        
        .header:after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(to right, #8B0000, #DAA520, #8B0000);
        }
        
        .header h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            text-transform: uppercase;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }
        
        .header p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto;
            opacity: 0.9;
        }
        
        .nav {
            background-color: #333;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        
        .nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
        }
        
        .nav ul li {
            margin: 0;
        }
        
        .nav ul li a {
            display: block;
            color: #fff;
            text-decoration: none;
            padding: 15px 25px;
            font-weight: bold;
            transition: all 0.3s ease;
            border-right: 1px solid #555;
        }
        
        .nav ul li:last-child a {
            border-right: none;
        }
        
        .nav ul li a:hover {
            background-color: #8B0000;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .section {
            margin-bottom: 40px;
            background: #fff;
            border-radius: 5px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 30px;
            border-left: 5px solid #8B0000;
        }
        
        .section h2 {
            color: #8B0000;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #DAA520;
            font-size: 1.8rem;
        }
        
        .heroes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .hero-card {
            background: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 15px;
            text-align: center;
            transition: transform 0.3s ease;
        }
        
        .hero-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .hero-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 3px;
margin-bottom: 10px;
            border: 1px solid #ddd;
        }
        
        .exhibits {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 20px;
        }
        
        .exhibit {
            background: #f9f9f9;
            border-radius: 5px;
            overflow: hidden;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .exhibit img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-bottom: 3px solid #8B0000;
        }
        
        .exhibit-content {
            padding: 15px;
        }
        
        .exhibit h3 {
            color: #8B0000;
            margin-bottom: 10px;
        }
        
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 30px auto;
        }
        
        .timeline:before {
            content: '';
            position: absolute;
            top: 0;
            bottom: 0;
            width: 4px;
            background: #8B0000;
            left: 50%;
            margin-left: -2px;
        }
        
        .timeline-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            box-sizing: border-box;
        }
        
        .timeline-item:nth-child(odd) {
            left: 0;
        }
        
        .timeline-item:nth-child(even) {
            left: 50%;
        }
        
        .timeline-content {
            padding: 20px;
            background: #f9f9f9;
            border-radius: 5px;
            border: 1px solid #ddd;
            position: relative;
        }
        
        .timeline-content:after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background: #8B0000;
            border: 4px solid #fff;
            border-radius: 50%;
            top: 20px;
        }
        
        .timeline-item:nth-child(odd) .timeline-content:after {
            right: -10px;
        }
        
        .timeline-item:nth-child(even) .timeline-content:after {
            left: -10px;
        }
        
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }
        
        .contact-item {
            background: #f9f9f9;
            padding: 20px;
            border-radius: 5px;
            text-align: center;
            border-left: 3px solid #8B0000;
        }
        
        .contact-item h3 {
            color: #8B0000;
            margin-bottom: 10px;
        }
        
        .footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 30px 0;
            margin-top: 40px;
        }
        
        .footer p {
            margin: 5px 0;
        }
        
        .btn {
            display: inline-block;
            background: #8B0000;
            color: #fff;
            padding: 10px 20px;
            border-radius: 3px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 10px;
            transition: background 0.3s ease;
        }
        
        .btn:hover {
            background: #A52A2A;
        }
        
        @media (max-width: 768px) {
            .nav ul {
                flex-direction: column;
            }
            
            .nav ul li a {
                border-right: none;
                border-bottom: 1px solid #555;
            }
            
            .timeline:before {
                left: 31px;
            }
            
            .timeline-item {
width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            
            .timeline-item:nth-child(even) {
                left: 0;
            }
            
            .timeline-content:after {
                left: 21px !important;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="container">
            <h1>Музей звезды в пустыне</h1>
            <p>Сохранение памяти о подвигах и героизме защитников Отечества</p>
        </div>
    </header>
    
    <nav class="nav">
        <ul>
            <li><a href="#main">Главная</a></li>
            <li><a href="#exhibits">Экспозиции</a></li>
            <li><a href="#history">История</a></li>
            <li><a href="#heroes">Герои</a></li>
            <li><a href="#contacts">Контакты</a></li>
        </ul>
    </nav>
    
    <div class="container">
        <section id="main" class="section">
            <h2>О музее</h2>
            <p>Музей истории создания противоракетной обороны «Звёзды в пустыне» хранит память о героическом труде сотен тысяч наших соотечественников, в том числе выдающихся ученых и офицеров-испытателей, на Балхашском полигоне противоракетной обороны (ПРО) в середине прошлого столетия. Противоракетная оборона страны создавалась в так называемый период «холодной войны».  Ее первые удары приняли на себя фронтовики.
      Посетители музея услышат рассказ о создании первой системы ПРО и первой противоракете, которая на огромной скорости в бескрайнем космическом пространстве способна найти и уничтожить межконтинентальную баллистическую ракету вероятного противника.
      Наши ученые и военные справились с решением этой задачи в марте 1961 года. Американцы смогли повторить такой эксперимент спустя 23 года<p>
            <a href="#contacts" class="btn">Записаться на экскурсию</a>
        <section id="exhibits" class="section">
            <h2>Экспозиции</h2>
            <div class="exhibits">
                <div class="exhibit">
                    <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200' viewBox='0 0 300 200'><rect width='300' height='200' fill='%23ddd'/><text x='150' y='100' font-family='Arial' font-size='18' fill='%23888' text-anchor='middle'>Оружие Победы</text></svg>" alt="Оружие Победы">
                    <div class="exhibit-content">
                        <h3>Оружие Победы</h3>
                        <p>Коллекция стрелкового оружия, артиллерии и бронетехники времен Великой Отечественной войны.</p>
                    </div>
                </div>
                
                <div class="exhibit">
                    <img width="145" height="120" alt="Image" src="https://github.com/user-attachments/assets/550a097b-aa67-4290-95b5-63f316368c4a" />
                    <div class="exhibit-content">
                        <h3>Награды и знаки отличия</h3>
                        <p>Уникальная коллекция орденов, медалей и наградных знаков различных исторических периодов.</p>
                    </div>
                </div>
                
                <div class="exhibit">
                    <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='300' height='200' viewBox='0 0 300 200'><rect width='300' height='200' fill='%23ddd'/><text x='150' y='100' font-family='Arial' font-size='18' fill='%23888' text-anchor='middle'>Фронтовые письма</text></svg>" alt="Фронтовые письма">
                    <div class="exhibit-content">
                        <h3>Фронтовые письма</h3>
                        <p>Подлинные письма с фронта, которые передают эмоции и переживания солдат военных лет.</p>
</div>
                </div>
            </div>
        </section>
        
        <section id="history" class="section">
            <h2>Историческая хроника</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>1941-1942</h3>
                        <p>Оборона Брестской крепости, битва за Москву, начало блокады Ленинграда.</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>1942-1943</h3>
                        <p>Сталинградская битва, прорыв блокады Ленинграда, Курская битва.</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>1944</h3>
                        <p>Операция "Багратион", освобождение территории СССР, выход к границам Европы.</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <h3>1945</h3>
                        <p>Берлинская операция, подписание акта о безоговорочной капитуляции Германии.</p>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="heroes" class="section">
            <h2>Герои войны</h2>
            <div class="heroes-grid">
                <div class="hero-card">
                    <![Image](https://github.com/user-attachments/assets/cb533665-b32d-46a9-b8cc-414c603ff337)>
                    <h3>Александр Матросов</h3>
                    <p>Закрыл амбразуру дзота своим телом, обеспечив успех атаки.</p>
                </div>
                
                <div class="hero-card">
                    <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='250' height='200' viewBox='0 0 250 200'><rect width='250' height='200' fill='%23ddd'/><text x='125' y='100' font-family='Arial' font-size='16' fill='%23888' text-anchor='middle'>Зоя Космодемьянская</text></svg>" alt="Зоя Космодемьянская">
                    <h3>Зоя Космодемьянская</h3>
                    <p>Партизанка, первая женщина - Герой Советского Союза в годы войны.</p>
                </div>
                
                <div class="hero-card">
                    <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='250' height='200' viewBox='0 0 250 200'><rect width='250' height='200' fill='%23ddd'/><text x='125' y='100' font-family='Arial' font-size='16' fill='%23888' text-anchor='middle'>Иван Кожедуб</text></svg>" alt="Иван Кожедуб">
                    <h3>Иван Кожедуб</h3>
                    <p>Лётчик-ас, трижды Герой Советского Союза, сбил 64 вражеских самолёта.</p>
                </div>
                
                <div class="hero-card">
                    <img src="data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='250' height='200' viewBox='0 0 250 200'><rect width='250' height='200' fill='%23ddd'/><text x='125' y='100' font-family='Arial' font-size='16' fill='%23888' text-anchor='middle'>Василий Зайцев</text></svg>" alt="Василий Зайцев">
                    <h3>Василий Зайцев</h3>
                    <p>Легендарный снайпер Сталинградской битвы, уничтожил более 200 врагов.</p>
                </div>
            </div>
</section>
        
        <section id="contacts" class="section">
            <h2>Контакты и посещение</h2>
            <div class="contact-info">
                <div class="contact-item">
                    <h3>Адрес</h3>
                    <p>г. Москва, ул. Углическая 17</p>
                </div>
                
                <div class="contact-item">
                    <h3>Телефон</h3>
                    <p>+8-(499)-908-10-21</p>
                </div>
                
                <div class="contact-item">
                    <h3>Часы работы</h3>
                    <p>Вт-Чт 8:00-14:00,Пн-Пт 8:00-16:45<br>Сб-Вс выходной</p>
                </div>
                
                <div class="contact-item">
                    <h3>Экскурсии</h3>
                    <p>Запись по телефону за 3 дня</p>
                </div>
            </div>
            
            <div style="margin-top: 30px; text-align: center;">
                <p>Для организованных групп школьников и студентов действуют льготные условия посещения.</p>
                <a href="#" class="btn">Записаться на экскурсию</a>
            </div>
        </section>
    <footer class="footer">
        <div class="container">
            <p>Музей Звезды в пустыне © 2023</p>
            <p>Все права защищены. При использовании материалов ссылка на музей обязательна.</p>
        </div>
    </footer>
