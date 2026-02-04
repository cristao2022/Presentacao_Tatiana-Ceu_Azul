<!DOCTYPE html>
<html lang="pt-AO">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sala Digital - O Futuro dos Nossos Filhos Começa Hoje</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #1a365d;
            --secondary: #2c5282;
            --accent: #ffd23f;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --light: #f8f9fa;
            --dark: #343a40;
            --text: #333;
            --white: #fff;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: var(--text);
            overflow-x: hidden;
            min-height: 100vh;
        }

        .slides-container {
            position: relative;
            width: 100%;
            min-height: 100vh;
            padding-bottom: 100px; /* Espaço para os dots na parte inferior */
        }

        .slide {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            min-height: 100vh;
            display: none;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
            padding: 100px 60px 120px 60px; /* Padding maior em cima e embaixo */
            text-align: center;
            color: white;
            opacity: 0;
            transform: translateX(100%);
            transition: all 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
            z-index: 1;
            overflow-y: auto;
        }

        .slide.active {
            display: flex;
            opacity: 1;
            transform: translateX(0);
            z-index: 10;
        }

        .slide.prev {
            transform: translateX(-100%);
        }

        .slide.next {
            transform: translateX(100%);
        }

        .slide-content {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 60px;
            max-width: 1200px;
            width: 100%;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
            animation: slideIn 0.8s ease-out;
            margin-bottom: 40px;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(50px) scale(0.95);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        .slide h1 {
            font-size: 3.5em;
            font-weight: 800;
            margin-bottom: 30px;
            color: var(--primary);
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
            line-height: 1.2;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .slide h2 {
            font-size: 2em;
            font-weight: 600;
            margin-bottom: 40px;
            color: var(--secondary);
            line-height: 1.4;
        }

        .slide p {
            font-size: 1.4em;
            line-height: 1.8;
            margin-bottom: 20px;
            color: var(--text);
            max-width: 900px;
        }

        .slide p.lead {
            font-size: 1.8em;
            font-weight: 600;
            margin-bottom: 30px;
        }

        .slide p.quote {
            font-size: 1.6em;
            font-style: italic;
            color: var(--secondary);
            margin: 30px 0;
            padding: 30px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            border-radius: 15px;
            position: relative;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .slide p.quote::before,
        .slide p.quote::after {
            content: '"';
            font-size: 4em;
            position: absolute;
            opacity: 0.2;
            color: white;
        }

        .slide p.quote::before {
            top: -20px;
            left: 10px;
        }

        .slide p.quote::after {
            bottom: -40px;
            right: 10px;
        }

        .slide ul {
            list-style: none;
            padding: 0;
            margin: 30px 0;
            text-align: left;
            max-width: 800px;
        }

        .slide li {
            font-size: 1.5em;
            margin: 20px 0;
            padding-left: 50px;
            position: relative;
            line-height: 1.6;
            color: var(--text);
            animation: fadeIn 0.6s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }

        .slide li:nth-child(1) { animation-delay: 0.1s; }
        .slide li:nth-child(2) { animation-delay: 0.2s; }
        .slide li:nth-child(3) { animation-delay: 0.3s; }
        .slide li:nth-child(4) { animation-delay: 0.4s; }
        .slide li:nth-child(5) { animation-delay: 0.5s; }

        .slide li::before {
            position: absolute;
            left: 0;
            top: 0;
            font-size: 2em;
            color: var(--secondary);
        }

        .comparison {
            display: flex;
            justify-content: space-around;
            width: 100%;
            max-width: 1000px;
            margin: 40px 0;
            gap: 40px;
        }

        .comparison-column {
            flex: 1;
            padding: 40px;
            border-radius: 20px;
            background: var(--light);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            transition: transform 0.3s ease;
        }

        .comparison-column:hover {
            transform: translateY(-10px);
        }

        .comparison-column h3 {
            font-size: 2em;
            margin-bottom: 30px;
            color: var(--secondary);
            text-align: center;
        }

        .comparison-column.before h3 {
            color: var(--danger);
        }

        .comparison-column.after h3 {
            color: var(--success);
        }

        .comparison-column p {
            font-size: 1.3em;
            margin: 15px 0;
            color: var(--text);
            text-align: left;
        }

        .price-box {
            background: linear-gradient(135deg, var(--accent) 0%, #ff9800 100%);
            padding: 50px;
            border-radius: 25px;
            text-align: center;
            margin: 40px 0;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.03); }
        }

        .price-box h3 {
            font-size: 1.8em;
            margin-bottom: 20px;
            color: var(--primary);
        }

        .price-amount {
            font-size: 4.5em;
            font-weight: 800;
            color: var(--primary);
            margin: 20px 0;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.2);
        }

        .price-description {
            font-size: 1.4em;
            color: var(--dark);
            margin-top: 15px;
        }

        .highlight-box {
            background: linear-gradient(135deg, var(--success) 0%, #20c997 100%);
            padding: 40px;
            border-radius: 20px;
            margin: 30px 0;
            color: white;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .warning-box {
            background: linear-gradient(135deg, var(--warning) 0%, #ff9800 100%);
            padding: 40px;
            border-radius: 20px;
            margin: 30px 0;
            color: var(--dark);
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .decision-box {
            display: flex;
            justify-content: space-around;
            width: 100%;
            max-width: 1100px;
            margin: 40px 0;
            gap: 30px;
        }

        .decision-option {
            flex: 1;
            padding: 40px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .decision-option.no {
            background: linear-gradient(135deg, var(--danger) 0%, #c82333 100%);
            color: white;
        }

        .decision-option.yes {
            background: linear-gradient(135deg, var(--success) 0%, #20c997 100%);
            color: white;
        }

        .decision-option h3 {
            font-size: 2em;
            margin-bottom: 25px;
        }

        .decision-option p {
            font-size: 1.3em;
            margin: 15px 0;
            line-height: 1.6;
        }

        .slide-counter {
            position: fixed;
            top: 30px;
            right: 40px;
            background: rgba(255, 255, 255, 0.95);
            padding: 15px 35px;
            border-radius: 50px;
            font-size: 1.3em;
            font-weight: 700;
            color: var(--primary);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
            z-index: 100;
        }

        .dots-container {
            position: fixed;
            bottom: 40px; /* Elevado para não sobrepor conteúdo */
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 12px;
            z-index: 100;
            background: rgba(255, 255, 255, 0.95);
            padding: 12px 25px;
            border-radius: 30px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.3);
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: rgba(44, 82, 130, 0.5);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .dot.active {
            background: var(--secondary);
            transform: scale(1.4);
            box-shadow: 0 0 10px rgba(44, 82, 130, 0.8);
        }

        .dot:hover {
            background: var(--secondary);
            transform: scale(1.3);
        }

        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            height: 6px;
            background: linear-gradient(90deg, var(--primary) 0%, var(--secondary) 100%);
            z-index: 1000;
            transition: width 0.5s ease;
        }

        .school-info {
            margin-top: 50px;
            font-size: 1.3em;
            color: var(--secondary);
            font-weight: 600;
        }

        .contact-info {
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            padding: 40px;
            border-radius: 20px;
            margin: 30px 0;
            color: white;
            text-align: left;
            max-width: 800px;
        }

        .contact-info h3 {
            font-size: 1.8em;
            margin-bottom: 20px;
            text-align: center;
        }

        .contact-info p {
            font-size: 1.3em;
            margin: 15px 0;
            line-height: 1.8;
        }

        .icon-text {
            display: flex;
            align-items: center;
            gap: 15px;
            margin: 15px 0;
        }

        .icon {
            font-size: 2em;
            color: var(--accent);
        }

        /* Responsividade */
        @media (max-width: 1024px) {
            .slide {
                padding: 80px 40px 100px 40px;
            }
            
            .slide h1 {
                font-size: 2.8em;
            }
            
            .slide h2 {
                font-size: 1.8em;
            }
            
            .slide p {
                font-size: 1.3em;
            }
            
            .slide-content {
                padding: 40px;
            }
            
            .price-amount {
                font-size: 3.5em;
            }
            
            .dots-container {
                bottom: 30px;
                gap: 8px;
            }
            
            .dot {
                width: 10px;
                height: 10px;
            }
        }

        @media (max-width: 768px) {
            .slide {
                padding: 60px 25px 90px 25px;
            }
            
            .slide h1 {
                font-size: 2.3em;
            }
            
            .slide h2 {
                font-size: 1.6em;
            }
            
            .slide p {
                font-size: 1.2em;
            }
            
            .slide-content {
                padding: 30px 20px;
            }
            
            .comparison,
            .decision-box {
                flex-direction: column;
                gap: 20px;
            }
            
            .price-amount {
                font-size: 2.8em;
            }
            
            .slide-counter {
                top: 20px;
                right: 20px;
                padding: 10px 25px;
                font-size: 1.1em;
            }
            
            .dots-container {
                bottom: 25px;
                gap: 6px;
                padding: 10px 20px;
            }
            
            .dot {
                width: 8px;
                height: 8px;
            }
        }

        @media (max-width: 480px) {
            .slide {
                padding: 50px 20px 80px 20px;
            }
            
            .slide h1 {
                font-size: 2em;
            }
            
            .slide h2 {
                font-size: 1.4em;
            }
            
            .slide p {
                font-size: 1.1em;
            }
            
            .price-amount {
                font-size: 2.2em;
            }
            
            .slide-counter {
                display: none;
            }
            
            .dots-container {
                bottom: 20px;
                padding: 8px 15px;
            }
            
            .dot {
                width: 7px;
                height: 7px;
            }
        }
    </style>
</head>
<body>
    <div class="progress-bar" id="progressBar"></div>
    
    <div class="slides-container">
        <!-- Slide 1: Capa -->
        <div class="slide active" id="slide1">
            <div class="slide-content">
                <h1>O FUTURO DE ANGOLA COMEÇA NA SALA DE AULA</h1>
                <h2>Por que estamos criando uma Sala Digital na nossa escola</h2>
                <p class="quote">Não formamos apenas alunos.<br>Formamos os engenheiros, médicos, professores e líderes<br>que vão reconstruir e desenvolver Angola.</p>
                <div class="school-info">
                    <p>[Nome da Escola]</p>
                    <p>[Cidade, Província] | Fevereiro de 2026</p>
                </div>
            </div>
        </div>

        <!-- Slide 2: Realidade -->
        <div class="slide" id="slide2">
            <div class="slide-content">
                <h1>Uma realidade que todo pai angolano conhece</h1>
                <p class="lead">"Quero que meu filho tenha mais oportunidades do que eu tive"</p>
                <ul>
                    <li><i class="fas fa-history"></i> Crescemos num período difícil da nossa história</li>
                    <li><i class="fas fa-book"></i> Tivemos acesso limitado a livros e materiais escolares</li>
                    <li><i class="fas fa-dream"></i> Sonhamos com um futuro melhor para os nossos filhos</li>
                </ul>
                <div class="highlight-box">
                    <p style="font-size: 1.6em; font-weight: 600;">Hoje, Angola avança com força, mas as nossas escolas precisam acompanhar este progresso.</p>
                </div>
                <p class="lead"><strong>Seu filho merece aprender com as ferramentas do século XXI — não do século passado.</strong></p>
                <p style="font-size: 1.4em; font-weight: 600; color: var(--secondary);">A tecnologia não é um luxo. É a ponte entre o sonho do seu filho e a realidade do seu futuro.</p>
            </div>
        </div>

        <!-- Slide 3: O que é Sala Digital -->
        <div class="slide" id="slide3">
            <div class="slide-content">
                <h1>O que é, de verdade, uma Sala Digital?</h1>
                <div class="warning-box">
                    <p style="font-size: 1.8em; font-weight: 700;">Não é "computador na sala". É abrir janelas para o mundo.</p>
                </div>
                <ul>
                    <li><i class="fas fa-globe-africa"></i> Pesquisa em bibliotecas digitais do mundo inteiro</li>
                    <li><i class="fas fa-satellite"></i> Visualiza o rio Cuanza visto do espaço, fauna do Cuando Cubango em HD</li>
                    <li><i class="fas fa-gamepad"></i> Pratica com simulações interativas — sem sair da escola</li>
                    <li><i class="fas fa-laptop-code"></i> Desenvolve confiança com ferramentas da universidade e trabalho</li>
                </ul>
                <p class="quote">É como dar asas ao conhecimento — sem sair da nossa terra, mas conectado ao mundo.</p>
                <div class="highlight-box">
                    <p style="font-size: 1.3em;"><strong>Importante:</strong> Utilizamos tecnologia vCloudPoint — solução inteligente que permite vários alunos usarem simultaneamente um sistema centralizado, garantindo estabilidade, segurança e baixo consumo de energia.</p>
                </div>
            </div>
        </div>

        <!-- Slide 4: Antes x Depois -->
        <div class="slide" id="slide4">
            <div class="slide-content">
                <h1>Benefícios concretos no dia a dia do seu filho</h1>
                <div class="comparison">
                    <div class="comparison-column before">
                        <h3><i class="fas fa-times-circle"></i> ANTES</h3>
                        <p><i class="fas fa-book"></i> Lê sobre petróleo em livro desatualizado</p>
                        <p><i class="fas fa-pen"></i> Copia mapas de Angola à mão</p>
                        <p><i class="fas fa-hourglass-half"></i> Espera meses por um livro da biblioteca</p>
                        <p><i class="fas fa-file"></i> Entrega trabalho manuscrito</p>
                    </div>
                    <div class="comparison-column after">
                        <h3><i class="fas fa-check-circle"></i> DEPOIS</h3>
                        <p><i class="fas fa-oil-well"></i> Explora plataforma petrolífera com animação 3D</p>
                        <p><i class="fas fa-map-marked-alt"></i> Interage com mapas digitais do nosso país</p>
                        <p><i class="fas fa-book-reader"></i> Acede a milhares de livros digitais em português</p>
                        <p><i class="fas fa-presentation"></i> Cria apresentações com fotos, áudio e texto</p>
                    </div>
                </div>
                <div class="highlight-box">
                    <p style="font-size: 1.5em; font-weight: 600;">Seu filho aprende sobre Angola e o mundo com profundidade, orgulho e curiosidade — desenvolvendo competências que o mercado de trabalho exige.</p>
                </div>
            </div>
        </div>

        <!-- Slide 5: Competências -->
        <div class="slide" id="slide5">
            <div class="slide-content">
                <h1>Competências para o mercado de trabalho angolano</h1>
                <p class="lead">Angola precisa urgentemente de jovens preparados para:</p>
                <ul>
                    <li><i class="fas fa-industry"></i> <strong>Sector petrolífero e mineiro</strong> — relatórios técnicos, análise de dados</li>
                    <li><i class="fas fa-seedling"></i> <strong>Agricultura moderna</strong> — gestão de culturas com tecnologia adaptada</li>
                    <li><i class="fas fa-landmark"></i> <strong>Turismo</strong> — conteúdos digitais sobre as maravilhas de Angola</li>
                    <li><i class="fas fa-lightbulb"></i> <strong>Empreendedorismo</strong> — negócios online que geram rendimento familiar</li>
                </ul>
                <p class="lead" style="margin-top: 40px;">Na Sala Digital, seu filho desenvolve naturalmente:</p>
                <ul>
                    <li><i class="fas fa-laptop"></i> <strong>Domínio do computador</strong> — essencial para qualquer emprego formal</li>
                    <li><i class="fas fa-search"></i> <strong>Pesquisa online</strong> — encontrar bolsas, estágios e concursos</li>
                    <li><i class="fas fa-envelope"></i> <strong>Comunicação digital</strong> — e-mails profissionais, currículos modernos</li>
                    <li><i class="fas fa-brain"></i> <strong>Pensamento crítico</strong> — discernir notícias verdadeiras de falsas</li>
                </ul>
                <p class="quote">Não formamos apenas alunos. Formamos futuros contribuintes para o desenvolvimento sustentável de Angola.</p>
            </div>
        </div>

        <!-- Slide 6: Na prática -->
        <div class="slide" id="slide6">
            <div class="slide-content">
                <h1>Na prática: o que seu filho fará na Sala Digital</h1>
                <ul>
                    <li><i class="fas fa-map"></i> <strong>Geografia:</strong> Explorar mapas interativos das 18 províncias — rios, serras, recursos naturais</li>
                    <li><i class="fas fa-binoculars"></i> <strong>Geografia:</strong> Comparar imagens de satélite de Luanda em 1990 e 2026</li>
                    <li><i class="fas fa-landmark"></i> <strong>História:</strong> "Visitar" virtualmente o Museu Nacional de História Militar</li>
                    <li><i class="fas fa-video"></i> <strong>História:</strong> Assistir depoimentos de heróis da independência</li>
                    <li><i class="fas fa-seedling"></i> <strong>Ciências:</strong> Simular cultivo de milho, mandioca, feijão adaptados ao clima</li>
                    <li><i class="fas fa-newspaper"></i> <strong>Português:</strong> Criar jornal digital sobre tradições do município</li>
                    <li><i class="fas fa-podcast"></i> <strong>Português:</strong> Gravar podcasts com lendas angolanas (Kimbo e Kiluange)</li>
                </ul>
                <div class="highlight-box">
                    <p style="font-size: 1.6em; font-weight: 600;">A tecnologia valoriza a nossa identidade — não apaga a nossa cultura. Pelo contrário: dá-lhe voz e alcance mundial.</p>
                </div>
            </div>
        </div>

        <!-- Slide 7: Igualdade -->
        <div class="slide" id="slide7">
            <div class="slide-content">
                <h1>Igualdade de oportunidades: justiça para todas as crianças</h1>
                <div class="warning-box">
                    <p style="font-size: 1.6em; font-weight: 600;">Realidade angolana que não podemos ignorar:</p>
                </div>
                <ul>
                    <li><i class="fas fa-times"></i> Muitas famílias não têm computador em casa</li>
                    <li><i class="fas fa-times"></i> Crianças de zonas rurais ficam mais distantes do mundo digital</li>
                    <li><i class="fas fa-times"></i> Sem acesso na escola, estas crianças nunca terão oportunidade</li>
                </ul>
                <div class="highlight-box" style="margin-top: 40px;">
                    <p style="font-size: 1.6em; font-weight: 600;">Com a Sala Digital da nossa escola:</p>
                </div>
                <ul>
                    <li><i class="fas fa-check"></i> Todo aluno — do bairro elegante ou do musseque — tem acesso igual</li>
                    <li><i class="fas fa-check"></i> Ninguém é deixado para trás por causa da condição económica</li>
                    <li><i class="fas fa-check"></i> A escola promove justiça social e inclusão</li>
                </ul>
                <p class="quote">Na nossa escola, o filho do motorista tem as mesmas oportunidades que o filho do director.<br>Porque o talento não tem endereço — e a educação deve ser direito de todos os filhos de Angola.</p>
            </div>
        </div>

        <!-- Slide 8: Universidade -->
        <div class="slide" id="slide8">
            <div class="slide-content">
                <h1>Preparação para a universidade em Angola e no estrangeiro</h1>
                <p class="lead">Universidades (UP, UAN, UÍ, ISCED) exigem cada vez mais:</p>
                <ul>
                    <li><i class="fas fa-file-word"></i> Trabalhos digitais formatados correctamente em Word</li>
                    <li><i class="fas fa-database"></i> Pesquisa em bases de dados académicas (não apenas Google)</li>
                    <li><i class="fas fa-laptop"></i> Uso de plataformas como Moodle para aulas e avaliações</li>
                    <li><i class="fas fa-chart-line"></i> Apresentações profissionais em PowerPoint</li>
                </ul>
                <div class="warning-box" style="margin-top: 40px;">
                    <p style="font-size: 1.6em; font-weight: 600;">Sem prática escolar prévia:</p>
                    <ul style="text-align: left; margin-top: 20px;">
                        <li><i class="fas fa-exclamation-triangle"></i> O aluno perde confiança no primeiro semestre</li>
                        <li><i class="fas fa-money-bill"></i> Gasta dinheiro com cursos básicos que deveriam ser gratuitos</li>
                        <li><i class="fas fa-frown"></i> Desiste de sonhos por vergonha de não saber usar ferramentas</li>
                    </ul>
                </div>
                <div class="highlight-box" style="margin-top: 30px;">
                    <p style="font-size: 1.6em; font-weight: 600;">A Sala Digital elimina esta barreira antes que ela destrua sonhos e potencialidades.</p>
                </div>
            </div>
        </div>

        <!-- Slide 9: Segurança -->
        <div class="slide" id="slide9">
            <div class="slide-content">
                <h1>Segurança e respeito aos valores familiares</h1>
                <div class="warning-box">
                    <p style="font-size: 1.6em; font-weight: 600;">Preocupação legítima de todo pai e mãe angolano:</p>
                    <p style="font-size: 1.8em; font-weight: 700; margin-top: 15px;">"A tecnologia vai afastar meu filho dos nossos valores?"</p>
                </div>
                <div class="highlight-box" style="margin-top: 30px;">
                    <p style="font-size: 1.6em; font-weight: 600;">Na nossa Sala Digital:</p>
                </div>
                <ul>
                    <li><i class="fas fa-shield-alt"></i> <strong>Conteúdo 100% controlado</strong> — apenas materiais educativos aprovados</li>
                    <li><i class="fas fa-chalkboard-teacher"></i> <strong>Professor supervisiona</strong> todas as actividades em tempo real</li>
                    <li><i class="fas fa-flag-angola"></i> <strong>Foco na cultura angolana</strong> — tradições, línguas nacionais, história</li>
                    <li><i class="fas fa-ban"></i> <strong>Proibido redes sociais, jogos</strong> e conteúdos impróprios</li>
                </ul>
                <p class="quote">A tecnologia na nossa escola respeita os valores da família angolana:<br>respeito aos mais velhos, disciplina, trabalho árduo e amor à pátria.</p>
            </div>
        </div>

        <!-- Slide 10: Exemplos africanos -->
        <div class="slide" id="slide10">
            <div class="slide-content">
                <h1>O exemplo de países africanos que avançaram</h1>
                <ul>
                    <li><i class="fas fa-chart-line"></i> <strong>Ruanda:</strong> Investiu cedo em salas digitais — hoje é referência tecnológica em África</li>
                    <li><i class="fas fa-users"></i> <strong>Quénia:</strong> Programa "Digital Literacy" chegou a 1,2 milhão de crianças</li>
                    <li><i class="fas fa-briefcase"></i> <strong>Gana:</strong> Jovens criaram startups que atraíram milhões em investimento</li>
                </ul>
                <div class="highlight-box" style="margin-top: 40px;">
                    <p style="font-size: 1.8em; font-weight: 700;">Angola tem tudo para ser o próximo grande sucesso africano — mas só se apostarmos HOJE na educação digital dos nossos filhos.</p>
                </div>
                <p class="quote">Os países que avançaram não tinham mais dinheiro que nós.<br>Tinham mais coragem para investir nas crianças.</p>
            </div>
        </div>

        <!-- Slide 11: Testemunho -->
        <div class="slide" id="slide11">
            <div class="slide-content">
                <h1>Uma voz que representa muitas famílias</h1>
                <p class="quote" style="font-size: 1.5em; line-height: 1.8;">
                    Eu sou mãe solteira, trabalho como quitandeira no Roque Santeiro desde as 5h da manhã.<br><br>
                    Não tenho condições de comprar computador para meu filho — nem sequer internet em casa.<br><br>
                    Quando soube que a escola terá Sala Digital, chorei de alegria.<br><br>
                    Meu filho não vai ser deixado para trás.<br><br>
                    Ele também terá direito ao futuro — como qualquer criança em qualquer país do mundo.
                </p>
                <p style="font-size: 1.4em; font-weight: 600; margin-top: 20px; color: var(--secondary);">— Mãe de aluno do 6.º ano, Luanda</p>
                <div class="highlight-box" style="margin-top: 40px;">
                    <p style="font-size: 1.6em; font-weight: 600;">👉 Quantas mães e pais nesta sala sentem exactamente o mesmo?</p>
                </div>
            </div>
        </div>

        <!-- Slide 12: Parceria -->
        <div class="slide" id="slide12">
            <div class="slide-content">
                <h1>Um projecto possível graças a uma parceria responsável</h1>
                <div class="warning-box">
                    <p style="font-size: 1.8em; font-weight: 700;">A nossa escola não tem recursos para fazer isto sozinha.<br>Mas recusamo-nos a deixar os nossos filhos para trás.</p>
                </div>
                <p class="lead" style="margin-top: 30px;">Como muitas escolas em Angola, enfrentamos:</p>
                <ul>
                    <li><i class="fas fa-exclamation-triangle"></i> Orçamento limitado — prioridade sempre foi professores qualificados</li>
                    <li><i class="fas fa-exclamation-triangle"></i> Investimento inicial em tecnologia exige capital que não dispomos</li>
                </ul>
                <div class="highlight-box" style="margin-top: 30px;">
                    <p style="font-size: 1.6em; font-weight: 600;">Por isso, decidimos agir com responsabilidade e visão:</p>
                </div>
                <ul>
                    <li><i class="fas fa-handshake"></i> Procuramos um parceiro sério, angolano e comprometido com a educação</li>
                    <li><i class="fas fa-building"></i> Encontramos a LMB – Soluções Tecnológicas, com experiência comprovada</li>
                    <li><i class="fas fa-project-diagram"></i> Estabelecemos uma parceria de colaboração onde:</li>
                </ul>
                <div class="price-box">
                    <h3>Contribuição mensal por aluno</h3>
                    <div class="price-amount">5.000 Kz</div>
                    <p class="price-description">(menos que um matabicho por dia — mas com impacto para toda a vida do seu filho)</p>
                </div>
                <p class="lead"><strong>Este valor assegura:</strong></p>
                <ul>
                    <li><i class="fas fa-tools"></i> Manutenção técnica contínua (técnico dedicado)</li>
                    <li><i class="fas fa-wifi"></i> Internet dedicada de alta velocidade</li>
                    <li><i class="fas fa-recycle"></i> Retorno gradual do investimento da LMB</li>
                </ul>
                <p class="quote">Não é uma taxa escolar. É um compromisso partilhado:<br>a escola oferece o espaço e os professores,<br>a LMB oferece a tecnologia,<br>e nós, pais, garantimos a sustentabilidade com um contributo acessível.</p>
            </div>
        </div>

        <!-- Slide 13: Solidariedade -->
        <div class="slide" id="slide13">
            <div class="slide-content">
                <h1>Solidariedade e flexibilidade: ninguém fica de fora</h1>
                <div class="price-box" style="background: linear-gradient(135deg, var(--success) 0%, #20c997 100%);">
                    <p style="font-size: 2em; margin-bottom: 20px;">5.000 Kz é acessível</p>
                    <div class="price-amount" style="font-size: 5em; color: white;">5.000 Kz</div>
                    <p class="price-description" style="font-size: 1.8em; color: var(--primary); margin-top: 20px;">e NINGUÉM será excluído por dificuldades económicas</p>
                </div>
                <div class="highlight-box" style="margin-top: 40px; background: linear-gradient(135deg, var(--warning) 0%, #ff9800 100%); color: var(--dark);">
                    <p style="font-size: 1.6em; font-weight: 600;">A escola tem um fundo de solidariedade para famílias que realmente não podem contribuir.<br><br>Porque acreditamos que o direito à educação digital não pode depender da condição económica.</p>
                </div>
            </div>
        </div>

        <!-- Slide 14: Chamada final -->
        <div class="slide" id="slide14">
            <div class="slide-content">
                <h1>Chamada final: o seu "sim" muda vidas</h1>
                <p class="lead">Hoje você decide com o coração de pai/mãe angolano</p>
                <div class="decision-box">
                    <div class="decision-option no">
                        <h3><i class="fas fa-times"></i> Dizer "não"</h3>
                        <p style="font-style: italic; margin-bottom: 20px;">"5.000 Kz... vou pensar..."</p>
                        <p><i class="fas fa-arrow-right"></i> Seu filho perde acesso diário à tecnologia</p>
                        <p><i class="fas fa-arrow-right"></i> Chega à universidade sem base digital</p>
                        <p><i class="fas fa-arrow-right"></i> Fica para trás num mundo que não espera</p>
                    </div>
                    <div class="decision-option yes">
                        <h3><i class="fas fa-check"></i> Dizer "sim"</h3>
                        <p style="font-style: italic; margin-bottom: 20px;">"5.000 Kz por mês é o meu investimento no futuro"</p>
                        <p><i class="fas fa-arrow-right"></i> Ele aprende competências que valem milhões</p>
                        <p><i class="fas fa-arrow-right"></i> Entra na universidade com confiança</p>
                        <p><i class="fas fa-arrow-right"></i> Tem orgulho de ser angolano preparado</p>
                    </div>
                </div>
                <p class="quote" style="font-size: 1.6em; line-height: 1.8;">
                    Não estamos a vender tecnologia.<br>
                    Estamos a oferecer dignidade, oportunidade e esperança.<br><br>
                    E 5.000 Kz por mês é pouco para quem ama seu filho o suficiente<br>
                    para investir nele todos os dias.
                </p>
            </div>
        </div>

        <!-- Slide 15: Conclusão -->
        <div class="slide" id="slide15">
            <div class="slide-content">
                <h1>OBRIGADO POR ACREDITAR NO FUTURO DOS NOSSOS FILHOS</h1>
                <div class="highlight-box">
                    <p style="font-size: 1.5em; line-height: 1.8;">
                        Agradecemos a sua presença, a sua atenção e, acima de tudo, o seu amor de pai/mãe — esse amor que move montanhas e transforma realidades.
                    </p>
                </div>
                <div class="highlight-box" style="margin-top: 30px; background: linear-gradient(135deg, var(--accent) 0%, #ff9800 100%); color: var(--primary);">
                    <p style="font-size: 1.6em; font-weight: 600;">Este projecto só existe porque:</p>
                </div>
                <ul style="margin-top: 30px;">
                    <li><i class="fas fa-heart"></i> <strong>A escola</strong> acredita na educação como motor de transformação nacional</li>
                    <li><i class="fas fa-heart"></i> <strong>A LMB</strong> acredita no potencial imenso das crianças angolanas</li>
                    <li><i class="fas fa-heart"></i> <strong>Você</strong> acredita no seu filho — e está disposto a dar-lhe as ferramentas para voar</li>
                </ul>
                <div class="highlight-box" style="margin-top: 40px; background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%); color: white;">
                    <p style="font-size: 1.6em; font-weight: 600; line-height: 1.8;">
                        Juntos, vamos construir mais do que uma Sala Digital.<br>
                        Vamos construir a geração que vai levar Angola mais longe — com competência, orgulho e visão.
                    </p>
                </div>
                <p class="quote" style="font-size: 1.3em; line-height: 1.8;">
                    O filho que hoje aprende com tecnologia na escola<br>
                    será o engenheiro que amanhã constrói estradas em Malanje,<br>
                    o médico que cura com dignidade em Menongue,<br>
                    o professor que inspira novas gerações em Luena,<br>
                    o empreendedor que cria empregos e riqueza em Luanda,<br>
                    o agricultor que alimenta o país com inovação no Huambo.<br><br>
                    <strong>Este é o futuro que estamos a construir — juntos.</strong>
                </p>
            </div>
        </div>

        <!-- Slide 16: Contato -->
        <div class="slide" id="slide16">
            <div class="slide-content">
                <h1>Informações práticas e contacto</h1>
                <div class="contact-info">
                    <h3><i class="fas fa-calendar-alt"></i> Próximos passos</h3>
                    <p><i class="fas fa-dot-circle"></i> <strong>Inauguração da Sala Digital:</strong> 15 de Março de 2026</p>
                    <p><i class="fas fa-dot-circle"></i> <strong>Primeiras aulas práticas:</strong> 22 de Março de 2026</p>
                    <p><i class="fas fa-dot-circle"></i> <strong>Dia de portas abertas para pais:</strong> 29 de Março de 2026</p>
                    
                    <h3 style="margin-top: 30px;"><i class="fas fa-handshake"></i> Parceria responsável</h3>
                    <p><i class="fas fa-school"></i> <strong>Escola:</strong> Complexo Escolar Tatiana - Céu Azul</p>
                    <p><i class="fas fa-laptop-code"></i> <strong>Parceiro tecnológico:</strong> LMB – Soluções Tecnológicas</p>
                    <p><i class="fas fa-cogs"></i> <strong>Âmbito:</strong> Infraestrutura, manutenção e conectividade Internet dedicada</p>
                    
                    <h3 style="margin-top: 30px;"><i class="fas fa-phone"></i> Contactos</h3>
                    <p><i class="fas fa-building"></i> <strong>Secretaria da Escola:</strong> xxxxxxxxx | info@lmbservices.com</p>
                    <p><i class="fas fa-user-tie"></i> <strong>Director(a):</strong> JJJJJ] – Tel. 923 xxx xxx</p>
                    <p><i class="fas fa-user-graduate"></i> <strong>Coordenador do Projecto:</strong> Cristao Cabunga – Telefone/WhatsApp: 923385314</p>
                </div>
                <p class="quote" style="font-size: 1.5em; line-height: 1.8; margin-top: 30px;">
                    Não deixemos que a hesitação de hoje<br>
                    se transforme no arrependimento de amanhã.<br><br>
                    O futuro dos nossos filhos não espera —<br>
                    e nós não podemos falhar com eles.
                </p>
            </div>
        </div>
    </div>

    <div class="slide-counter" id="slideCounter">Slide 1 de 16</div>

    <div class="dots-container" id="dotsContainer"></div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const totalSlides = 16;
            let currentSlide = 1;

            // Criar dots de navegação
            const dotsContainer = document.getElementById('dotsContainer');
            for (let i = 1; i <= totalSlides; i++) {
                const dot = document.createElement('div');
                dot.className = 'dot';
                dot.dataset.slide = i;
                dot.addEventListener('click', () => goToSlide(i));
                dotsContainer.appendChild(dot);
            }

            // Atualizar UI inicial
            updateUI();

            // Função para ir para slide específico
            function goToSlide(slideNumber) {
                if (slideNumber < 1 || slideNumber > totalSlides) return;
                
                // Remover classes dos slides antigos
                document.querySelectorAll('.slide').forEach(slide => {
                    slide.classList.remove('active', 'prev', 'next');
                });

                // Adicionar classes de transição
                if (slideNumber > currentSlide) {
                    document.getElementById(`slide${currentSlide}`).classList.add('prev');
                } else if (slideNumber < currentSlide) {
                    document.getElementById(`slide${currentSlide}`).classList.add('next');
                }

                // Mostrar novo slide
                document.getElementById(`slide${slideNumber}`).classList.add('active');
                
                currentSlide = slideNumber;
                updateUI();
                
                // Rolar suavemente para o topo
                window.scrollTo({ top: 0, behavior: 'smooth' });
            }

            // Função para próximo slide
            function nextSlide() {
                if (currentSlide < totalSlides) {
                    goToSlide(currentSlide + 1);
                }
            }

            // Função para slide anterior
            function prevSlide() {
                if (currentSlide > 1) {
                    goToSlide(currentSlide - 1);
                }
            }

            // Atualizar UI (contador, dots, botões)
            function updateUI() {
                document.getElementById('slideCounter').textContent = `Slide ${currentSlide} de ${totalSlides}`;
                
                // Atualizar dots
                document.querySelectorAll('.dot').forEach((dot, index) => {
                    dot.classList.toggle('active', index + 1 === currentSlide);
                });
                
                // Atualizar barra de progresso
                const progress = ((currentSlide - 1) / (totalSlides - 1)) * 100;
                document.getElementById('progressBar').style.width = `${progress}%`;
            }

            // Navegação por teclado
            document.addEventListener('keydown', function(e) {
                if (e.key === 'ArrowLeft' || e.key === 'ArrowUp' || e.key === 'PageUp') {
                    prevSlide();
                } else if (e.key === 'ArrowRight' || e.key === 'ArrowDown' || e.key === ' ' || e.key === 'PageDown') {
                    nextSlide();
                } else if (e.key === 'Home') {
                    goToSlide(1);
                } else if (e.key === 'End') {
                    goToSlide(totalSlides);
                } else if (e.key >= '1' && e.key <= '9') {
                    const slideNum = parseInt(e.key);
                    if (slideNum <= totalSlides) {
                        goToSlide(slideNum);
                    }
                }
            });

            // Swipe para mobile
            let touchStartX = 0;
            let touchEndX = 0;

            document.addEventListener('touchstart', function(e) {
                touchStartX = e.changedTouches[0].screenX;
            });

            document.addEventListener('touchend', function(e) {
                touchEndX = e.changedTouches[0].screenX;
                handleSwipe();
            });

            function handleSwipe() {
                const swipeThreshold = 50;
                if (touchStartX - touchEndX > swipeThreshold) {
                    nextSlide();
                } else if (touchEndX - touchStartX > swipeThreshold) {
                    prevSlide();
                }
            }

            // Iniciar apresentação
            goToSlide(1);
        });
    </script>
</body>
</html>
