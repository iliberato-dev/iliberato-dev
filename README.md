<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfólio | Isaque Liberato</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&family=Orbitron:wght@500;700&display=swap" rel="stylesheet">

    <style>
        /* --- Reset Básico e Estilo Global --- */
        :root {
            --bg-color: #1a1a2e;
            --card-bg-color: rgba(26, 26, 46, 0.6);
            --primary-color: #00e5ff;
            --secondary-color: #e4d804;
            --text-color: #e0e0e0;
            --font-heading: 'Orbitron', sans-serif;
            --font-body: 'Montserrat', sans-serif;
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
            background-color: var(--bg-color);
            color: var(--text-color);
            font-family: var(--font-body);
            overflow-x: hidden;
        }
        
        /* --- Fundo de Partículas (Canvas) --- */
        #particle-background {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }
        
        /* --- Layout Principal --- */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* --- Estilo das Seções e Animações de Scroll --- */
        section {
            margin-bottom: 80px;
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
        }
        
        section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        /* --- Cabeçalho (Header) --- */
        .header {
            text-align: center;
            margin-bottom: 80px;
        }

        .header img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            border: 4px solid var(--primary-color);
            box-shadow: 0 0 25px var(--primary-color);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .header img:hover {
            transform: scale(1.05) rotate(5deg);
            box-shadow: 0 0 40px var(--primary-color);
        }

        .header h1 {
            font-family: var(--font-heading);
            font-size: 2.5rem;
            color: white;
            margin-top: 20px;
            text-shadow: 0 0 10px var(--primary-color);
        }

        .header h3 {
            font-size: 1.2rem;
            color: var(--primary-color);
            font-weight: 400;
            min-height: 50px;
        }
        
        .typewriter-cursor {
            color: var(--secondary-color);
            animation: blink 1s step-end infinite;
        }

        @keyframes blink {
            from, to { color: transparent }
            50% { color: var(--secondary-color); }
        }

        /* --- Estilo dos Cards --- */
        .card {
            background: var(--card-bg-color);
            border: 1px solid var(--primary-color);
            border-radius: 15px;
            padding: 30px;
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            box-shadow: 0 8px 32px 0 rgba(0, 229, 255, 0.2);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 12px 40px 0 rgba(0, 229, 255, 0.3);
        }
        
        .card h2 {
            font-family: var(--font-heading);
            color: var(--primary-color);
            margin-bottom: 20px;
            border-bottom: 2px solid var(--secondary-color);
            padding-bottom: 10px;
            display: inline-block;
        }
        
        /* --- Seção Sobre Mim --- */
        #sobre ul {
            list-style: none;
        }
        
        #sobre li {
            margin-bottom: 15px;
            line-height: 1.6;
        }
        
        #sobre li strong {
            color: var(--secondary-color);
            font-weight: 700;
        }
        
        #sobre a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: bold;
            transition: text-shadow 0.3s ease;
        }

        #sobre a:hover {
            text-shadow: 0 0 8px var(--primary-color);
        }

        /* --- Seção Tecnologias --- */
        #tecnologias .skills-container {
            text-align: center;
        }

        /* --- Seção GitHub --- */
        #github .stats-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        #github .stats-container img {
            max-width: 100%;
        }

        /* --- Rodapé (Footer) --- */
        footer {
            text-align: center;
            padding: 40px 20px;
        }

        .social-links a {
            margin: 0 15px;
            display: inline-block;
            transition: transform 0.3s ease;
        }
        
        .social-links a:hover {
            transform: scale(1.2);
        }

        .social-links img {
            width: 40px;
            filter: invert(89%) sepia(85%) saturate(1476%) hue-rotate(107deg) brightness(102%) contrast(107%);
        }
        
        footer p {
            margin-top: 20px;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>

    <canvas id="particle-background"></canvas>

    <div class="container">

        <header class="header">
            <img src="https://i.imgur.com/Rfnx5Vt.png" alt="Foto de Perfil de Isaque Liberato">
            <h1>Olá 👋, eu sou Isaque Liberato</h1>
            <h3 id="subtitle"></h3>
        </header>

        <main>
            <section id="sobre" class="card">
                <h2>// Sobre Mim</h2>
                <ul>
                    <li>🔭 Atualmente guiando a próxima geração de devs e imerso em <strong>React Hooks avançados, Next.js com SSR e soluções Serverless na nuvem</strong>.</li>
                    <li>🌱 Em constante evolução, explorando as fronteiras da <strong>Microfrontend Architecture e APIs GraphQL de alta performance</strong>.</li>
                    <li>👯 Entusiasta por colaborações em <strong>projetos open source que desafiam os limites do desenvolvimento web</strong>.</li>
                    <li>💬 Sempre aberto a debates sobre <strong>ecossistema JavaScript moderno, Clean Code e as tendências disruptivas do futuro da web</strong>.</li>
                    <li>📫 Contate-me: <a href="mailto:isaque.cedesp@gmail.com">isaque.cedesp@gmail.com</a></li>
                </ul>
            </section>

            <section id="tecnologias" class="card">
                <h2>// Tecnologias no meu Radar</h2>
                <div class="skills-container">
                    <img src="https://skillicons.dev/icons?i=html,css,js,ts,react,nextjs,nodejs,express,mongodb,postgres,docker,git,github,figma,aws,azure,graphql&theme=dark&perline=7" alt="Ícones de Tecnologias">
                </div>
            </section>

            <section id="github" class="card">
                <h2>// Monitorando meu Progresso no GitHub</h2>
                <div class="stats-container">
                    <img src="https://github-readme-stats.vercel.app/api?username=iliberato-dev&show_icons=true&theme=dark&rank_icon=github&bg_color=1a1a2e00&title_color=00e5ff&icon_color=00e5ff&text_color=e0e0e0&border_color=00e5ff" alt="Estatísticas do GitHub de Isaque Liberato">
                    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=iliberato-dev&layout=compact&theme=dark&bg_color=1a1a2e00&title_color=00e5ff&text_color=e0e0e0&border_color=00e5ff" alt="Linguagens mais usadas por Isaque Liberato no GitHub">
                    <img src="https://streak-stats.demolab.com/?user=iliberato-dev&theme=dark&background=1a1a2e00&ring=00e5ff&fire=00e5ff&currStreakNum=e0e0e0&currStreakLabel=00e5ff&sideNums=e0e0e0&sideLabels=00e5ff&border=00e5ff" alt="Sequência de contribuições de Isaque Liberato no GitHub">
                </div>
            </section>
        </main>

        <footer>
            <section class="social-links">
                <a href="https://www.linkedin.com/in/isaque-liberato-b552b51a7/" target="_blank" title="LinkedIn">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in.svg" alt="LinkedIn">
                </a>
                <a href="https://github.com/iliberato-dev" target="_blank" title="GitHub">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/github.svg" alt="GitHub">
                </a>
            </section>
            <p>&copy; 2025 - Isaque Liberato | Criado com paixão e código.</p>
        </footer>

    </div>

    <script>
    document.addEventListener('DOMContentLoaded', function() {

        // --- LÓGICA DO FUNDO DE PARTÍCULAS (CANVAS) ---
        const canvas = document.getElementById('particle-background');
        const ctx = canvas.getContext('2d');

        let particles = [];
        
        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resizeCanvas();

        function createParticles() {
            particles = [];
            let numberOfParticles = (canvas.height * canvas.width) / 9000;
            for (let i = 0; i < numberOfParticles; i++) {
                particles.push({
                    x: Math.random() * canvas.width,
                    y: Math.random() * canvas.height,
                    radius: Math.random() * 1.5 + 0.5,
                    vx: Math.random() * 0.5 - 0.25,
                    vy: Math.random() * 0.5 - 0.25,
                });
            }
        }
        createParticles();
        
        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for(let particle of particles) {
                particle.x += particle.vx;
                particle.y += particle.vy;

                if (particle.x < 0 || particle.x > canvas.width) particle.vx *= -1;
                if (particle.y < 0 || particle.y > canvas.height) particle.vy *= -1;

                ctx.beginPath();
                ctx.arc(particle.x, particle.y, particle.radius, 0, Math.PI * 2);
                ctx.fillStyle = 'rgba(0, 229, 255, 0.5)';
                ctx.fill();
            }
            requestAnimationFrame(animate);
        }
        animate();

        window.addEventListener('resize', () => {
            resizeCanvas();
            createParticles();
        });

        // --- LÓGICA DO EFEITO DE DIGITAÇÃO ---
        const subtitleElement = document.getElementById('subtitle');
        const text = "Desenvolvedor Web | Professor de Programação | Explorador do Futuro Digital";
        let index = 0;
        
        function typeWriter() {
            if (index < text.length) {
                subtitleElement.innerHTML = text.substring(0, index + 1) + '<span class="typewriter-cursor">|</span>';
                index++;
                setTimeout(typeWriter, 70);
            } else {
                 subtitleElement.innerHTML = text; // Remove cursor at the end
            }
        }
        typeWriter();

        // --- LÓGICA DAS ANIMAÇÕES DE SCROLL ---
        const sections = document.querySelectorAll('section');
        const observer = new IntersectionObserver(entries => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                    // Optional: unobserve after it becomes visible to save resources
                    // observer.unobserve(entry.target);
                }
            });
        }, {
            threshold: 0.1 // Triggers when 10% of the element is visible
        });
        
        sections.forEach(section => {
            observer.observe(section);
        });
    });
    </script>
</body>
</html>
