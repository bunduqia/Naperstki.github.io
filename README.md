Игра Наперстики 

<div class="Box-sc-g0xbh4-0 bDycpP"><img alt="fon.png" src="https://github.com/bunduqia/naperstki/blob/main/assets/www/fon.png?raw=true" data-hpc="true" class="Box-sc-g0xbh4-0 fzFXnm"></div>

Одолжи деньги ,выбери ставку, 
посмотри где шарик, и рискуй

перед каждым риском ты должен знать где шарик

удачи ,в игре есть скрытые имоции у девушки.
еле заметные что с продолжительной игрой
создает впечатление что она живая.

<html lang="en"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Наперстки</title>
    <meta name="description" content="A template for HTML and CSS. All images are located in the 'assets/www' folder.">
    <meta name="keywords" content="html, css, fonts">
    <meta name="author" content="kritikans">
    <meta name="version" content="1.0.0">
    <meta name="license" content="MIT">
    <link rel="stylesheet" href="assets/fonts/fonts.css">
    <style>
        /* Запретить масштабирование на мобильных устройствах */
        @viewport {
            zoom: 1;
            width: device-width;
            initial-scale: 1;
            maximum-scale: 1;
            user-scalable: no;
        }

        /* Используем фиксированные размеры для элементов */
        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .container {
            width: 100vw;  /* Используем 100% от ширины экрана */
            height: 100vh; /* Используем 100% от высоты экрана */
            max-width: 100%;
            max-height: 100%;
            position: relative;
        }

        .game-interface {
            width: 100%;
            height: 100%;
            font-size: 16px;  /* Зафиксированный размер шрифта */
            overflow: hidden;
        }

        button, .control {
            font-size: 16px;
            width: auto;  /* Размер кнопок не изменяется */
            height: auto; /* Размеры элементов управления фиксированы */
        }

        html, body {
            width: 100%;
            height: 100%;
            padding: 0;
            margin: 0;
            font-family: Arial, sans-serif;
            background: url('assets/www/fon.png') no-repeat center center fixed;
            background-size: cover;
            background-attachment: fixed;
            overflow: auto;
            position: relative;
            transition: background-image 0.5s ease-in-out;
            touch-action: manipulation;
            -ms-content-zooming: none;
            -ms-touch-action: manipulation;
            -ms-user-select: none;
            -webkit-user-select: none;
            -webkit-touch-callout: none;
            -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
            -webkit-text-size-adjust: 100%;
            -webkit-user-drag: none;
            -webkit-user-modify: read-only;
            -webkit-user-select: none;
            -webkit-user-zoom: none;
            -webkit-user-zoom: 1;
            -webkit-user-zoom: fixed;
            -webkit-user-zoom: 1.0;
            -webkit-user-zoom: 100%;
        }

        body {
            padding-top: 5px;
        }

        body::after {
            content: "";
            position: fixed;
            top: 80%;
            bottom: 10%;
            left: 50%;
            transform: translateX(-50%);
            width: 450px;
            height: fixed;
            max-height: 65px;
            filter: blur(10px);
            border-radius: 50%;
            z-index: -1;
            pointer-events: none;
        }

        #layers {
            position: relative;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .cloud {
            overflow: hidden;
            position: fixed;
            width: 100%;
            height: 100%;
            opacity: 0.5;
            z-index: 1;
            filter: blur(30px);
            pointer-events: none; /* Пропускаем клики */
        }

        .cloud img {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none; /* Дополнительно на случай вложенных событий */
        }

        .cloud1 {
            animation: animCloud 100s infinite linear;
        }

        .cloud2 {
            animation: animCloud 40s infinite linear;
        }

        .cloud3 {
            animation: animCloud 60s infinite linear;
        }

        .cloud4 {
            animation: animCloud 80s infinite linear;
        }

        @keyframes animCloud {
            from {
                transform: translateX(100%);
            }
            to {
                transform: translateX(-100%);
            }
        }

        .play-button, .button, .arrow-button, .exit-button, #feedbackButton, #submitReview {
            padding: 10px 20px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            color: white;
            background-image: linear-gradient(180deg, #41c6ff, #1a64fc), linear-gradient(180deg, #79cdfd, #1a64fc);
            box-shadow: 0 0 20px 0 #3a7cffab;
            transition: background-image 0.3s ease, box-shadow 0.3s ease;
        }

        .play-button:hover, .button:hover, .arrow-button:hover, .exit-button:hover, #feedbackButton:hover, #submitReview:hover {
            background-color: #0056b3;
            box-shadow: 0 0 2px rgba(255, 255, 0, 0.6);
        }

        .play-button:active, .button:active, .arrow-button:active, .exit-button:active, #feedbackButton:active, #submitReview:active {
            transform: translateY(0);
            box-shadow: none;
        }

        #fullscreenAlert {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            justify-content: center;
            align-items: center;
            flex-direction: column;
            z-index: 1000;
        }

        #gif {
            max-width: 100%;
            max-height: 100%;
        }

        #timer {
            margin-top: 20px;
            font-size: 24px;
            color: white;
        }

        .box {
            position: fixed;
            top: 10px;
            left: 17px;
            width: 800px;
            height: 600px;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            background-color: transparent;
            border: none;
        }

        #buttonContainer {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100%;
            height: auto;
            background-color: transparent;
            padding: 20px;
            box-sizing: border-box;
        }

        #betButton, #startButton, #confirmButton, #resetButton {
            width: 100px;
            height: 40px;
            margin: 0 10px;
            padding: 10px 20px;
            background-image: linear-gradient(180deg, #41c6ff, #1a64fc), linear-gradient(180deg, #79cdfd, #1a64fc);
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            transform: translateX(40px);
            box-shadow: 0 0 20px 0 #3a7cffab;
            transition: background-color 0.3s, box-shadow 0.3s ease;
        }

        #betButton:hover, #startButton:hover, #confirmButton:hover, #resetButton:hover {
            box-shadow: 0 0 30px 5px #3a7cff;
            transform: translateX(40px) scale(1.02);
        }

        #betButton {
            background-color: #007bff;
            transition: background-color 0.3s;
        }

        #betButton:hover {
            background-color: #007bff;
        }

        #startButton, #confirmButton {
            display: none;
            box-shadow: 0 0 10px rgba(255, 255, 0, 0.2);
        }

        #resetButton {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 100px;
            height: 40px;
            margin: 0 10px;
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            box-shadow: 0 0 2px rgba(255, 255, 0, 0.6);
            transition: background-color 0.3s, box-shadow 0.3s;
        }

        #resetButton.highlight {
            animation: highlightButton 2s infinite;
            box-shadow: 0 0 10px rgba(244, 244, 0, 0.6);
        }

        #notification {
            display: none;
            position: absolute;
            top: 20%;
            margin-left: 125px;
            left: 50%;
            opacity: 0.5;
            height: auto;
            min-width: 100px; /* Минимальная ширина */
            max-width: 300px; /* Максимальная ширина */
            transform: translateX(-50%);
            background-color: rgba(255, 255, 255, 0.5);
            color: #000000;
            padding: 15px 20px; /* Уменьшим padding для коротких текстов */
            border-radius: 50px;
            z-index: 10000;
            font-size: 22px;
            white-space: nowrap; /* Текст в одну строку */
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(8px);
            border: 4px solid transparent;
            background-image: linear-gradient(to right, #ffffff, #f0f0f0, #d0d0d0);
            background-origin: border-box;
            transition: box-shadow 0.3s ease, background-color 0.3s ease, background-image 0.3s ease;
            font-family: 'segoeprint';
            font-weight: bold;
            text-align: center;
            word-wrap: break-word; /* Перенос слов, если текст длинный */
        }

        #notification span {
            text-shadow: 1px 1px 3px rgba(255, 255, 255, 0.9);
            color: #000000;
        }

        #notification:hover {
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.3);
            background-color: rgba(255, 255, 255, 1);
            background-image: linear-gradient(to right, #ffffff, #f0f0f0, #a0a0a0);
        }

        #circle {
            margin-top: 30px;
            opacity: 0.5;
            display: block;
            position: fixed;
            top: calc(20% + 60px);
            left: calc(50% - 60px);
            width: 10px;
            height: 12px;
            background-color: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            z-index: 1000;
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.2);
            backdrop-filter: blur(8px);
            border: 4px solid transparent;
            background-image: linear-gradient(to right, #ffffff, #f0f0f0, #d0d0d0);
            background-origin: border-box;
            transition: box-shadow 0.3s ease, background-color 0.3s ease, background-image 0.3s ease;
        }

        #circle:hover {
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.3);
            background-color: rgba(255, 255, 255, 1);
            background-image: linear-gradient(to right, #ffffff, #f0f0f0, #a0a0a0);
        }

        .hidden {
            display: none !important;
        }

        #feedbackButton {
            position: fixed;
            bottom: 30px;
            left: 20px;
            padding: 10px 20px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-size: 16px;
            color: white;
            background-image: linear-gradient(180deg, #41c6ff, #1a64fc), linear-gradient(180deg, #79cdfd, #1a64fc);
            box-shadow: 0 0 20px 0 #3a7cffab;
            transition: background-image 0.3s ease, box-shadow 0.3s ease;
        }

        #feedbackButton:hover {
            background-color: #0056b3;
            box-shadow: 0 0 2px rgba(255, 255, 0, 0.6);
        }

        #feedbackModal {
            display: none;
            position: fixed;
            top: 50%;
            left: 5%;
            right: 5%;
            transform: translate(0, -50%);
            background-color: rgba(244, 244, 244, 0.95);
            padding: 12.5px;
            border-radius: 6.25px;
            box-shadow: 0 0 25px rgba(0, 0, 0, 0.9);
            z-index: 1000;
            max-width: 2160px;
            text-align: center;
            transition: width 0.5s ease-in-out;
        }

        #feedbackModal.shrink {
            left: 50%;
            right: 100%;
            width: 100%;
            transform: translate(-50%, -50%);
        }

        #closeModal {
            position: absolute;
            top: -28.125px;
            right: -21.875px;
            background: none;
            border: none;
            font-size: 18.75px;
            font-weight: bold;
            cursor: pointer;
            color: #B22222;
            transition: color 0.3s, text-shadow 0.3s;
            z-index: 2;
        }

        #closeModal::before {
            content: '×';
            position: absolute;
            top: -13.75px;
            right: -2px;
            font-size: 50px;
            color: white;
            z-index: -1;
            filter: blur(1.875px);
        }

        #closeModal:hover {
            color: #FF6347;
            text-shadow: 0 0 6.25px rgba(255, 99, 71, 0.8), 0 0 12.5px rgba(255, 99, 71, 0.6), 0 0 18.75px rgba(255, 99, 71, 0.4);
        }

        .stars {
            color: #ffffff;
            display: flex;
            justify-content: center;
            gap: 15px;
            margin-bottom: 30px;
            position: relative;
        }

        .stars::before {
            content: '★★★★★';
            font-size: 60px;
            position: absolute;
            top: -12.5px;
            left: 50%;
            transform: translateX(-50%) scaleX(1.05);
            color: #ffffff;
            z-index: -1;
            opacity: 0.999;
            filter: blur(0px);
        }

        .stars span {
            font-size: 45px;
            cursor: pointer;
            color: #ffffff;
            transition: color 0.3s;
        }

        .stars span.active {
            color: #FFFF00;
        }

        #reviewText {
            width: 93%;
            height: 100px;
            padding: 10px;
            border: 2px solid #ccc;
            border-radius: 5px;
            margin-bottom: 20px;
            resize: none;
            background-color: rgba(255, 255, 255, 0.9);
            box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.6);
        }

        #reviewsChat {
            position: relative;
            left: 50%;
            transform: translateX(-50%);
            margin-left: 0;
            margin-right: 0;
            width: 93%;
            height: 100px;
            overflow-y: auto;
            border: 2px solid #ccc;
            border-radius: 5px;
            padding: 10px;
            background-color: rgba(249, 249, 249, 0.9);
            text-align: left;
            box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.6);
        }

        #submitReview {
            margin-top: 15px;
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            transform: translateX(0px) scale(1.1);
            background-image: linear-gradient(180deg, #41c6ff, #1a64fc), linear-gradient(180deg, #79cdfd, #1a64fc);
            box-shadow: 0 0 20px 0 #3a7cffab;
            transition: background-image 0.3s ease, box-shadow 0.3s ease;
        }

        #submitReview:hover {
            background-color: #0056b3;
        }

        #muteButton {
            position: fixed;
            top: 1px;
            right: 1px;
            background: none;
            border: none;
            border-radius: 30px;
            padding: 0;
            display: inline-block;
        }

        #muteButton img {
            width: 65px;
            height: 65px;
            display: block;
            margin: 0;
        }

        #muteButton:hover img {
            opacity: 0.99;
        }

        .buttons {
            position: fixed;
            bottom: 80px;
            left: 53%;
            transform: translateX(-50%);
            display: flex;
            gap: 2px;
            box-shadow: 0 0 1px rgba(255, 255, 0, 0.6);
            margin-left: -50px;
            padding: 0;
        }

        .button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #28a745;
            color: white;
            gap: 2px;
            transition: background-color 0.01s;
            box-shadow: 0 0 2px rgba(255, 255, 0, 0.6);
            margin: 0 9px;
        }

        .button:hover {
            background-color: #666;
        }

        .score-bet {
            position: fixed;
            top: 10%;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            align-items: center;
            gap: 2vw;
            font-size: 10px;
            color: white;
        }

        .score-bet .button {
            width: 150px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            font-size: 18px;
            padding: 10px;
            border-radius: 10px;
            background-image: linear-gradient(180deg, #41c6ff, #1a64fc), linear-gradient(180deg, #79cdfd, #1a64fc);
            box-shadow: 0 0 20px 0 #3a7cffab;
            color: white;
            cursor: pointer;
            transition: background-image 0.3s ease, box-shadow 0.3s ease;
        }

        .score-bet .button:hover {
            box-shadow: 0 0 4px 0 #3a7cff;
        }

        .bet-input-wrapper {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 2px;
        }

        .bet-input {
            font-weight: bold;
            background-color: white !important;
            color: #1a64fc;
            box-shadow: 0 0 4px 0 #0000ff;
            text-align: center;
            font-size: 20px;
            padding: 7px;
            width: 85px;
            border: 2px solid #1a64fc;
            border-radius: 15px;
            outline: none;
            gap: 2px;
            background-image: none;
            opacity: 1;
        }

        .bet-input::placeholder {
            color: #1a64fc;
            opacity: 1;
        }

        input::placeholder {
            color: #1a64fc !important;
            opacity: 1;
        }

        .bet-input::placeholder {
            color: rgba(0, 0, 0, 0.5);
            opacity: 1;
        }

        .bet-input:focus {
            box-shadow: 0 0 25px 0 #1a64fc;
        }

        .balance-anim {
            font-size: 20px;
            font-weight: bold;
            color: #ff0;
            animation: increaseBalance 3s linear;
            box-shadow: 0 0 2px rgba(255, 255, 0, 1.1);
        }

        .exit-button {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 40px;
            height: 40px;
            padding: 0;
            border: none;
            border-radius: 50%;
            cursor: pointer;
            font-size: 16px;
            color: white;
            box-shadow: 0 0 2px rgba(255, 255, 0, 0.2);
            background-image: linear-gradient(180deg, #41c6ff, #1a64fc), linear-gradient(180deg, #79cdfd, #1a64fc);
            transition: background-image 0.3s ease, box-shadow 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .exit-button:hover {
            background-image: linear-gradient(180deg, #b300ff, #8a2be2);
            box-shadow: 0 0 2px rgba(255, 255, 0, 0.6);
        }

        .exit-button:active {
            transform: translateY(0);
            box-shadow: 0 0 20px 0 #3a7cffab;
        }

        @keyframes increaseBalance {
            0% {
                transform: scale(0.1);
            }
            100% {
                transform: scale(1.1);
            }
        }

        @keyframes highlightButton {
            0% {
                box-shadow: 0 0 10px 2px rgba(255, 255, 0, 0.8);
                transform: scale(1);
            }
            50% {
                box-shadow: 0 0 20px 4px rgba(255, 255, 0, 1);
                transform: scale(1.05);
            }
            100% {
                box-shadow: 0 0 10px 2px rgba(255, 255, 0, 0.8);
                transform: scale(1);
            }
        }

        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            background-color: #f4f4f4;
            color: #333;
        }

        header {
            background-color: #007bff;
            padding: 10px 20px;
            color: white;
            text-align: center;
        }

        main {
            padding: 20px;
        }

        footer {
            background-color: #222;
            color: white;
            text-align: center;
            padding: 10px;
            position: fixed;
            bottom: 0;
            width: 100%;
        }

        h1, h2 {
            margin: 10px 0;
        }

        a {
            text-decoration: none;
            color: #007bff;
        }

        a:hover {
            text-decoration: underline;
        }

        .container {
            max-width: 768px;
            margin: 0 auto;
            padding: 0 15px;
        }

        .row {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
        }

        .col {
            flex: 1;
            min-width: 250px;
        }

        @media (max-width: 480px) {
            header {
                padding: 15px 10px;
                font-size: 16px;
            }
            main {
                padding: 15px;
            }
            .container {
                padding: 0 10px;
            }
            .row {
                flex-direction: column;
                align-items: center;
            }
            .col {
                width: 100%;
                max-width: 100%;
                margin-bottom: 20px;
            }
            footer {
                position: relative;
                bottom: unset;
            }
        }

        @media (max-width: 250px) {
            header {
                font-size: 14px;
            }
            footer {
                font-size: 12px;
            }
            .container {
                padding: 0 5px;
            }
            .row {
                gap: 15px;
            }
            .col {
                font-size: 14px;
            }
        }

        .cup {
            margin-top: 27px;
            position: absolute;
            width: 40px;
            height: 40px;
            margin-left: 5px;
            background-image: url('assets/www/stak.png');
            background-size: cover;
            background-position: center;
            cursor: pointer;
            transition: transform 0.1s, top 0.1s, left 0.1s;
            transform: translate(-50%, -50%);
            border-radius: 5px;
            opacity: 0.95;
        }

        .cup:hover {
            transform: translate(-50%, -50%) scale(1.15);
        }

        :root {
            --ball-size: 14px;
            --ball-color: #ffcc00;
            --highlight-color: rgba(255, 255, 255, 0.8);
            --shadow-color: rgba(0, 0, 0, 0.3);
        }

        .ball {
            margin-left: -1.5px;
            margin-top: 30px;
            display: none;
            position: absolute;
            width: var(--ball-size);
            height: var(--ball-size);
            background: var(--ball-color);
            border-radius: 50%;
            box-shadow: 0 2px 4px var(--shadow-color);
            filter: drop-shadow(0 3px 3px rgba(0, 0, 0, 0.4));
        }

        .ball::before {
            content: '';
            position: absolute;
            top: 15%;
            width: 30%;
            height: 30%;
            background: radial-gradient(circle at 50% 50%, rgba(255, 255, 255, 0.9) 1%, rgba(255, 255, 255, 0) 7%);
            border-radius: 50%;
            transform: rotate(45deg);
        }

        .ball::after {
            content: '';
            position: absolute;
            bottom: -4.6px;
            width: 2px;
            height: 6.6px;
            background: radial-gradient(ellipse at center, var(--shadow-color) 30%, transparent 70%);
            transform: translateX(-50%);
            z-index: -1;
        }
    </style>
</head>
<body style="transform: scale(0.75); transform-origin: 0px 0px; width: 133.333%; height: 133.333%;">
<button id="exit-button" style="position: fixed; bottom: 25px; right: 25px; width: 25px; height: 25px; background: transparent; border: none; cursor: pointer;"></button>
<div class="cloud">
    <img src="assets/www/cloud01.png" alt="" class="cloud1">
    <img src="assets/www/cloud02.png" alt="" class="cloud2">
    <img src="assets/www/cloud03.png" alt="" class="cloud3">
    <img src="assets/www/cloud04.png" alt="" class="cloud4">
</div>
<div id="layers">
    <div class="cup" data-id="1" style="left: 771px; top: 432px;"></div>
    <div class="cup" data-id="2" style="left: 836px; top: 432px;"></div>
    <div class="cup" data-id="3" style="left: 901px; top: 432px;"></div>
    <div class="ball"></div>
    <div id="circle" style="display: none;"></div>
    <div id="notification" style="display: none; width: auto; height: auto; left: calc(50% - 140.5px);">одолжи бабки и начнём</div>
    <div class="score-bet">
        <button class="button" id="scoreButton">Где бабки ?</button>
        <div class="bet-input-wrapper">
            <label for="betInput"></label><input type="number" id="betInput" class="bet-input" placeholder="bet 0" min="1" max="1000">
        </div>
    </div>
    <div class="buttons">
        <button class="button" id="betButton">bet</button>
        <button class="button" id="startButton">шарик</button>
        <button class="button" id="confirmButton" disabled="">риск</button>
        <button class="button" id="resetButton">одолжить</button>
    </div>
    <audio id="sound50" src="assets/www/33.mp3" auto="" loop=""></audio>
    <button id="feedbackButton">Отзыв</button>
    <div class="buttons2">
        <button class="exit-button">
            <svg xmlns="" width="30" height="30" viewBox="0 0 26 26" fill="none">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M10.5162 2.60938C9.75 3.28862 9.75 4.53109 9.75 7.01605V18.9839C9.75 21.4688 9.75 22.7113 10.5162 23.3905C11.2824 24.0698 12.4535 23.8655 14.7957 23.4569L17.3186 23.017C19.9126 22.5645 21.2096 22.3383 21.9799 21.3868C22.75 20.4354 22.75 19.0594 22.75 16.3073V9.69266C22.75 6.94056 22.75 5.56452 21.9799 4.61307C21.2096 3.66161 19.9126 3.4354 17.3186 2.98296L14.7957 2.54293C12.4535 2.1344 11.2824 1.93014 10.5162 2.60938ZM13 11.0159C13.4487 11.0159 13.8125 11.3966 13.8125 11.8662V14.1337C13.8125 14.6033 13.4487 14.984 13 14.984C12.5513 14.984 12.1875 14.6033 12.1875 14.1337V11.8662C12.1875 11.3966 12.5513 11.0159 13 11.0159Z" fill="white"></path>
                <path d="M8.1761 4.875C5.9463 4.87825 4.78399 4.92728 4.04325 5.66802C3.25 6.46127 3.25 7.73799 3.25 10.2914V15.7081C3.25 18.2615 3.25 19.5382 4.04325 20.3316C4.78399 21.0722 5.9463 21.1213 8.1761 21.1246C8.12484 20.4493 8.12491 19.6687 8.12501 18.8249V7.17459C8.12491 6.33087 8.12484 5.55024 8.1761 4.875Z" fill="white"></path>
            </svg>
        </button>
        <div id="feedbackModal">
            <button id="closeModal">✕</button>
            <div class="stars">
                <span data-value="1">★</span>
                <span data-value="2">★</span>
                <span data-value="3">★</span>
                <span data-value="4">★</span>
                <span data-value="5">★</span>
            </div>
            <label for="reviewText"></label><textarea id="reviewText" placeholder="Пиши ник и отзыв..."></textarea>
            <div id="reviewsChat"></div>
            <button id="submitReview">Отправить</button>
        </div>
    </div>
    <a href="#" id="muteButton"><img src="assets/www/on.png" alt="Mute" id="muteIcon"></a>
</div>
<button id="exit-button" style="position: fixed; bottom: 25px; right: 25px; width: 25px; height: 25px; background: transparent; border: none; cursor: pointer;"></button>
<script>
    window.addEventListener("resize", function() {
        // Получение нового размера экрана
        const width = window.innerWidth;
        const height = window.innerHeight;

        // Переустановить размеры контейнера
        document.querySelector('.container').style.width = `${width}px`;
        document.querySelector('.container').style.height = `${height}px`;
    });

    document.addEventListener('wheel', function(event) {
        if (event.ctrlKey) {
            event.preventDefault();
        }
    }, { passive: false });

    const NotificationManager = (() => {
        const notificationElement = document.getElementById('notification');
        const circleElement = document.getElementById('circle');
        let activeTimeouts = [];

        const clearActiveTimeouts = () => {
            activeTimeouts.forEach(clearTimeout);
            activeTimeouts = [];
        };

        const showNotification = (message, duration = 1500) => {
            clearActiveTimeouts();
            circleElement.style.display = 'none';
            notificationElement.style.display = 'none';

            // Устанавливаем текст уведомления
            notificationElement.textContent = message;

            // Автоматически подстраиваем ширину и высоту
            notificationElement.style.width = 'auto';
            notificationElement.style.height = 'auto';

            // Показываем уведомление
            notificationElement.style.display = 'block';

            // Центрируем уведомление
            const notificationWidth = notificationElement.offsetWidth;
            notificationElement.style.left = `calc(50% - ${notificationWidth / 2}px)`;

            // Скрываем уведомление через указанное время
            const notificationTimeout = setTimeout(() => {
                notificationElement.style.display = 'none';
            }, duration);

            activeTimeouts.push(notificationTimeout);
        };

        return { showNotification };
    })();

    window.onload = () => {
        enterFullscreen();
        NotificationManager.showNotification("одолжи бабки и начнём", 3200);
    };

    function enterFullscreen() {
        const element = document.documentElement;
        if (element.requestFullscreen) {
            element.requestFullscreen();
        } else if (element.mozRequestFullScreen) {
            element.mozRequestFullScreen();
        } else if (element.webkitRequestFullscreen) {
            element.webkitRequestFullscreen();
        } else if (element.msRequestFullscreen) {
            element.msRequestFullscreen();
        }
    }

    function exitFullscreen() {
        if (document.exitFullscreen) {
            document.exitFullscreen();
        } else if (document.mozCancelFullScreen) {
            document.mozCancelFullScreen();
        } else if (document.webkitExitFullscreen) {
            document.webkitExitFullscreen();
        } else if (document.msExitFullscreen) {
            document.msExitFullscreen();
        }
    }

    document.addEventListener('fullscreenchange', () => {
        if (document.fullscreenElement) {
            document.body.style.overflow = 'hidden';
            document.body.style.marginTop = '0';
            document.body.style.marginBottom = '0';
        } else {
            document.body.style.overflow = '';
            document.body.style.marginTop = '';
            document.body.style.marginBottom = '';
        }
    });

    let isNotificationActive = false;
    document.querySelectorAll('button').forEach(button => {
        button.addEventListener('click', () => {
            if (isNotificationActive) {
                const notificationElement = document.getElementById('notification');
                if (notificationElement) {
                    notificationElement.style.display = 'none';
                }
                isNotificationActive = false;
            }
        });
    });

    document.getElementById('scoreButton').addEventListener('click', () => {
        const showNotifications = async () => {
            const messages = ["щас скажу", "казик с лицензией", "вывод без верификации", "много бонусов", "турниров", "куча фри-спинов", "мгновенный вывод", "PIASTRIX, USDT", "карты Мир"];
            isNotificationActive = true;
            await showNotificationWithDelay(messages[0], 1000);
            if (!isNotificationActive) return;
            const qrCodeImage = document.createElement('img');
            qrCodeImage.src = 'assets/www/qrcode2.png';
            qrCodeImage.style.position = 'fixed';
            qrCodeImage.style.top = '50%';
            qrCodeImage.style.left = '50%';
            qrCodeImage.style.transform = 'translate(-50%, -50%)';
            qrCodeImage.style.zIndex = '1';
            document.body.appendChild(qrCodeImage);
            for (let i = 1; i < messages.length; i++) {
                await showNotificationWithDelay(messages[i], 2000);
                if (!isNotificationActive) break;
            }
            if (!isNotificationActive) {
                document.body.removeChild(qrCodeImage);
                return;
            }
            await sleep(100);
            document.body.removeChild(qrCodeImage);
            isNotificationActive = false;
        };

        const showNotificationWithDelay = (message, duration) => {
            return new Promise((resolve) => {
                if (!isNotificationActive) {
                    resolve();
                    return;
                }
                NotificationManager.showNotification(message, duration);
                setTimeout(resolve, duration);
            });
        };

        const sleep = (ms) => new Promise((resolve) => setTimeout(resolve, ms));
        showNotifications();
    });

    const betButton = document.getElementById('betButton');
    const betValues = [10, 20, 50, 100, 200, 500];
    let betIndex = 0;
    betButton.addEventListener('click', () => {
        betInput.value = betValues[betIndex];
        betIndex = (betIndex + 1) % betValues.length;
        NotificationManager.showNotification(`bet ${betInput.value} ₽`, 1200);
    });

    let fullscreenAlert = document.getElementById('fullscreenAlert');
    let timerDisplay = document.getElementById('timer');
    let timerDuration = 30;

    function showAlert() {
        if (fullscreenAlert.style.display !== 'flex') {
            fullscreenAlert.style.display = 'flex';
            startTimer();
        }
    }

    function startTimer() {
        let timeLeft = timerDuration;
        timerDisplay.textContent = timeLeft;
        let timerInterval = setInterval(() => {
            timeLeft--;
            timerDisplay.textContent = timeLeft;
            if (timeLeft <= 0) {
                clearInterval(timerInterval);
                fullscreenAlert.style.display = 'none';
            }
        }, 1000);
    }

    setInterval(showAlert, 1000);

    const muteButton = document.getElementById('muteButton');
    const muteIcon = document.getElementById('muteIcon');
    const sound50 = document.getElementById('sound50');
    let isMuted = false;
    muteButton.addEventListener('click', () => {
        isMuted = !isMuted;
        sound50.muted = isMuted;
        muteIcon.src = isMuted ? 'assets/www/off.png' : 'assets/www/on.png';
        NotificationManager.showNotification(isMuted ? "втихую решил" : "станцуем", 1500);
    });

    const feedbackButton = document.getElementById('feedbackButton');
    const feedbackModal = document.getElementById('feedbackModal');
    const closeModal = document.getElementById('closeModal');
    const stars = document.querySelectorAll('.stars span');
    const reviewText = document.getElementById('reviewText');
    const reviewsChat = document.getElementById('reviewsChat');
    const submitReview = document.getElementById('submitReview');
    let selectedRating = 0;

    feedbackButton.addEventListener('click', () => {
        feedbackModal.style.display = 'block';
    });

    closeModal.addEventListener('click', () => {
        feedbackModal.style.display = 'none';
    });

    stars.forEach(star => {
        star.addEventListener('click', () => {
            selectedRating = star.getAttribute('data-value');
            stars.forEach(s => s.classList.remove('active'));
            for (let i = 0; i < selectedRating; i++) {
                stars[i].classList.add('active');
            }
        });
    });

    submitReview.addEventListener('click', () => {
        const review = reviewText.value.trim();
        if (review && selectedRating > 0) {
            const reviewElement = document.createElement('div');
            reviewElement.innerHTML = `<strong>${selectedRating} звезд:</strong> ${review}`;
            reviewsChat.appendChild(reviewElement);
            reviewText.value = '';
            selectedRating = 0;
            stars.forEach(s => s.classList.remove('active'));
            NotificationManager.showNotification("Спасибо за ваш отзыв!");
        } else {
            NotificationManager.showNotification("звезду не нажал ≧◠‿◠≦✌.", 1500);
        }
    });

    window.addEventListener('click', (event) => {
        if (event.target === feedbackModal) {
            feedbackModal.style.display = 'none';
        }
    });

    const cups = [{ id: 1, x: 0, y: 0 }, { id: 2, x: 0, y: 0 }, { id: 3, x: 0, y: 0 }];
    let ballUnder = 0;
    let gameOver = false;
    let gameRunning = false;
    let playerBalance = 0;
    let currentBet = 0;
    let canSelectCup = false;
    const startButton = document.getElementById("startButton");
    const confirmButton = document.getElementById("confirmButton");
    const resetButton = document.getElementById("resetButton");
    const notification = document.getElementById("notification");
    const scoreButton = document.getElementById("scoreButton");
    const betInput = document.getElementById("betInput");
    let betButtonClicked = false;
    let startButtonClicked = false;

    betButton.addEventListener("click", () => {
        betButtonClicked = true;
    });

    startButton.addEventListener("click", () => {
        startButtonClicked = true;
        NotificationManager.showNotification("запомнил где шарик", 2000);
    });

    confirmButton.addEventListener("click", () => {
        if (!betButtonClicked || !startButtonClicked) {
            NotificationManager.showNotification("делай ставку", 1500);
        } else {
            confirmStart();
        }
    });

    // Функция для обновления позиций стаканов
    const updatePositions = () => {
        const containerWidth = layers.offsetWidth;
        const containerHeight = layers.offsetHeight;
        const cupWidth = 35;
        const gap = 30;
        const startX = (containerWidth - (cups.length * cupWidth + (cups.length - 1) * gap)) / 2;
        const startY = containerHeight / 2;
        cups.forEach((cup, index) => {
            cup.x = startX + index * (cupWidth + gap);
            cup.y = startY;
            const cupElement = document.querySelector(`.cup[data-id="${cup.id}"]`);
            cupElement.style.left = `${cup.x}px`;
            cupElement.style.top = `${cup.y}px`;
        });
    };

    let currentMove = 3;
    const ballPositions = [3, 2, 1, 2, 3, 1, 2, 3, 1, 3, 2, 1, 3, 1, 2];

    const shuffleCups = () => {
        return new Promise((resolve) => {
            canSelectCup = false;
            const ball = document.querySelector('.ball');
            ball.style.display = 'none';
            setTimeout(async () => {
                let iterations = 2;
                const rotationDuration = 150;
                const pauseDuration = 250;
                const pairs = [[cups[0], cups[1]], [cups[1], cups[2]], [cups[0], cups[2]]];
                for (let i = 0; i < iterations; i++) {
                    for (let j = 0; j < pairs.length; j++) {
                        const [cup1, cup2] = pairs[j];
                        const center = { x: (cup1.x + cup2.x) / 2, y: (cup1.y + cup2.y) / 2 };
                        await rotatePairSmooth(cup1, cup2, center, 360, rotationDuration);
                        if (j < pairs.length - 1) {
                            await sleep(pauseDuration);
                        }
                    }
                }
                if (currentMove < 15) {
                    ballUnder = ballPositions[currentMove];
                } else {
                    const relativeMove = (currentMove - 15) % 14;
                    ballUnder = ballPositions[relativeMove + 1] || 1;
                }
                currentMove++;
                updatePositions();
                canSelectCup = true;
                NotificationManager.showNotification("какой наперсток ?", 1500);
                resolve();
            }, 500);
        });
    };

    const sleep = (ms) => new Promise((resolve) => setTimeout(resolve, ms));

    const rotatePairSmooth = (cup1, cup2, center, angle, duration) => {
        return new Promise((resolve) => {
            const startTime = performance.now();
            const startAngle = 0;
            const radiansDelta = (angle * Math.PI) / 180;
            const radius = Math.sqrt((cup1.x - center.x) ** 2 + (cup1.y - center.y) ** 2);
            const step = (currentTime) => {
                const elapsed = currentTime - startTime;
                const progress = Math.min(elapsed / duration, 1);
                const currentAngle = startAngle + radiansDelta * progress;
                cup1.x = center.x + radius * Math.cos(currentAngle);
                cup1.y = center.y + radius * Math.sin(currentAngle);
                cup2.x = center.x + radius * Math.cos(currentAngle + Math.PI);
                cup2.y = center.y + radius * Math.sin(currentAngle + Math.PI);
                const cupElement1 = document.querySelector(`.cup[data-id="${cup1.id}"]`);
                const cupElement2 = document.querySelector(`.cup[data-id="${cup2.id}"]`);
                if (cupElement1 && cupElement2) {
                    cupElement1.style.left = `${cup1.x}px`;
                    cupElement1.style.top = `${cup1.y}px`;
                    cupElement2.style.left = `${cup2.x}px`;
                    cupElement2.style.top = `${cup2.y}px`;
                }
                if (progress < 1) {
                    requestAnimationFrame(step);
                } else {
                    resolve();
                }
            };
            requestAnimationFrame(step);
        });
    };

    const preloadImages = (urls) => {
        const images = []; // Массив для хранения объектов Image

        urls.forEach(url => {
            const img = new Image();
            img.src = url;
            images.push(img); // Сохраняем объект Image в массиве, чтобы удерживать в памяти
        });

        return images; // Возвращаем массив изображений
    };

    preloadImages(['assets/www/fon.png', 'assets/www/fon2.png', 'assets/www/fon3.png']);

    const changeBackground = (imageUrl, duration) => {
        document.body.style.backgroundImage = `url('${imageUrl}')`;
        setTimeout(() => {
            document.body.style.backgroundImage = 'url("assets/www/fon.png")';
        }, duration);
    };

    handleClick = (id) => {
        if (!canSelectCup || gameOver) return;

        const cupElement = document.querySelector(`.cup[data-id="${id}"]`);
        const ball = document.querySelector('.ball');

        canSelectCup = false;

        if (cupElement.classList.contains('active')) return;

        const currentTop = parseInt(window.getComputedStyle(cupElement).top, 10);
        cupElement.style.top = `${currentTop - 35}px`;
        cupElement.classList.add('active');

        setTimeout(() => {
            if (id === ballUnder) {
                ball.style.left = `${cups[id - 1].x}px`;
                ball.style.top = `${cups[id - 1].y}px`;
                ball.style.display = 'block';
                document.body.style.backgroundImage = 'url("assets/www/fon.png")';
                changeBackground('assets/www/fon2.png', 700);
                setTimeout(() => {
                    ball.style.display = 'none';
                }, 500);
            } else {
                document.body.style.backgroundImage = 'url("assets/www/fon.png")';
                ball.style.display = 'none';
                changeBackground('assets/www/fon3.png', 700);
            }
        }, 200);

        setTimeout(() => {
            cupElement.style.top = `${currentTop}px`;
            cupElement.classList.remove('active');
        }, 700);

        window.addEventListener('resize', () => {
            updatePositions();
        });

        let difficultyLevel = 2;

        setTimeout(() => {
            if (id === ballUnder) {
                playerBalance += currentBet;
                scoreButton.textContent = `${playerBalance} ₽`;
                NotificationManager.showNotification(` + ${currentBet} ₽`, 1500);
            } else {
                playerBalance -= currentBet;
                scoreButton.textContent = `${playerBalance} ₽`;
                NotificationManager.showNotification(` - ${currentBet} ₽`, 1500);
            }
            gameOver = true;
            resetButton.disabled = false;
            startButton.disabled = false;
        }, 1000);
    };

    let difficultyLevel = 2;

    const startGame = () => {
        if (gameRunning) return;
        gameRunning = true;
        const maxCups = 3;
        ballUnder = Math.floor(Math.random() * maxCups) + 1;
        console.log(` №${ballUnder} (Уровень сложности: ${difficultyLevel})`);
        gameOver = false;
        resetButton.disabled = true;
        confirmButton.disabled = false;
        startButton.disabled = true;
        const ball = document.querySelector('.ball');
        ball.style.display = 'none';
        const cupWithBall = document.querySelector(`.cup[data-id="${ballUnder}"]`);
        if (cupWithBall) {
            const currentTop = parseInt(window.getComputedStyle(cupWithBall).top, 10);
            cupWithBall.style.top = `${currentTop - 30}px`;
            setTimeout(() => {
                ball.style.left = `${cups[ballUnder - 1].x}px`;
                ball.style.top = `${cups[ballUnder - 1].y}px`;
                ball.style.display = 'block';
                setTimeout(() => {
                    cupWithBall.style.top = `${currentTop}px`;
                    ball.style.display = 'none';
                    updatePositions();
                }, 625);
            }, 125);
        }
        if (difficultyLevel < 5) {
            difficultyLevel++;
        }
    };

    const confirmStart = async () => {
        const bet = parseInt(betInput.value);
        if (isNaN(bet) || bet <= 0 || bet > playerBalance) {
            NotificationManager.showNotification("делай ставку", 1500);
            return;
        }
        currentBet = bet;
        const ball = document.querySelector('.ball');
        ball.style.display = 'none';
        confirmButton.disabled = true;
        canSelectCup = false;
        await shuffleCups();
        cups.forEach((cup) => {
            const div = document.querySelector(`.cup[data-id="${cup.id}"]`);
            div.onclick = () => handleClick(cup.id);
        });
        canSelectCup = true;
        gameRunning = false;
    };

    const resetGame = () => {
        if (playerBalance <= 0) {
            NotificationManager.showNotification("Да кто тебе займет нищеброд.", 1500);
            updateUIAfterLoss();
        } else {
            playerBalance = 2000;
            scoreButton.textContent = `Баланс: ${playerBalance}`;
            betInput.value = '';
            NotificationManager.showNotification("нашел бабки сыграем", 1500);
            updateUIAfterLoss();
        }
    };

    const updateUIAfterLoss = () => {
        if (playerBalance <= 0) {
            betButton.style.display = 'none';
            startButton.style.display = 'none';
            confirmButton.style.display = 'none';
            resetButton.style.display = 'inline-block';
            resetButton.disabled = false;
        } else {
            betButton.style.display = 'inline-block';
            startButton.style.display = 'inline-block';
            confirmButton.style.display = 'inline-block';
            resetButton.style.display = 'none';
        }
    };

    const borrowMoney = () => {
        if (playerBalance === 0) {
            console.log('Playing sound');
            sound50.play();
            const borrowedAmount = Math.floor(Math.random() * 901) + 100;
            playerBalance += borrowedAmount;
            scoreButton.textContent = ` ${playerBalance}`;
            NotificationManager.showNotification(`ЗАНЯЛ ${playerBalance}`);
            updateUIAfterLoss();
        }
    };

    const updateBorrowButton = () => {
        if (playerBalance > 0) {
            resetButton.disabled = false;
            sound50.play();
        } else {
            resetButton.disabled = false;
            sound50.play();
        }
    };

    document.addEventListener('DOMContentLoaded', () => {
        const decrementButton = document.getElementById('decrement');
        const incrementButton = document.getElementById('increment');
        const betInput = document.getElementById('betInput');
        if (!decrementButton || !incrementButton || !betInput) {
            console.error("One or more elements not found. Check your HTML.");
            return;
        }
        const minBet = parseInt(betInput.getAttribute('min')) || 1;
        const maxBet = parseInt(betInput.getAttribute('max')) || 1000;
        decrementButton.addEventListener('click', () => {
            let currentValue = parseInt(betInput.value) || minBet;
            betInput.value = Math.max(minBet, currentValue - 1);
        });
        incrementButton.addEventListener('click', () => {
            let currentValue = parseInt(betInput.value) || minBet;
            betInput.value = Math.min(maxBet, currentValue + 1);
        });
        betInput.addEventListener('input', () => {
            let value = parseInt(betInput.value);
            if (isNaN(value) || value < minBet) {
                betInput.value = minBet;
            } else if (value > maxBet) {
                betInput.value = maxBet;
            }
        });
    });

    let initialScale = window.devicePixelRatio || 1;

    function adjustScale() {
        const currentScale = window.devicePixelRatio || 1;
        const scaleFactor = initialScale / currentScale;
        document.body.style.transform = `scale(${scaleFactor})`;
        document.body.style.transformOrigin = '0 0';
        document.body.style.width = `${100 / scaleFactor}%`;
        document.body.style.height = `${100 / scaleFactor}%`;
    }

    window.addEventListener('resize', adjustScale);
    window.addEventListener('DOMContentLoaded', adjustScale);

    resetButton.onclick = borrowMoney;
    startButton.onclick = startGame;
    confirmButton.onclick = confirmStart;

    updatePositions();

    document.querySelector('.exit-button').addEventListener('click', function () {
        if (window.AndroidInterface) {
            window.AndroidInterface.exitToHomeScreen();
        }
    });

    const ball = document.createElement('div');
    ball.className = 'ball';
    updatePositions();
    updateBorrowButton();

</script>


</body></html>
