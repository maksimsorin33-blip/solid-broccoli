<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <title>Сайт о породах собак</title>
        <link rel="stylesheet" href="style.css">
        <!-- Подключение сброса стилей -->
        <link rel="stylesheet" href="reset.css" />
        <!-- Подключение файла стилей -->
        <link rel="stylesheet" href="style.css" />
        <link href="media-queries.css" rel="stylesheet" type="text/css">
        <script src="main.js"></script>
        <style>
            /* Добавляем новую цветовую схему */
            :root {
                --primary-color: #2c3e50;
                --secondary-color: #3498db;
                --accent-color: #e74c3c;
                --light-bg: #ecf0f1;
                --dark-text: #2c3e50;
                --dog-brown: #8B4513;
                --dog-gold: #FFD700;
            }
            
            body {
                background-color: var(--light-bg);
                color: var(--dark-text);
                font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            }
            
            header {
                background: linear-gradient(135deg, var(--primary-color), #1a252f);
                color: white;
                display: flex;
                justify-content: space-between;
                align-items: center;
                padding: 15px 30px;
                position: relative;
            }
            
            .header-contacts {
                display: flex;
                align-items: center;
                gap: 20px;
            }
            
            .vk-link {
                color: white;
                text-decoration: none;
                background-color: #4a76a8;
                padding: 8px 15px;
                border-radius: 5px;
                font-weight: bold;
                transition: all 0.3s;
                display: flex;
                align-items: center;
                gap: 5px;
            }
            
            .vk-link:hover {
                background-color: #5a86b8;
                transform: translateY(-2px);
                box-shadow: 0 4px 8px rgba(0,0,0,0.2);
            }
            
            .phone-number {
                color: white;
                font-weight: bold;
                background-color: rgba(255,255,255,0.1);
                padding: 8px 15px;
                border-radius: 5px;
                border: 1px solid rgba(255,255,255,0.2);
            }
            
            .entrance, .btn {
                background-color: var(--secondary-color);
                color: white;
                border: none;
                padding: 10px 20px;
                border-radius: 5px;
                cursor: pointer;
                transition: background-color 0.3s;
            }
            
            .entrance:hover, .btn:hover {
                background-color: var(--accent-color);
            }
            
            /* Стили для формы входа */
            .form-popup {
                display: none;
                position: fixed;
                top: 50%;
                left: 50%;
                transform: translate(-50%, -50%);
                z-index: 1000;
                background-color: white;
                padding: 30px;
                border-radius: 10px;
                box-shadow: 0 5px 20px rgba(0,0,0,0.3);
                width: 90%;
                max-width: 400px;
            }
            
            .form-container h1 {
                color: var(--primary-color);
                margin-bottom: 20px;
                text-align: center;
            }
            
            .form-container label {
                display: block;
                margin-top: 15px;
                color: var(--dark-text);
                font-weight: bold;
            }
            
            .form-container input[type="text"] {
                width: 100%;
                padding: 10px;
                margin-top: 5px;
                border: 2px solid #ddd;
                border-radius: 5px;
                box-sizing: border-box;
            }
            
            .form-container .btn {
                width: 100%;
                margin-top: 15px;
            }
            
            .cancel {
                background-color: #95a5a6;
            }
            
            .cancel:hover {
                background-color: #7f8c8d;
            }
            
            .sidenav {
                background-color: var(--primary-color);
                height: 100%;
                width: 0;
                position: fixed;
                z-index: 1;
                top: 0;
                left: 0;
                overflow-x: hidden;
                transition: 0.5s;
                padding-top: 60px;
            }
            
            .sidenav a {
                padding: 8px 8px 8px 32px;
                text-decoration: none;
                font-size: 25px;
                color: #818181;
                display: block;
                transition: 0.3s;
            }
            
            .sidenav .closebtn {
                position: absolute;
                top: 0;
                right: 25px;
                font-size: 36px;
                margin-left: 50px;
            }
            
            section {
                background-color: white;
                border-radius: 10px;
                box-shadow: 0 4px 6px rgba(0,0,0,0.1);
                margin: 20px 0;
                padding: 20px;
                border-left: 5px solid var(--secondary-color);
            }
            
            .dog-breed-section {
                border-left: 5px solid var(--dog-brown);
            }
            
            .products-item_heading,
            .dog-breeds_heading,
            .dog-breeds-1_heading,
            .dog-breeds-2_heading,
            .dog-breeds-3_heading,
            .dog-breeds-4_heading {
                color: var(--primary-color);
                border-bottom: 2px solid var(--dog-brown);
                padding-bottom: 10px;
            }
            
            .container {
                background-color: white;
                border-radius: 10px;
                padding: 30px;
                box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            }
            
            .topic-text {
                color: var(--primary-color);
                font-size: 24px;
                font-weight: bold;
            }
            
            .input-box input,
            .input-box textarea {
                border: 2px solid #ddd;
                border-radius: 5px;
                padding: 12px;
                width: 100%;
                transition: border-color 0.3s;
            }
            
            .input-box input:focus,
            .input-box textarea:focus {
                border-color: var(--secondary-color);
                outline: none;
            }
            
            .footer {
                background-color: var(--primary-color);
                color: white;
                padding: 20px;
                text-align: center;
                margin-top: 40px;
            }
            
            .footer a {
                color: var(--secondary-color);
                text-decoration: none;
            }
            
            .footer a:hover {
                color: var(--accent-color);
                text-decoration: underline;
            }
            
            /* Стили для изображений собак */
            .products-item_image,
            .dog-breeds_image,
            .dog-breeds-1_image,
            .dog-breeds-2_image,
            .dog-breeds-3_image,
            .dog-breeds-4_image {
                max-width: 100%;
                height: 300px;
                object-fit: cover;
                border-radius: 8px;
                margin: 15px 0;
                display: block;
                border: 3px solid var(--dog-brown);
            }
            
            /* Убираем логотип и главное изображение */
            .logotip,
            .the_title_of_the_title_image {
                display: none;
            }
            
            /* Скрываем изображения в шапке */
            .meny-toggle img,
            .login img {
                display: none;
            }
            
            .meny-toggle,
            .login {
                display: none;
            }
            
            /* Стили для лого в шапке */
            .logo span {
                font-size: 20px;
                font-weight: bold;
                color: white;
            }
            
            .dog-paw {
                color: var(--dog-gold);
                font-size: 24px;
                margin: 0 5px;
            }
            
            .intro-text {
                font-size: 18px;
                line-height: 1.6;
                text-align: justify;
            }
            
            .breed-characteristics {
                background-color: #f8f9fa;
                padding: 15px;
                border-radius: 8px;
                margin-top: 15px;
                border-left: 4px solid var(--dog-brown);
            }
            
            .breed-characteristics ul {
                padding-left: 20px;
            }
            
            .breed-characteristics li {
                margin-bottom: 8px;
            }
        </style>
    </head>
    <body>
        <header>
            <button class="entrance" id="Vxod" onclick="openForm()">Вход в кинологический клуб</button>
            <div class="form-popup" id="myForm">
                <form action="#" class="form-container">
                  <h1>Войти в кинологический клуб</h1>
                  <label for="name"><b>Имя</b></label>
                  <input type="text" placeholder="Ваше имя" name="name" required>
                  <label for="email"><b>Е-мейл</b></label>
                  <input type="text" placeholder="Ваш е-мейл" name="email" required>
                  <button type="submit" class="btn">Вступить в клуб</button>
                  <button type="button" class="btn cancel" id="Vixod" onclick="closeForm()">Закрыть</button>
                </form>
            </div>
            
            <!-- Убраны изображения в меню-переключателе -->
            <div class="meny-toggle" onclick="openNav()">
                <!-- Изображение убрано -->
            </div>
            
            <div class="logo">
                <span>🐕 Исследование пород собак 🐕</span>
            </div>
            
            <!-- Добавлены контакты в шапку -->
            <div class="header-contacts">
                <a href="https://vk.com/dogbreeds" class="vk-link" target="_blank">Группа VK о собаках</a>
                <div class="phone-number">Кинологи: +7 (999) 123-45-67</div>
            </div>
            
            <!-- Убрано изображение для входа -->
            <div class="login">
                <!-- Изображение убрано -->
            </div>
        </header>
        
        <!-- Боковое меню (очищено) -->
        <aside id="aside" class="sidenav">
            <nav>
                <a href="javascript:void(0)" class="closebtn" onclick="closeNav()">&times;</a>
                <!-- Удалены все ссылки и контакты -->
            </nav>
        </aside>
        
        <main>
            <section class="the_title_of_the_title"> 
                <div class="the_title_of_the_title_description intro-text">
                    <span class="dog-paw">🐾</span> Собака — не просто домашнее животное, а верный друг и компаньон человека на протяжении тысячелетий. Каждая порода собак обладает уникальными характеристиками, темпераментом и особенностями ухода. От миниатюрных чихуахуа до величественных сенбернаров — мир собак невероятно разнообразен. На этом сайте мы исследуем различные породы, их историю, особенности содержания и предназначение. <span class="dog-paw">🐾</span>
                </div>
            </section>
            
            <!-- Раздел 1: Немецкая овчарка -->
            <section class="products-item dog-breed-section"> 
                <h1 class="products-item_heading">Немецкая овчарка — универсальная служебная порода</h1>
                <img class="products-item_image" src="Photo1.jpg" alt="Немецкая овчарка">
                <div class="products-item_description">
                    Немецкая овчарка — одна из самых популярных и узнаваемых пород в мире. Изначально выведенная для выпаса овец, сегодня она успешно служит в полиции, армии, на таможне, а также является прекрасным компаньоном и защитником семьи.
                    <div class="breed-characteristics">
                        <strong>Характеристики породы:</strong>
                        <ul>
                            <li><strong>Рост:</strong> 55-65 см (кобели), 50-60 см (суки)</li>
                            <li><strong>Вес:</strong> 30-40 кг</li>
                            <li><strong>Продолжительность жизни:</strong> 9-13 лет</li>
                            <li><strong>Темперамент:</strong> Умная, преданная, смелая, уверенная</li>
                            <li><strong>Назначение:</strong> Служебная, охранная, семейная собака</li>
                        </ul>
                    </div>
                </div>
            </section>
            
            <!-- Раздел 2: Золотистый ретривер -->
            <section class="dog-breeds dog-breed-section"> 
                <h1 class="dog-breeds_heading">Золотистый ретривер — семейный любимец</h1>
                <img class="dog-breeds_image" src="Photo2.jpg" alt="Золотистый ретривер">
                <div class="dog-breeds_description">
                    Золотистый ретривер — порода, известная своим дружелюбным характером, интеллектом и красивой золотистой шерстью. Идеальная семейная собака, прекрасно ладящая с детьми и другими животными. Часто используется как собака-терапевт и поводырь.
                    <div class="breed-characteristics">
                        <strong>Особенности породы:</strong>
                        <ul>
                            <li>Отличные способности к обучению</li>
                            <li>Высокий уровень эмпатии</li>
                            <li>Любовь к воде и плаванию</li>
                            <li>Нуждается в регулярных физических нагрузках</li>
                            <li>Требует регулярного ухода за шерстью</li>
                        </ul>
                    </div>
                </div>
            </section>
            
            <!-- Раздел 3: Сибирский хаски -->
            <section class="dog-breeds-1 dog-breed-section"> 
                <h1 class="dog-breeds-1_heading">Сибирский хаски — северная ездовая собака</h1>
                <img class="dog-breeds-1_image" src="Photo3.jpg" alt="Сибирский хаски">
                <div class="dog-breeds-1_description">
                    Сибирский хаски — порода, выведенная чукчами для перевозки грузов на большие расстояния в суровых условиях Севера. Известны своими яркими голубыми глазами, густой шерстью и невероятной выносливостью. Обладают дружелюбным, но независимым характером.
                    <div class="breed-characteristics">
                        <strong>Особенности содержания:</strong>
                        <ul>
                            <li>Требует очень активного образа жизни</li>
                            <li>Сильно линяет 2 раза в год</li>
                            <li>Может быть упрямым при обучении</li>
                            <li>Плохо переносит жару</li>
                            <li>Имеет сильный охотничий инстинкт</li>
                        </ul>
                    </div>
                </div>
            </section>
            
            <!-- Раздел 4: Такса -->
            <section class="dog-breeds-2 dog-breed-section"> 
                <h1 class="dog-breeds-2_heading">Такса — охотничья норная собака</h1>
                <img class="dog-breeds-2_image" src="Photo4.jpg" alt="Такса">
                <div class="dog-breeds-2_description">
                    Такса — небольшая собака с длинным телом и короткими лапами, изначально выведенная для охоты на барсуков и других норных животных. Обладает бесстрашным характером, высоким интеллектом и большой привязанностью к хозяину. Бывают трех размеров и трех типов шерсти.
                    <div class="breed-characteristics">
                        <strong>Разновидности такс:</strong>
                        <ul>
                            <li><strong>По размеру:</strong> стандартная, миниатюрная, кроличья</li>
                            <li><strong>По шерсти:</strong> гладкошерстная, длинношерстная, жесткошерстная</li>
                            <li><strong>Особенности:</strong> Склонность к заболеваниям позвоночника</li>
                            <li><strong>Характер:</strong> Упрямый, умный, энергичный</li>
                        </ul>
                    </div>
                </div>
            </section>
            
            <!-- Раздел 5: Французский бульдог -->
            <section class="dog-breeds-3 dog-breed-section"> 
                <h1 class="dog-breeds-3_heading">Французский бульдог — декоративный компаньон</h1>
                <img class="dog-breeds-3_image" src="Photo5.jpg" alt="Французский бульдог">
                <div class="dog-breeds-3_description">
                    Французский бульдог — популярная декоративная порода, известная своими большими ушами-«летучими мышами» и дружелюбным характером. Идеальная собака для содержания в квартире, не требует длительных прогулок и сложного ухода. Отлично ладит с детьми и другими домашними животными.
                    <div class="breed-characteristics">
                        <strong>Важно знать:</strong>
                        <ul>
                            <li>Плохо переносят жару из-за брахицефального строения черепа</li>
                            <li>Склонны к аллергиям и кожным заболеваниям</li>
                            <li>Часто имеют проблемы с дыханием и храпят</li>
                            <li>Нуждаются в регулярной чистке складок на морде</li>
                            <li>Очень привязываются к хозяину и не любят одиночества</li>
                        </ul>
                    </div>
                </div>
            </section>
            
            <!-- Раздел 6: Бордер-колли -->
            <section class="dog-breeds-4 dog-breed-section"> 
                <h1 class="dog-breeds-4_heading">Бордер-колли — самая умная порода собак</h1>
                <img class="dog-breeds-4_image" src="Photo6.jpg" alt="Бордер-колли">
                <div class="dog-breeds-4_description">
                    Бордер-колли — порода, признанная самой умной среди собак. Выведена для пастушьей работы, обладает невероятной работоспособностью, энергией и желанием учиться. Требует серьезных физических и умственных нагрузок, иначе может развивать деструктивное поведение.
                    <div class="breed-characteristics">
                        <strong>Особенности породы:</strong>
                        <ul>
                            <li>Невероятно высокая обучаемость</li>
                            <li>Потребность в постоянной занятости</li>
                            <li>Отличные спортивные способности (аджилити, фрисби)</li>
                            <li>Сильный пастуший инстинкт (может "пасти" детей, других животных)</li>
              
