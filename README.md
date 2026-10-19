<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Thecodedcharm 🍓</title>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Nunito:wght@400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --pink: #FFCED8;
            --soft-pink: #FFDDDD;
            --cream: #FFF4DE;
            --butter: #FFE8C4;
            --jam: #850E35;
            --rose: #D94F78;
            --white: #FFFDF9;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: "Nunito", sans-serif;
            color: var(--jam);
            background: var(--pink);
            overflow-x: hidden;
        }

        a {
            color: inherit;
            text-decoration: none;
        }

        button {
            font: inherit;
        }

        ::selection {
            background: var(--jam);
            color: white;
        }

        /* DREAMY BACKGROUND */

        .dreamy-sky {
            position: fixed;
            inset: 0;
            z-index: -2;
            overflow: hidden;
            pointer-events: none;
            background:
                radial-gradient(ellipse at 10% 20%, #fff2e7 0%, transparent 35%),
                radial-gradient(ellipse at 90% 30%, #ffb8cf 0%, transparent 35%),
                radial-gradient(ellipse at 50% 90%, #fff0d8 0%, transparent 45%),
                #FFCED8;
        }

        .dreamy-sky::before {
            content: "";
            position: absolute;
            inset: 0;
            opacity: 0.3;
            background-image: radial-gradient(#ffffff 1px, transparent 1px);
            background-size: 27px 27px;
        }

        .floating-world {
            position: fixed;
            inset: 0;
            z-index: 5;
            overflow: hidden;
            pointer-events: none;
        }

        .floaty {
            position: absolute;
            top: -60px;
            left: var(--left);
            font-size: var(--size);
            opacity: 0.8;
            animation: fall var(--duration) linear infinite;
            animation-delay: var(--delay);
        }

        @keyframes fall {
            0% {
                transform: translate3d(0, -50px, 0) rotate(0deg);
                opacity: 0;
            }

            10% {
                opacity: 0.85;
            }

            50% {
                transform: translate3d(45px, 50vh, 0) rotate(150deg);
            }

            90% {
                opacity: 0.8;
            }

            100% {
                transform: translate3d(-30px, 110vh, 0) rotate(330deg);
                opacity: 0;
            }
        }

        /* TINY DECORATIONS */

        .corner-note {
            position: absolute;
            top: 25px;
            font-family: "DM Serif Display", serif;
            font-style: italic;
            font-size: 14px;
            line-height: 1.8;
            opacity: 0.75;
        }

        .corner-note.left {
            left: 30px;
            transform: rotate(-8deg);
        }

        .corner-note.right {
            right: 30px;
            transform: rotate(8deg);
            text-align: right;
        }

        /* PAGE */

        .page {
            width: min(1100px, 92%);
            margin: auto;
            padding-bottom: 45px;
        }

        /* HERO */

        .hero {
            min-height: 570px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            padding: 85px 15px 65px;
        }

        .hero-flower {
            font-size: 48px;
            display: inline-block;
            animation: flowerDance 4s ease-in-out infinite;
        }

        @keyframes flowerDance {
            0%, 100% {
                transform: rotate(-12deg) translateY(0);
            }

            50% {
                transform: rotate(12deg) translateY(-12px);
            }
        }

        .eyebrow {
            margin-top: 18px;
            padding: 8px 17px;
            border: 1px solid #e7a1b1;
            background: #fff5edb8;
            border-radius: 50px;
            font-size: 12px;
            letter-spacing: 2px;
            text-transform: uppercase;
            font-weight: 800;
        }

        .hero h1 {
            font-family: "DM Serif Display", serif;
            font-size: clamp(55px, 9vw, 105px);
            font-weight: 400;
            line-height: 1.1;
            letter-spacing: -3px;
            margin-top: 15px;
            color: var(--jam);
            animation: appear 1s ease both;
        }

        .hero h1 span {
            font-style: italic;
            color: var(--rose);
        }

        .hero-description {
            max-width: 530px;
            margin-top: 20px;
            font-size: 17px;
            line-height: 1.9;
            color: #8d3451;
        }

        .hero-description strong {
            color: var(--jam);
        }

        .hero-buttons {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 28px;
        }

        .button {
            padding: 13px 22px;
            border: 1px solid var(--jam);
            border-radius: 50px;
            font-weight: 800;
            font-size: 13px;
            transition: transform 0.3s, box-shadow 0.3s, background 0.3s;
            cursor: pointer;
        }

        .button.primary {
            background: var(--jam);
            color: white;
        }

        .button.secondary {
            background: var(--cream);
        }

        .button:hover {
            transform: translateY(-5px) rotate(-2deg);
            box-shadow: 0 8px 0 #850e3520;
        }

        .hero-strawberry {
            position: absolute;
            font-size: 45px;
            animation: bob 4s ease-in-out infinite;
        }

        .hero-strawberry.one {
            top: 140px;
            left: 8%;
        }

        .hero-strawberry.two {
            bottom: 85px;
            right: 8%;
            animation-delay: -2s;
        }

        .hero-strawberry.three {
            top: 90px;
            right: 17%;
            font-size: 28px;
            animation-delay: -1s;
        }

        @keyframes bob {
            0%, 100% {
                transform: translateY(0) rotate(-10deg);
            }

            50% {
                transform: translateY(-18px) rotate(10deg);
            }
        }

        @keyframes appear {
            from {
                opacity: 0;
                transform: translateY(25px);
            }

            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* NAVIGATION */

        .navigation {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            padding: 0 0 55px;
        }

        .navigation a {
            padding: 10px 17px;
            background: #fff6ebc9;
            border: 1px solid #efb3c0;
            border-radius: 50px;
            font-size: 12px;
            font-weight: 800;
            transition: 0.3s;
        }

        .navigation a:hover {
            background: white;
            transform: translateY(-4px);
        }

        /* SECTIONS */

        .section {
            margin-bottom: 35px;
            scroll-margin-top: 25px;
        }

        .section-heading {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }

        .section-heading h2 {
            font-family: "DM Serif Display", serif;
            font-size: clamp(27px, 4vw, 36px);
            font-weight: 400;
        }

        .section-heading h2 span {
            color: var(--rose);
        }

        .tiny-label {
            font-size: 11px;
            letter-spacing: 1px;
            font-weight: 800;
            text-transform: uppercase;
            opacity: 0.65;
        }

        .paper {
            background: var(--cream);
            border: 1px solid #f4b8c5;
            border-radius: 25px;
            padding: 30px;
            box-shadow: 0 8px 0 #850e3509;
            position: relative;
            overflow: hidden;
        }

        .paper::after {
            content: "✿";
            position: absolute;
            right: 20px;
            bottom: 7px;
            color: #f0b5bf;
            font-size: 35px;
            opacity: 0.65;
            pointer-events: none;
        }

        /* ABOUT */

        .about-grid {
            display: grid;
            grid-template-columns: 1.4fr 1fr;
            gap: 25px;
            align-items: center;
        }

        .about-text {
            font-size: 15px;
            line-height: 2;
            max-width: 600px;
        }

        .about-text p + p {
            margin-top: 12px;
        }

        .signature {
            margin-top: 18px;
            font-family: "DM Serif Display", serif;
            font-style: italic;
            font-size: 20px;
            color: var(--rose);
        }

        .personality-card {
            background: #ffe1e5;
            padding: 22px;
            border: 1px dashed #df9eae;
            border-radius: 18px;
            transform: rotate(2deg);
        }

        .personality-card h3 {
            font-family: "DM Serif Display", serif;
            font-size: 22px;
            margin-bottom: 15px;
        }

        .personality-card p {
            margin: 11px 0;
            font-size: 13px;
        }

        /* SKILLS PATISSERIE */

        .bakery {
            background: var(--cream);
            border: 1px solid #f0b1bf;
            border-radius: 25px;
            padding: 30px;
            position: relative;
        }

        .bakery-title {
            width: fit-content;
            margin: -30px auto 25px;
            padding: 13px 35px;
            background: #ffc4d1;
            border: 1px solid #e89aaf;
            border-radius: 0 0 22px 22px;
            font-family: "DM Serif Display", serif;
            font-size: 23px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(6, minmax(0, 1fr));
            gap: 15px;
        }

        .skill {
            background: #fffaf0;
            border: 1px solid #f3c8c7;
            border-radius: 18px;
            padding: 18px 7px;
            text-align: center;
            transition: 0.35s;
            cursor: default;
        }

        .skill:hover {
            transform: translateY(-9px) rotate(3deg);
            background: #ffe5e8;
            box-shadow: 0 8px 0 #e8a4b450;
        }

        .skill-dessert {
            font-size: 38px;
            display: block;
            margin-bottom: 12px;
            animation: bob 4s ease-in-out infinite;
        }

        .skill:nth-child(even) .skill-dessert {
            animation-delay: -2s;
        }

        .skill-name {
            font-size: 12px;
            font-weight: 800;
        }

        /* PROJECTS */

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(2, minmax(0, 1fr));
            gap: 18px;
        }

        .project {
            background: var(--cream);
            border: 1px solid #efb7c2;
            border-radius: 22px;
            padding: 15px;
            transition: transform 0.35s, box-shadow 0.35s;
            position: relative;
            overflow: hidden;
        }

        .project:hover {
            transform: translateY(-7px);
            box-shadow: 0 12px 0 #a53c5815;
        }

        .project-art {
            height: 150px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 65px;
            position: relative;
            overflow: hidden;
            background: #ffdce4;
        }

        .project:nth-child(2) .project-art {
            background: #ffe7bd;
        }

        .project:nth-child(3) .project-art {
            background: #e9dfff;
        }

        .project:nth-child(4) .project-art {
            background: #ffe7d7;
        }

        .project-art::before,
        .project-art::after {
            position: absolute;
            font-size: 25px;
            opacity: 0.8;
        }

        .project-art::before {
            content: "✿";
            top: 10px;
            left: 15px;
            animation: flowerDance 5s infinite;
        }

        .project-art::after {
            content: "✧";
            bottom: 10px;
            right: 15px;
            animation: bob 3s infinite;
        }

        .project-art span {
            transition: transform 0.4s;
        }

        .project:hover .project-art span {
            transform: scale(1.2) rotate(-8deg);
        }

        .project h3 {
            margin-top: 17px;
            font-family: "DM Serif Display", serif;
            font-size: 23px;
            font-weight: 400;
        }

        .project p {
            font-size: 13px;
            line-height: 1.8;
            margin-top: 8px;
            color: #8b5361;
        }

        .project-tags {
            display: flex;
            gap: 7px;
            flex-wrap: wrap;
            margin-top: 13px;
        }

        .project-tags span {
            background: #ffd7df;
            padding: 5px 10px;
            border-radius: 50px;
            font-size: 10px;
            font-weight: 800;
        }

        .project-link {
            display: inline-block;
            margin-top: 15px;
            font-size: 12px;
            font-weight: 800;
            border-bottom: 1px solid var(--rose);
        }

        /* CODING GARDEN */

        .garden {
            background: var(--cream);
            border: 1px solid #efb7c2;
            border-radius: 25px;
            padding: 30px;
        }

        .garden-top {
            display: flex;
            justify-content: space-between;
            gap: 15px;
            flex-wrap: wrap;
            align-items: center;
            margin-bottom: 20px;
        }

        .garden-top h3 {
            font-family: "DM Serif Display", serif;
            font-size: 24px;
            font-weight: 400;
        }

        .garden-top p {
            font-size: 12px;
            opacity: 0.7;
            margin-top: 5px;
        }

        .garden-stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 12px;
        }

        .stat {
            background: #ffe2e5;
            border-radius: 15px;
            padding: 18px 10px;
            text-align: center;
        }

        .stat strong {
            display: block;
            font-family: "DM Serif Display", serif;
            font-size: 29px;
        }

        .stat span {
            font-size: 11px;
        }

        .garden-note {
            margin-top: 18px;
            background: #fff9ee;
            border: 1px dashed #e5a9b6;
            border-radius: 14px;
            padding: 15px;
            font-family: "DM Serif Display", serif;
            font-style: italic;
            text-align: center;
        }

        /* CONTACT */

        .contact {
            text-align: center;
            padding: 45px 20px;
            background: var(--jam);
            color: var(--cream);
            border-radius: 28px;
            position: relative;
            overflow: hidden;
        }

        .contact h2 {
            font-family: "DM Serif Display", serif;
            font-weight: 400;
            font-size: clamp(35px, 6vw, 52px);
        }

        .contact p {
            max-width: 440px;
            margin: 15px auto 25px;
            line-height: 1.9;
            font-size: 14px;
        }

        .contact .button {
            display: inline-block;
            background: var(--cream);
            color: var(--jam);
            border-color: var(--cream);
        }

        .contact-flower {
            position: absolute;
            font-size: 45px;
            opacity: 0.3;
        }

        .contact-flower.left {
            top: 10px;
            left: 20px;
        }

        .contact-flower.right {
            bottom: 5px;
            right: 20px;
        }

        /* FOOTER */

        footer {
            text-align: center;
            padding: 35px 10px 15px;
            font-size: 12px;
            line-height: 2;
        }

        footer .footer-flower {
            display: inline-block;
            animation: flowerDance 4s infinite;
        }

        /* RESPONSIVE */

        @media (max-width: 750px) {
            .hero {
                min-height: 500px;
            }

            .hero-strawberry.one {
                left: 2%;
            }

            .hero-strawberry.two {
                right: 2%;
            }

            .corner-note {
                display: none;
            }

            .about-grid {
                grid-template-columns: 1fr;
            }

            .skills-grid {
                grid-template-columns: repeat(3, minmax(0, 1fr));
            }

            .paper,
            .bakery,
            .garden {
                padding: 22px;
            }

            .bakery-title {
                margin-top: -22px;
            }
        }

        @media (max-width: 480px) {
            .page {
                width: 92%;
            }

            .hero {
                padding-top: 75px;
            }

            .hero h1 {
                letter-spacing: -2px;
            }

            .hero-description {
                font-size: 14px;
            }

            .projects-grid {
                grid-template-columns: 1fr;
            }

            .project-art {
                height: 170px;
            }

            .navigation {
                gap: 7px;
                padding-bottom: 40px;
            }

            .navigation a {
                padding: 9px 12px;
                font-size: 11px;
            }

            .garden-stats {
                grid-template-columns: 1fr;
            }

            .section-heading h2 {
                font-size: 27px;
            }
        }

        /* ACCESSIBILITY */

        @media (prefers-reduced-motion: reduce) {
            *,
            *::before,
            *::after {
                animation-duration: 0.01ms !important;
                animation-iteration-count: 1 !important;
                scroll-behavior: auto !important;
                transition-duration: 0.01ms !important;
            }
        }
    </style>
</head>

<body>

    <div class="dreamy-sky"></div>

    <div class="floating-world" id="floatingWorld"></div>

    <div class="corner-note left">
        small steps<br>
        build big dreams ♡
    </div>

    <div class="corner-note right">
        good things<br>
        take time ♡
    </div>

    <main class="page">

        <!-- HERO -->

        <section class="hero" id="home">

            <span class="hero-strawberry one">🍓</span>
            <span class="hero-strawberry two">🍓</span>
            <span class="hero-strawberry three">✧</span>

            <div class="hero-flower">🌷</div>

            <div class="eyebrow">
                ✿ Developer · Dreamer · Creator ✿
            </div>

            <h1>
                the<span>coded</span>charm
            </h1>

            <p class="hero-description">
                Hi, I'm Khushi! ♡ A creative computer science student
                turning <strong>little ideas into beautiful digital experiences.</strong>
                Welcome to my tiny corner of the internet.
            </p>

            <div class="hero-buttons">
                <a href="#projects" class="button primary">
                    Explore my projects 🍓
                </a>

                <a href="#about" class="button secondary">
                    Get to know me ♡
                </a>
            </div>

        </section>

        <!-- NAVIGATION -->

        <nav class="navigation">
            <a href="#about">♡ About Me</a>
            <a href="#skills">✿ My Skills</a>
            <a href="#projects">🍰 Projects</a>
            <a href="#garden">🍓 Coding Garden</a>
            <a href="#contact">💌 Say Hello</a>
        </nav>

        <!-- ABOUT -->

        <section class="section" id="about">

            <div class="section-heading">
                <h2>Once upon a <span>Khushi...</span> ♡</h2>
                <span class="tiny-label">A little introduction</span>
            </div>

            <div class="paper about-grid">

                <div class="about-text">

                    <p>
                        I'm a computer science student with a big heart
                        for creativity, code, and cute little things!
                    </p>

                    <p>
                        I love designing, building, and exploring new ideas.
                        From UI/UX to web development and game design,
                        I'm always excited to learn, create, and bring my
                        imagination to life.
                    </p>

                    <p>
                        Currently collecting coding skills, creative ideas,
                        and tiny wins, one project at a time. 🌷
                    </p>

                    <div class="signature">
                        Same girl. Bigger dreams. Better code. ♡
                    </div>

                </div>

                <div class="personality-card">

                    <h3>Little things about me 🎀</h3>

                    <p>♡ Creative thinker</p>
                    <p>♡ Curious problem solver</p>
                    <p>♡ Lover of pretty interfaces</p>
                    <p>♡ Always learning something new</p>
                    <p>♡ Future tech creator</p>

                </div>

            </div>

        </section>

        <!-- SKILLS -->

        <section class="section" id="skills">

            <div class="section-heading">
                <h2>My little <span>patisserie</span> 🍰</h2>
                <span class="tiny-label">Skills baked with love</span>
            </div>

            <div class="bakery">

                <div class="bakery-title">
                    The Skill Bakery ♡
                </div>

                <div class="skills-grid">

                    <div class="skill">
                        <span class="skill-dessert">🍰</span>
                        <span class="skill-name">HTML</span>
                    </div>

                    <div class="skill">
                        <span class="skill-dessert">🧁</span>
                        <span class="skill-name">CSS</span>
                    </div>

                    <div class="skill">
                        <span class="skill-dessert">🍓</span>
                        <span class="skill-name">JavaScript</span>
                    </div>

                    <div class="skill">
                        <span class="skill-dessert">🍪</span>
                        <span class="skill-name">Python</span>
                    </div>

                    <div class="skill">
                        <span class="skill-dessert">🍮</span>
                        <span class="skill-name">UI/UX</span>
                    </div>

                    <div class="skill">
                        <span class="skill-dessert">🍒</span>
                        <span class="skill-name">Git</span>
                    </div>

                </div>

            </div>

        </section>

        <!-- PROJECTS -->

        <section class="section" id="projects">

            <div class="section-heading">
                <h2>Freshly baked <span>projects</span> ♡</h2>
                <span class="tiny-label">Made with imagination</span>
            </div>

            <div class="projects-grid">

                <article class="project">

                    <div class="project-art">
                        <span>🌷</span>
                    </div>

                    <h3>Blooming Tulip</h3>

                    <p>
                        A digital flower that blooms through CSS,
                        turning a little experiment into a tiny garden.
                    </p>

                    <div class="project-tags">
                        <span>HTML</span>
                        <span>CSS</span>
                        <span>Animation</span>
                    </div>

                    <a
                        href="https://blooming-tulip.vercel.app/"
                        target="_blank"
                        rel="noopener noreferrer"
                        class="project-link"
                    >
                        Visit the garden ↗
                    </a>

                </article>

                <article class="project">

                    <div class="project-art">
                        <span>🎲</span>
                    </div>

                    <h3>Garba Night Ludo</h3>

                    <p>
                        A festive Ludo board inspired by colorful
                        Garba nights, created with HTML and CSS.
                    </p>

                    <div class="project-tags">
                        <span>HTML</span>
                        <span>CSS</span>
                        <span>Game Design</span>
                    </div>

                    <a href="#contact" class="project-link">
                        More details soon ♡
                    </a>

                </article>

                <article class="project">

                    <div class="project-art">
                        <span>🐈</span>
                    </div>

                    <h3>Pixel Pet</h3>

                    <p>
                        A tiny pixel-inspired world for a cute digital
                        companion, full of playful ideas.
                    </p>

                    <div class="project-tags">
                        <span>JavaScript</span>
                        <span>Creativity</span>
                    </div>

                    <a href="#contact" class="project-link">
                        Coming soon ♡
                    </a>

                </article>

                <article class="project">

                    <div class="project-art">
                        <span>🪟</span>
                    </div>

                    <h3>My Cozy Portfolio</h3>

                    <p>
                        A little home on the internet where design,
                        imagination, and code come together.
                    </p>

                    <div class="project-tags">
                        <span>HTML</span>
                        <span>CSS</span>
                        <span>Web Design</span>
                    </div>

                    <a href="#home" class="project-link">
                        You're here already ♡
                    </a>

                </article>

            </div>

        </section>

        <!-- CODING GARDEN -->

        <section class="section" id="garden">

            <div class="section-heading">
                <h2>My coding <span>garden</span> 🍓</h2>
                <span class="tiny-label">Growing one commit at a time</span>
            </div>

            <div class="garden">

                <div class="garden-top">

                    <div>
                        <h3>A garden still growing 🌱</h3>
                        <p>Every little step counts.</p>
                    </div>

                    <span>🌷 🍓 🌷</span>

                </div>

                <div class="garden-stats">

                    <div class="stat">
                        <strong>🌱</strong>
                        <span>Learning every day</span>
                    </div>

                    <div class="stat">
                        <strong>💻</strong>
                        <span>Building new things</span>
                    </div>

                    <div class="stat">
                        <strong>✨</strong>
                        <span>Dreaming bigger</span>
                    </div>

                </div>

                <div class="garden-note">
                    "A little progress each day adds up to beautiful things." ♡
                </div>

            </div>

        </section>

        <!-- CONTACT -->

        <section class="section" id="contact">

            <div class="contact">

                <span class="contact-flower left">🌷</span>
                <span class="contact-flower right">🍓</span>

                <h2>Let's make magic! ♡</h2>

                <p>
                    Have a fun idea, want to collaborate, or just want
                    to talk about design and code? My little inbox is open.
                </p>

                <a
                    href="mailto:YOUR_EMAIL@example.com"
                    class="button"
                >
                    Send me a little letter 💌
                </a>

            </div>

        </section>

        <!-- FOOTER -->

        <footer>

            <div>
                Made with love, code, and a sprinkle of strawberry magic
                <span class="footer-flower">🍓</span>
            </div>

            <div>
                © 2026 thecodedcharm · Growing at my own pace ♡
            </div>

        </footer>

    </main>

    <script>
        const floatingWorld = document.getElementById("floatingWorld");

        const decorations = [
            "🍓", "✿", "♡", "✧", "🌸", "⋆", "🌷", "୨୧"
        ];

        for (let i = 0; i < 32; i++) {
            const decoration = document.createElement("span");

            decoration.className = "floaty";
            decoration.textContent =
                decorations[Math.floor(Math.random() * decorations.length)];

            decoration.style.setProperty(
                "--left",
                Math.random() * 100 + "%"
            );

            decoration.style.setProperty(
                "--size",
                (12 + Math.random() * 17) + "px"
            );

            decoration.style.setProperty(
                "--duration",
                (12 + Math.random() * 20) + "s"
            );

            decoration.style.setProperty(
                "--delay",
                (-Math.random() * 30) + "s"
            );

            floatingWorld.appendChild(decoration);
        }
    </script>

</body>
</html>
