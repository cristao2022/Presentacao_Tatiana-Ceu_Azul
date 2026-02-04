<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sala Digital - Pais Angola</title>
    <style>
        body { 
            font-family: Arial, sans-serif; 
            margin: 0; padding: 0; 
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%); 
            color: #333; 
        }
        .slide { 
            height: 100vh; 
            padding: 40px; 
            display: none; 
            justify-content: center; 
            align-items: center; 
            text-align: center; 
            color: white; 
            font-size: 1.4em; 
        }
        .slide.active { display: flex; flex-direction: column; }
        .slide h1 { font-size: 3.2em; margin-bottom: 25px; color: #fff; text-shadow: 3px 3px 6px rgba(0,0,0,0.6); }
        .slide h2 { font-size: 2.3em; margin-bottom: 25px; color: #f4f4f4; }
        .slide h3 { font-size: 1.9em; margin: 25px 0; color: #ffd700; }
        .slide p { max-width: 850px; line-height: 1.7; margin-bottom: 20px; font-weight: 500; }
        blockquote { 
            font-style: italic; font-size: 1.3em; 
            border-left: 6px solid #ffd700; 
            padding: 25px; 
            background: rgba(255,215,0,0.1); 
            margin: 30px 0; 
            max-width: 700px; 
        }
        ul { text-align: left; max-width: 750px; font-size: 1.25em; }
        li { margin: 18px 0; padding-left: 25px; position: relative; }
        li:before { 
            content: "✨"; position: absolute; left: 0; 
            font-size: 1.5em; color: #ffd700; 
        }
        .comparison { 
            display: grid; grid-template-columns: 1fr 1fr; 
            gap: 50px; max-width: 1000px; margin: 40px 0; 
        }
        .comp-item { 
            background: rgba(255,255,255,0.15); 
            padding: 35px; border-radius: 20px; 
            backdrop-filter: blur(10px); 
        }
        .comp-item h3 { margin-top: 0; }
        .antes { border-left: 6px solid #ff6b6b; color: #ff6b6b; }
        .depois { border-left: 6px solid #51cf66; color: #51cf66; }
        button { 
            position: fixed; bottom: 60px; 
            padding: 18px 35px; font-size: 1.3em; 
            border: none; border-radius: 35px; 
            background: rgba(255,255,255,0.95); 
            cursor: pointer; margin: 0 25px; 
            font-weight: bold; box-shadow: 0 8px 25px rgba(0,0,0,0.3);
        }
        button:hover:not(:disabled) { 
            background: #ffd700; color: #1e3c72; transform: scale(1.08); 
        }
        button:disabled { opacity: 0.5; cursor: not-allowed; }
        #prev { left: 60px; }
        #next { right: 60px; }
        .counter { 
            position: fixed; top: 30px; 
            left: 50%; transform: translateX(-50%); 
            background: rgba(0,0,0,0.7); color: #ffd700; 
            padding: 15px 30px; border-radius: 30px; 
            font-size: 1.3em; font-weight: bold; 
        }
        .highlight { 
            background: linear-gradient(135deg, #ffd700, #ffed4a); 
            color: #1e3c72; padding: 30px 40px; 
            border-radius: 25px; margin: 30px 0; 
            font-size: 1.45em; font-weight: bold; 
            box-shadow: 0 10px 30px rgba(255,215,0,0.4);
        }
        .contact-box { 
            background: rgba(255,255,255,0.2); 
            padding: 40px; border-radius: 25px; 
            backdrop-filter: blur(15px); max-width: 800px; 
        }
    </style>
</head>
<body>
    <div class="counter" id="counter">1 / 16</div>
    
    <!-- SLIDE 1: CAPA PODEROSA -->
    <div class="slide active" id="slide1">
        <h1>🇦🇴 O FUTURO DE ANGOLA</h1>
        <h2>COMEÇA NA NOSSA SALA DE AULA</h2>
        <blockquote>
            "Não formamos apenas alunos.<br>
            <strong>Formamos ENGENHEIROS, MÉDICOS,<br>
            PROFESSORES e LÍDERES</strong><br>
            que vão RECONSTRUIR Angola."
        </blockquote>
        <p style="font-size: 1.3em;">[Nome da Escola] | Luanda | Fevereiro 2026</p>
    </div>

    <!-- SLIDE 2: EMOÇÃO PAI ANGOLANO -->
    <div class="slide" id="slide2">
        <h1>"Quero MAIS para meu filho"</h1>
        <p>Você cresceu na guerra ou na reconstrução.<br>
        <strong>Livros velhos. Professoras sobrecarregadas. Sonhos adiados.</strong></p>
        <div class="highlight">
            HOJE Angola tem ESTRADAS, ELECTRICIDADE, INTERNET.<br>
            <strong>MAIS as escolas precisam dar o SALTO!</strong>
        </div>
        <p style="font-size: 1.6em; color: #ffd700;">
            Seu filho merece o SÉCULO XXI!
        </p>
    </div>

    <!-- SLIDE 3: DEFINIÇÃO CLARA -->
    <div class="slide" id="slide3">
        <h1>Sala Digital = JANELAS para o MUNDO</h1>
        <ul>
            <li>🌍 <strong>Rio Cuanza VISTO DO ESPAÇO</strong></li>
            <li>🦁 <strong>Elefantes do Cuando Cubango em HD</strong></li>
            <li>📚 <strong>10.000 LIVROS GRÁTIS</strong> (Pepetela incluso!)</li>
            <li>🎯 <strong>FERRAMENTAS da UNIVERSIDADE</strong></li>
        </ul>
        <blockquote>
            vCloudPoint: 20 alunos = 1 servidor.<br>
            <strong>ESTÁVEL • SEGURO • BARATO na electricidade angolana.
        </blockquote>
    </div>

    <!-- SLIDE 4: COMPARAÇÃO IMPACTANTE -->
    <div class="slide" id="slide4">
        <h1>ANTES vs DEPOIS</h1>
        <div class="comparison">
            <div class="comp-item antes">
                <h3>🚫 SEM Sala Digital</h3>
                <p><strong>Petróleo:</strong> lê em livro de 1995</p>
                <p><strong>Mapas:</strong> desenha à mão</p>
                <p><strong>Livros:</strong> espera 6 meses</p>
            </div>
            <div class="comp-item depois">
                <h3>✅ COM Sala Digital</h3>
                <p><strong>Petróleo:</strong> PLATAFORMA 3D interativa</p>
                <p><strong>Mapas:</strong> ZOOM nas 18 províncias</p>
                <p><strong>Livros:</strong> 10.000 INSTANTES</p>
            </div>
        </div>
    </div>

    <!-- SLIDE 5: MERCADO DE TRABALHO -->
    <div class="slide" id="slide5">
        <h1>🚀 Empregos que Angola PRECISA</h1>
        <div class="highlight">
            PETRÓLEO • MINAS • AGRICULTURA • TURISMO • STARTUPS
        </div>
        <ul>
            <li>💼 Relatórios técnicos (Sonangol)</li>
            <li>🌾 Apps para milho/mandioca</li>
            <li>🏞️ Sites das Quedas de Kalandula</li>
            <li>💻 Negócios online (Kwanzas!)</li>
        </ul>
    </div>

    <!-- SLIDE 6: EXEMPLO PRÁTICO -->
    <div class="slide" id="slide6">
        <h1>SEU FILHO VAI FAZER ISTO</h1>
        <ul>
            <li>🗺️ <strong>Geografia:</strong> Luanda 1990 vs 2026 (SATÉLITE)</li>
            <li>📜 <strong>História:</strong> Heróis independência em VÍDEO</li>
            <li>🔬 <strong>Ciências:</strong> Mandioca no Huambo (SIMULAÇÃO)</li>
            <li>🎙️ <strong>Português:</strong> PODCAST lenda Kimbo/Kiluange</li>
        </ul>
    </div>

    <!-- SLIDE 7: IGUALDADE -->
    <div class="slide" id="slide7">
        <h1>🇦🇴 JUSTIÇA SOCIAL</h1>
        <div class="highlight" style="font-size: 2.2em;">
            Filho do MOTORISTA = Filho do DIRECTOR
        </div>
        <ul>
            <li>🏘️ Musseque Prenda → MESMO acesso</li>
            <li>🌾 Roça interior → MESMA tecnologia</li>
            <li>💰 Sem computador casa → NÃO importa</li>
        </ul>
    </div>

    <!-- SLIDE 8: UNIVERSIDADE -->
    <div class="slide" id="slide8">
        <h1>🎓 ENTRAR na UNIVERSIDADE</h1>
        <ul>
            <li>✅ UAN, UP, UÍ: trabalhos Word perfeitos</li>
            <li>✅ Moodle: entregas ONLINE</li>
            <li>✅ PowerPoint: apresentações PRO</li>
            <li>❌ Sem prática = VERGONHA no 1º ano</li>
        </ul>
        <p style="font-size: 1.8em; color: #ff6b6b;">
            <strong>5.000 Kz/mês SALVA sonhos!</strong>
        </p>
    </div>

    <!-- SLIDE 9: SEGURANÇA -->
    <div class="slide" id="slide9">
        <h1>👨‍👩‍👧‍👦 VALORES FAMILIARES</h1>
        <ul>
            <li>🛡️ PROFESSOR controla TUDO</li>
            <li>🇦🇴 ÚMBUNDU • KIMBUNDU • HISTÓRIA</li>
            <li>🚫 WhatsApp/Instagram PROIBIDO</li>
            <li>✅ Respeito aos mais velhos</li>
        </ul>
    </div>

    <!-- SLIDE 10: ÁFRICA -->
    <div class="slide" id="slide10">
        <h1>🌍 ÁFRICA que VENCEU</h1>
        <ul>
            <li>🇷🇼 Ruanda: #1 tecnologia África</li>
            <li>🇰🇪 Quénia: 1,2MILHÕES digitais</li>
            <li>🇬🇭 Gana: startups = MILHÕES USD</li>
        </ul>
        <div class="highlight" style="font-size: 2.5em;">
            🇦🇴 ANGOLA = PRÓXIMO LÍDER!
        </div>
    </div>

    <!-- SLIDE 11: TESTEMUNHO REAL -->
    <div class="slide" id="slide11">
        <h1>VOZ de MÃE LUANDINA</h1>
        <blockquote style="font-size: 1.5em;">
            "Quitandeira Roque Santeiro, 5h da manhã.<br>
            <strong>SEM computador casa.</strong><br>
            Sala Digital = <strong>MEU FILHO TEM FUTURO!</strong><br>
            Chorei quando soube."
            <br><small>— Mãe, 6º ano</small>
        </blockquote>
    </div>

    <!-- SLIDE 12: PARCERIA -->
    <div class="slide" id="slide12">
        <h1>🤝 COMO FUNCIONA</h1>
        <ul style="font-size: 1.4em;">
            <li>💰 <strong>LMB paga TUDO</strong> (servidores + instalação)</li>
            <li>🏫 <strong>Escola dá ESPAÇO</strong></li>
            <li>👨‍👩‍👧‍👦 <strong>Você: 5.000 Kz/mês</strong></li>
        </ul>
        <div class="highlight">
            <strong>5.000 Kz = 167 Kz/DIA</strong><br>
            Menos que 1 pão + café!
        </div>
    </div>

    <!-- SLIDE 13: SOLIDARIEDADE -->
    <div class="slide" id="slide13">
        <h1>❤️ NINGUÉM FORA</h1>
        <p style="font-size: 3.5em; margin-bottom: 50px;">
            SOLIDARIEDADE ANGOLANA
        </p>
        <p style="font-size: 2em;">
            5.000 Kz é para TODOS.<br>
            <strong>Família em dificuldade? FALA connosco.</strong>
        </p>
    </div>

    <!-- SLIDE 14: DECISÃO FINAL -->
    <div class="slide" id="slide14">
        <h1>HOJE VOCÊ ESCOLHE</h1>
        <div class="comparison">
            <div class="comp-item antes">
                <h3 style="font-size: 2em;">❌ "Vou pensar..."</h3>
                <p>Filho SEM tecnologia</p>
                <p>Universidade = VERGONHA</p>
                <p>Emprego = IMPOSSÍVEL</p>
            </div>
            <div class="comp-item depois">
                <h3 style="font-size: 2em;">✅ "5.000 Kz/mês"</h3>
                <p>Sonangol • UP • Startups</p>
                <p>ORGULHO angolano</p>
                <p>FUTURO GARANTIDO</p>
            </div>
        </div>
    </div>

    <!-- SLIDE 15: CONCLUSÃO ÉPICA -->
    <div class="slide" id="slide15">
        <h1>OBRIGADO PAI/ MÃE!</h1>
        <div class="highlight" style="font-size: 1.6em;">
            Seu "SIM" cria:<br>
            🛣️ Engenheiro em Malanje<br>
            🩺 Médico em Menongue<br>
            👨‍🏫 Professor em Luena<br>
            💼 Empreendedor em Luanda
        </div>
    </div>

    <!-- SLIDE 16: ACÇÃO IMEDIATA -->
    <div class="slide" id="slide16">
        <div class="contact-box">
            <h1 style="color: #1e3c72;">📅 PLANO</h1>
            <h3>15 MAR: INAUGURAÇÃO</h3>
            <h3>22 MAR: AULAS começam</h3>
            <h3>29 MAR: VOCÊ visita!</h3>
            
            <h2 style="color: #ff6b6b; margin-top: 30px;">📞 AGORA</h2>
            <p style="font-size: 1.6em;">
                Director: [Telefone]<br>
                Coordenador: WhatsApp [Número]
            </p>
            <blockquote style="color: #1e3c72;">
                "5.000 Kz/mês = FILHO NO TOPO.<br>
                Hesitar = arrependimento eterno."
            </blockquote>
        </div>
    </div>

    <button id="prev">◀ ANTERIOR</button>
    <button id="next">PRÓXIMO ▶</button>

    <script>
        let current = 1;
        const total = 16;
        
        function updateSlide() {
            for(let i=1; i<=total; i++) {
                document.getElementById('slide'+i).classList.toggle('active', i===current);
            }
            document.getElementById('counter').innerHTML = current + ' / ' + total;
        }
        
        document.getElementById('prev').onclick = () => {
            if(current > 1) { current--; updateSlide(); }
        };
        
        document.getElementById('next').onclick = () => {
            if(current < total) { current++; updateSlide(); }
        };
        
        document.onkeydown = (e) => {
            if(e.key=='ArrowLeft' && current>1) { current--; updateSlide(); }
            if(e.key=='ArrowRight' && current<total) { current++; updateSlide(); }
        };
        
        // Mobile swipe
        let startX=0;
        document.addEventListener('touchstart', e=>startX=e.touches[0].clientX);
        document.addEventListener('touchend', e=>{
            let endX = e.changedTouches[0].clientX;
            if(startX-endX>60) document.getElementById('next').click();
            if(endX-startX>60) document.getElementById('prev').click();
        });
        
        updateSlide();
    </script>
</body>
</html>

