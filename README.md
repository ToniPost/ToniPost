<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toni Postis - Full Stack Developer | IA | Redes Neuronales</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #0d0d0d;
            color: #c9d1d9;
            font-family: 'Segoe UI', 'Space Mono', 'Courier New', monospace;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Canvas de fondo para la red neuronal */
        #neuralCanvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
            opacity: 0.2;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header */
        .header {
            text-align: center;
            padding: 40px 0;
            border-bottom: 1px solid rgba(0, 229, 255, 0.3);
            margin-bottom: 30px;
        }

        h1 {
            font-size: 72px;
            color: #ffffff;
            text-shadow: 0 0 20px rgba(0, 229, 255, 0.5);
            letter-spacing: 4px;
        }

        /* Tablas */
        .stack-table {
            width: 100%;
            margin: 30px 0;
            background: rgba(13, 13, 13, 0.8);
            border-radius: 10px;
            border: 1px solid rgba(0, 229, 255, 0.2);
        }

        .stack-table td {
            padding: 20px;
            vertical-align: top;
            border-right: 1px solid rgba(0, 229, 255, 0.1);
        }

        .stack-table td:last-child {
            border-right: none;
        }

        .badge {
            display: inline-block;
            background: #1a1a1a;
            color: #00e5ff;
            padding: 5px 12px;
            margin: 3px;
            border-radius: 20px;
            font-size: 12px;
            text-decoration: none;
            transition: all 0.3s ease;
        }

        .badge:hover {
            transform: translateY(-2px);
            box-shadow: 0 0 15px rgba(0, 229, 255, 0.3);
        }

        .project-table, .metrics-table, .neuron-table, .modules-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        .project-table th, .project-table td,
        .metrics-table th, .metrics-table td,
        .neuron-table th, .neuron-table td,
        .modules-table th, .modules-table td {
            border: 1px solid rgba(0, 229, 255, 0.2);
            padding: 12px;
            text-align: left;
        }

        .project-table th, .metrics-table th, .neuron-table th, .modules-table th {
            background: rgba(0, 229, 255, 0.1);
            color: #00e5ff;
        }

        .neuron-diagram {
            background: #0a0a0a;
            padding: 20px;
            border-radius: 10px;
            font-family: monospace;
            font-size: 12px;
            text-align: center;
            margin: 20px 0;
            border: 1px solid rgba(0, 229, 255, 0.3);
            overflow-x: auto;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
            margin: 30px 0;
        }

        .social-link {
            background: #1a1a1a;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            color: #00e5ff;
            transition: all 0.3s ease;
        }

        .social-link:hover {
            background: #00e5ff;
            color: #0d0d0d;
            transform: translateY(-3px);
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.5);
        }

        hr {
            border-color: rgba(0, 229, 255, 0.2);
            margin: 30px 0;
        }

        img[align="right"] {
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 229, 255, 0.2);
        }

        code {
            color: #00e5ff;
        }

        blockquote {
            border-left: 3px solid #00e5ff;
            padding-left: 20px;
            margin: 20px 0;
            color: #aaa;
        }

        h2, h3 {
            color: #00e5ff;
            margin-top: 30px;
        }

        a {
            color: #00e5ff;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>

<canvas id="neuralCanvas"></canvas>

<div class="container">
    <div class="header">
        <img src="https://capsule-render.vercel.app/api?type=cylinder&color=0:0d0d0d,100:0d0d0d&height=120&section=header&text=TONI%20POSTIS&fontSize=72&fontColor=ffffff&fontAlignY=55&desc=Full%20Stack%20%E2%80%94%20Mobile%20%E2%80%94%20Cloud%20%E2%80%94%20AI&descAlignY=80&descSize=16&animation=blinking&stroke=00e5ff&strokeWidth=2" width="100%"/>
        <br/><br/>
        <img src="https://readme-typing-svg.demolab.com?font=Space+Mono&weight=700&size=18&pause=2000&color=00E5FF&center=true&vCenter=true&width=700&lines=Building+products+people+actually+use.;7%2B+years+%E2%80%94+50%2B+projects+%E2%80%94+0+compromises.;Flutter+%2B+Python+%2B+React+%2B+Cloud.;From+idea+to+deploy%2C+end+to+end." alt="Typing SVG"/>
    </div>

    <img align="right" height="230" src="https://raw.githubusercontent.com/gist/patevs/b007a0e98078b3c0e7904068c8e8e044/raw/88f20c9d749d756be63f22b09f3c4ac570bc5101/programming.gif"/>

    <h3>Hola, soy <strong>Toni</strong> 👋</h3>
    <p>Desarrollador full stack con <strong>+7 años</strong> creando productos digitales que van desde la primera línea de código hasta producción.</p>
    <p>Me muevo igual de bien en el <strong>backend</strong> que en el <strong>frontend</strong>, en <strong>mobile</strong> que en <strong>cloud</strong>. No busco ser el experto de una sola herramienta — busco entregar resultados.</p>
    <p>Trabajo con startups y empresas en todo el mundo para construir:</p>
    <ul>
        <li>📱 <strong>Apps móviles</strong> con Flutter que se sienten nativas</li>
        <li>🌐 <strong>Plataformas web</strong> con React + Node.js / Django</li>
        <li>🤖 <strong>Integraciones de IA</strong> con OpenAI, TensorFlow y más</li>
        <li>☁️ <strong>Infraestructura cloud</strong> escalable en AWS, Azure y GCP</li>
    </ul>
    <blockquote><em>"No solo escribo código — diseño soluciones, anticipo problemas y entrego experiencias."</em></blockquote>

    <br clear="right"/>
    <hr/>

    <h2>⚡ Stack</h2>
    <table class="stack-table">
        <tr>
            <td valign="top" width="33%">
                <strong>Lenguajes</strong><br/><br/>
                <code>Python      ████████████  Expert</code><br/>
                <code>JavaScript  ████████████  Expert</code><br/>
                <code>Dart        ████████████  Expert</code><br/>
                <code>Kotlin      ████████░░░░  Advanced</code><br/>
                <code>Java        ████████░░░░  Advanced</code><br/>
                <code>C++         ██████░░░░░░  Mid</code><br/>
                <code>PHP         ██████░░░░░░  Mid</code>
            </td>
            <td valign="top" width="33%">
                <strong>Frontend & Mobile</strong><br/><br/>
                <img src="https://img.shields.io/badge/Flutter-0d0d0d?style=flat-square&logo=Flutter&logoColor=00e5ff"/><br/>
                <img src="https://img.shields.io/badge/React-0d0d0d?style=flat-square&logo=react&logoColor=61DAFB"/><br/>
                <img src="https://img.shields.io/badge/React_Native-0d0d0d?style=flat-square&logo=react&logoColor=61DAFB"/><br/>
                <img src="https://img.shields.io/badge/Angular-0d0d0d?style=flat-square&logo=angular&logoColor=DD0031"/><br/>
                <img src="https://img.shields.io/badge/HTML5-0d0d0d?style=flat-square&logo=html5&logoColor=E34F26"/><br/>
                <img src="https://img.shields.io/badge/CSS3-0d0d0d?style=flat-square&logo=css3&logoColor=1572B6"/><br/>
                <img src="https://img.shields.io/badge/.NET-0d0d0d?style=flat-square&logo=dotnet&logoColor=9B59B6"/>
            </td>
            <td valign="top" width="33%">
                <strong>Backend & Bases de Datos</strong><br/><br/>
                <img src="https://img.shields.io/badge/Node.js-0d0d0d?style=flat-square&logo=node.js&logoColor=6DA55F"/><br/>
                <img src="https://img.shields.io/badge/Django-0d0d0d?style=flat-square&logo=django&logoColor=00e5ff"/><br/>
                <img src="https://img.shields.io/badge/PostgreSQL-0d0d0d?style=flat-square&logo=postgresql&logoColor=4169E1"/><br/>
                <img src="https://img.shields.io/badge/MongoDB-0d0d0d?style=flat-square&logo=mongodb&logoColor=47A248"/><br/>
                <img src="https://img.shields.io/badge/MySQL-0d0d0d?style=flat-square&logo=mysql&logoColor=00e5ff"/><br/>
                <img src="https://img.shields.io/badge/Firebase-0d0d0d?style=flat-square&logo=firebase&logoColor=FFCA28"/><br/>
                <img src="https://img.shields.io/badge/Redis-0d0d0d?style=flat-square&logo=redis&logoColor=DC382D"/>
            </td>
        </tr>
        <tr>
            <td valign="top">
                <strong>Cloud & DevOps</strong><br/><br/>
                <img src="https://img.shields.io/badge/AWS-0d0d0d?style=flat-square&logo=amazon-aws&logoColor=FF9900"/><br/>
                <img src="https://img.shields.io/badge/Azure-0d0d0d?style=flat-square&logo=microsoftazure&logoColor=0072C6"/><br/>
                <img src="https://img.shields.io/badge/GCP-0d0d0d?style=flat-square&logo=google-cloud&logoColor=4285F4"/><br/>
                <img src="https://img.shields.io/badge/Docker-0d0d0d?style=flat-square&logo=docker&logoColor=2496ED"/><br/>
                <img src="https://img.shields.io/badge/Oracle_Cloud-0d0d0d?style=flat-square&logo=oracle&logoColor=F80000"/>
            </td>
            <td valign="top">
                <strong>IA & Data</strong><br/><br/>
                <img src="https://img.shields.io/badge/OpenAI-0d0d0d?style=flat-square&logo=openai&logoColor=ffffff"/><br/>
                <img src="https://img.shields.io/badge/TensorFlow-0d0d0d?style=flat-square&logo=tensorflow&logoColor=FF6F00"/><br/>
                <img src="https://img.shields.io/badge/PyTorch-0d0d0d?style=flat-square&logo=pytorch&logoColor=EE4C2C"/><br/>
                <img src="https://img.shields.io/badge/OpenCV-0d0d0d?style=flat-square&logo=opencv&logoColor=5C3EE8"/><br/>
                <img src="https://img.shields.io/badge/Pandas-0d0d0d?style=flat-square&logo=pandas&logoColor=150458"/><br/>
                <img src="https://img.shields.io/badge/Keras-0d0d0d?style=flat-square&logo=keras&logoColor=D00000"/><br/>
                <img src="https://img.shields.io/badge/Groq-0d0d0d?style=flat-square&logo=groq&logoColor=00e5ff"/>
            </td>
            <td valign="top">
                <strong>Diseño & Herramientas</strong><br/><br/>
                <img src="https://img.shields.io/badge/Figma-0d0d0d?style=flat-square&logo=figma&logoColor=F24E1E"/><br/>
                <img src="https://img.shields.io/badge/Adobe_XD-0d0d0d?style=flat-square&logo=adobe-xd&logoColor=FF61F6"/><br/>
                <img src="https://img.shields.io/badge/Blender-0d0d0d?style=flat-square&logo=blender&logoColor=F5792A"/><br/>
                <img src="https://img.shields.io/badge/Photoshop-0d0d0d?style=flat-square&logo=adobephotoshop&logoColor=31A8FF"/><br/>
                <img src="https://img.shields.io/badge/After_Effects-0d0d0d?style=flat-square&logo=adobeaftereffects&logoColor=9999FF"/><br/>
                <img src="https://img.shields.io/badge/n8n-0d0d0d?style=flat-square&logo=n8n&logoColor=EA4B71"/>
            </td>
        </tr>
    </table>

    <hr/>

    <h2>🚀 Proyectos Destacados</h2>
    <table class="project-table">
        <thead>
            <tr><th>Proyecto</th><th>Stack</th><th>Descripción</th></tr>
        </thead>
        <tbody>
            <tr><td>🏠 <strong>App Inmobiliaria</strong></td><td><code>Flutter</code> <code>Firebase</code> <code>IA</code></td><td>Búsqueda inteligente de propiedades con recomendaciones por IA</td></tr>
            <tr><td>🛒 <strong>E-Commerce Platform</strong></td><td><code>React</code> <code>Node.js</code> <code>Stripe</code></td><td>Plataforma completa de ventas con pagos y gestión de inventario</td></tr>
            <tr><td>🤖 <strong>Chatbot WhatsApp</strong></td><td><code>Python</code> <code>OpenAI</code> <code>API</code></td><td>Asistente conversacional integrado en WhatsApp para negocios</td></tr>
            <tr><td>📊 <strong>Analytics Dashboard</strong></td><td><code>Django</code> <code>React</code> <code>AWS</code></td><td>Panel de métricas en tiempo real con visualizaciones avanzadas</td></tr>
            <tr><td>🎮 <strong>AR Experience</strong></td><td><code>Flutter</code> <code>ARKit</code> <code>ARCore</code></td><td>Realidad aumentada multiplataforma para catálogos de producto</td></tr>
            <tr><td>🎬 <strong>Editor de Video IA</strong></td><td><code>Python</code> <code>FFmpeg</code> <code>TensorFlow</code></td><td>Edición automática de video con inteligencia artificial</td></tr>
            <tr><td>🧠 <strong>InnovaIA</strong></td><td><code>Node.js</code> <code>Python</code> <code>React</code> <code>n8n</code> <code>GPT-4</code> <code>Groq</code></td><td>Agencia de automatización con IA para negocios</td></tr>
            <tr><td>🥗 <strong>Innova Food Studio</strong></td><td><code>Flutter</code> <code>IA</code> <code>Android</code></td><td>App de escaneo de alimentos con alertas sanitarias</td></tr>
            <tr><td>📺 <strong>Innova ViralPro</strong></td><td><code>JavaScript</code> <code>Groq</code> <code>LLaMA 3.3</code></td><td>Suite de inteligencia para YouTubers</td></tr>
        </tbody>
    </table>

    <hr/>

    <h2>🧠 InnovaIA — Ecosistema Propio</h2>
    <blockquote><p>Fundador y desarrollador de <strong><a href="https://innovaia.org">InnovaIA</a></strong> — plataforma de inteligencia artificial aplicada a negocios reales.</p></blockquote>

    <table class="metrics-table">
        <thead><tr><th>Métrica</th><th>Resultado</th></tr></thead>
        <tbody>
            <tr><td>⚡ Reducción tareas manuales</td><td>−60% en el primer mes</td></tr>
            <tr><td>📈 Aumento en conversiones</td><td>+35% con funnels IA</td></tr>
            <tr><td>🕐 Atención automatizada</td><td>24/7 sin intervención humana</td></tr>
            <tr><td>🚀 Velocidad de análisis</td><td>×3 vs equipos manuales</td></tr>
        </tbody>
    </table>

    <p>InnovaIA diseña e implementa tres líneas de soluciones de IA:</p>
    <p><strong>01 — Asistentes & Chatbots Expertos</strong><br/>Bots entrenados con la documentación, productos y FAQs del cliente. Atención al cliente, soporte técnico, ventas y onboarding automatizados en WhatsApp, Web y Telegram.</p>
    <p><strong>02 — Paneles de Datos & Alertas</strong><br/>Dashboards únicos que consolidan métricas de todas las plataformas con alertas inteligentes. Detección de anomalías en ventas, errores, tickets e inventario en tiempo real.</p>
    <p><strong>03 — Automatización de Procesos</strong><br/>Flujos conectados con Stripe, WooCommerce, Google Sheets, n8n y APIs internas: facturación automática, emails personalizados, segmentación y scoring de clientes.</p>

    <hr/>

    <h3>🧬 Redes Neuronales — El motor invisible</h3>
    <p>InnovaIA no usa IA genérica. Cada solución está construida sobre <strong>redes neuronales personalizadas</strong>, entrenadas con datos reales del negocio y optimizadas para casos de uso concretos:</p>

    <table class="neuron-table">
        <thead><tr><th>Arquitectura</th><th>Aplicación</th><th>Producto</th></tr></thead>
        <tbody>
            <tr><td>🖼️ <strong>CNN</strong> (Convolucionales)</td><td>Procesamiento de imágenes, detección de patrones visuales</td><td>Innova Food Studio</td></tr>
            <tr><td>🔄 <strong>Transformers</strong></td><td>Lenguaje natural, conversación con contexto</td><td>Asistentes IA</td></tr>
            <tr><td>📈 <strong>LSTM</strong> (Memoria a largo plazo)</td><td>Predicción de series temporales, forecasting</td><td>Paneles de datos</td></tr>
            <tr><td>🎬 <strong>CNN + LSTM</strong> (Híbridas)</td><td>Análisis de tendencias, comportamiento de audiencia</td><td>Innova ViralPro</td></tr>
            <tr><td>✍️ <strong>Generativas</strong> (LLaMA 3.3, GPT-4)</td><td>Creación de contenido, análisis semántico</td><td>Scripts, títulos, análisis</td></tr>
        </tbody>
    </table>

    <div class="neuron-diagram">
        <pre>
╔═══════════════════════════════════════════════════════════════╗
║                    ARQUITECTURA NEURONAL                       ║
╠═══════════════════════════════════════════════════════════════╣
║                                                               ║
║     INPUT LAYER          HIDDEN LAYERS        OUTPUT LAYER    ║
║    ┌──────┐            ┌──────┐             ┌──────┐         ║
║    │  ○───┼────────────┼──○───┼─────────────┼──○── │         ║
║    └──────┘      ╱     └──────┘      ╱      └──────┘         ║
║    ┌──────┐    ╱╲     ┌──────┐    ╱╲       ┌──────┐           ║
║    │  ○───┼──╱──╲─────┼──○───┼──╱──╲───────┼──○── │           ║
║    └──────┘  ╲  ╱     └──────┘  ╲  ╱       └──────┘           ║
║    ┌──────┐   ╲╱      ┌──────┐   ╲╱       ┌──────┐            ║
║    │  ○───┼────────────┼──○───┼────────────┼──○── │            ║
║    └──────┘            └──────┘            └──────┘            ║
║                                                               ║
║    Datos de     →    Procesamiento    →    Predicción         ║
║    entrada           multicapa             precisa            ║
║                                                               ║
╚═══════════════════════════════════════════════════════════════╝
        </pre>
    </div>

    <blockquote><p>El resultado: modelos que aprenden del negocio, no al revés. Cuantos más datos procesan, más precisos se vuelven.</p></blockquote>

    <hr/>

    <h3>📦 Productos lanzados bajo InnovaIA</h3>
    <hr/>

    <h3>🥗 Innova Food Studio — App Android</h3>
    <p>
        <a href="https://play.google.com/store/apps/details?id=org.antoniopostiguiillo.innovafoodstudio"><img src="https://img.shields.io/badge/Google_Play-0d0d0d?style=for-the-badge&logo=google-play&logoColor=00e5ff" alt="Google Play"/></a>
        <img src="https://img.shields.io/badge/Flutter-0d0d0d?style=flat-square&logo=Flutter&logoColor=00e5ff" alt="Flutter"/>
        <img src="https://img.shields.io/badge/Android-0d0d0d?style=flat-square&logo=android&logoColor=3DDC84" alt="Android"/>
        <img src="https://img.shields.io/badge/CNN-0d0d0d?style=flat-square&logo=tensorflow&logoColor=FF6F00" alt="CNN"/>
    </p>
    <p><strong>¿Para qué sirve?</strong><br/>Escaneás cualquier alimento con la cámara del móvil y la app te dice exactamente qué estás a punto de comer. Detecta alertas sanitarias oficiales activas, analiza ingredientes y aditivos, identifica alérgenos y genera un perfil de riesgo personalizado según tu historial.</p>
    <p><strong>🧠 Red Neuronal: CNN (Convolucional)</strong><br/>La app utiliza una red neuronal convolucional entrenada con más de 50,000 imágenes de etiquetas de alimentos. Capaz de reconocer texto, logos y patrones visuales en milisegundos, incluso con mala iluminación o ángulos difíciles.</p>
    <p><strong>Funciones principales:</strong></p>
    <ul>
        <li>📷 Escaneo rápido con cámara + CNN en tiempo real</li>
        <li>🚨 Detección de alertas sanitarias oficiales en tiempo real</li>
        <li>🧪 Análisis completo de ingredientes y aditivos</li>
        <li>⚠️ Identificación de alérgenos y componentes sensibles</li>
        <li>📋 Historial de productos escaneados</li>
        <li>👤 Revisión de riesgos según perfil personal</li>
    </ul>
    <blockquote><p>Ideal para personas con alergias, intolerancias, problemas de azúcar, colesterol elevado o quienes simplemente quieren saber qué están comiendo.</p></blockquote>

    <hr/>

    <h3>📺 Innova ViralPro — YouTube Intelligence Suite</h3>
    <p>
        <a href="https://innovaia.org/youtube"><img src="https://img.shields.io/badge/innovaia.org%2Fyoutube-0d0d0d?style=for-the-badge&logo=youtube&logoColor=FF0000" alt="Ver plataforma"/></a>
        <img src="https://img.shields.io/badge/JavaScript-0d0d0d?style=flat-square&logo=javascript&logoColor=F7DF1E" alt="JavaScript"/>
        <img src="https://img.shields.io/badge/Groq_LLaMA_3.3-0d0d0d?style=flat-square&logo=groq&logoColor=00e5ff" alt="Groq"/>
        <img src="https://img.shields.io/badge/YouTube_API_v3-0d0d0d?style=flat-square&logo=youtube&logoColor=FF0000" alt="YouTube API"/>
        <img src="https://img.shields.io/badge/LSTM-0d0d0d?style=flat-square&logo=tensorflow&logoColor=FF6F00" alt="LSTM"/>
    </p>
    <p><strong>¿Para qué sirve?</strong><br/>Suite completa de inteligencia para creadores de YouTube. Combina la YouTube Data API v3 con Groq (LLaMA 3.3 70B) para darte ventaja competitiva antes, durante y después de publicar un vídeo.</p>
    <p><strong>🧠 Redes Neuronales: LSTM + Híbridas</strong></p>
    <ul>
        <li><strong>LSTM</strong> → Predicción de CPM estacional y tendencias de viralidad</li>
        <li><strong>CNN + LSTM</strong> → Análisis de patrones de comportamiento de audiencia</li>
        <li><strong>Transformers</strong> → Generación de guiones y análisis semántico de comentarios</li>
    </ul>
    <p><strong>Módulos incluidos:</strong></p>
    <table class="modules-table">
        <thead><tr><th>Módulo</th><th>Función</th><th>Tecnología IA</th></tr></thead>
        <tbody>
            <tr><td>🔍 <strong>Buscador de Videos</strong></td><td>Analiza los más virales de cualquier nicho con VIQ Score</td><td>LSTM</td></tr>
            <tr><td>📱 <strong>Shorts Analyzer</strong></td><td>CPM real de Shorts vs Video largo, estrategia de crecimiento</td><td>LSTM</td></tr>
            <tr><td>🕵️ <strong>Spy Tool</strong></td><td>Compara dos canales competidores y detecta huecos de contenido</td><td>Embeddings</td></tr>
            <tr><td>🎯 <strong>Viral Score Predictor</strong></td><td>Predice el potencial viral de un título antes de publicar</td><td>LSTM + Attention</td></tr>
            <tr><td>📅 <strong>CPM Season Calendar</strong></td><td>Calendario mensual de CPM — cuándo ganar hasta 3× más</td><td>LSTM + Time Series</td></tr>
            <tr><td>🔑 <strong>Keywords Analyzer</strong></td><td>Extrae y puntúa palabras clave del nicho con oportunidad real</td><td>TF-IDF + Embeddings</td></tr>
            <tr><td>💰 <strong>Calculadora de Ganancias</strong></td><td>Estimación detallada de ingresos por video y canal</td><td>Regresión Neuronal</td></tr>
            <tr><td>🎬 <strong>Script Generator IA</strong></td><td>Guión completo con gancho, secciones, CTA y tags SEO</td><td>LLaMA 3.3 (Groq)</td></tr>
            <tr><td>💀 <strong>Esqueleto Explainer 3D</strong></td><td>Flujo automático para vídeos científicos con personaje 3D</td><td>Transformers</td></tr>
            <tr><td>🔤 <strong>A/B Tester de Títulos</strong></td><td>Predice CTR de hasta 4 títulos y propone el ganador</td><td>Transformers</td></tr>
            <tr><td>💬 <strong>Análisis de Comentarios</strong></td><td>Sentimiento, preguntas sin responder e ideas de contenido</td><td>LSTM + Sentiment</td></tr>
            <tr><td>🤝 <strong>Calculadora de Sponsors</strong></td><td>Tarifas exactas + email de contacto a marcas generado por IA</td><td>LLaMA 3.3</td></tr>
            <tr><td>🎨 <strong>Prompt Studio</strong></td><td>Prompts profesionales para miniaturas en 7 plataformas</td><td>GPT-4 / Groq</td></tr>
        </tbody>
    </table>

    <hr/>

    <h2>📈 GitHub Stats</h2>
    <div align="center">
        <img height="160" src="https://github-readme-stats.vercel.app/api?username=ToniPost&theme=github_dark&hide_border=true&bg_color=0d0d0d&title_color=00e5ff&text_color=c9d1d9&icon_color=00e5ff&show_icons=true&include_all_commits=true&count_private=true"/>
        &nbsp;&nbsp;
        <img height="160" src="https://github-readme-streak-stats.herokuapp.com/?user=ToniPost&theme=github-dark&hide_border=true&background=0d0d0d&ring=00e5ff&fire=00e5ff&currStreakLabel=00e5ff&sideLabels=c9d1d9&dates=555555"/>
        <br/><br/>
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ToniPost&theme=github_dark&hide_border=true&bg_color=0d0d0d&title_color=00e5ff&text_color=c9d1d9&layout=compact&langs_count=8"/>
    </div>

    <hr/>

    <h2>🏆 Trofeos</h2>
    <div align="center">
        <img src="https://github-profile-trophy.vercel.app/?username=ToniPost&theme=darkhub&no-frame=true&no-bg=true&margin-w=6&column=7" alt="Trophies"/>
    </div>

    <hr/>

    <h2>🌍 Conéctate</h2>
    <div align="center" class="social-links">
        <a href="https://tonipost.dev" class="social-link">🌐 Portfolio</a>
        <a href="https://innovaia.org" class="social-link">🧠 InnovaIA</a>
        <a href="https://linkedin.com/in/tonipost" class="social-link">💼 LinkedIn</a>
        <a href="https://github.com/ToniPost" class="social-link">🐙 GitHub</a>
        <a href="https://twitter.com/tonipost" class="social-link">🐦 Twitter</a>
        <a href="https://youtube.com/@tonipost" class="social-link">📺 YouTube</a>
        <a href="https://play.google.com/store/apps/developer?id=Innovaia+Ecosystem" class="social-link">📱 Google Play</a>
    </div>

    <div align="center">
        <img src="https://visitcount.itsvg.in/api?id=ToniPost&icon=6&color=0" alt="Visitor Count"/>
        <br/><br/>
        <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d0d0d,100:00e5ff&height=100&section=footer&reversal=false" width="100%"/>
    </div>
</div>

<script>
    (function() {
        const canvas = document.getElementById('neuralCanvas');
        if (!canvas) return;
        
        function setupCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        
        setupCanvas();
        window.addEventListener('resize', setupCanvas);
        
        const ctx = canvas.getContext('2d');
        
        // Nodos de la red neuronal
        const nodes = [];
        const numNodes = 60;
        const connections = [];
        
        // Crear nodos en posiciones aleatorias
        for (let i = 0; i < numNodes; i++) {
            nodes.push({
                x: Math.random() * canvas.width,
                y: Math.random() * canvas.height,
                vx: (Math.random() - 0.5) * 0.6,
                vy: (Math.random() - 0.5) * 0.6,
                radius: 2 + Math.random() * 4,
                pulsePhase: Math.random() * Math.PI * 2,
                layer: Math.floor(Math.random() * 4) // 0: input, 1-2: hidden, 3: output
            });
        }
        
        // Crear conexiones (cada nodo se conecta a los 4-6 más cercanos)
        for (let i = 0; i < nodes.length; i++) {
            const distances = [];
            for (let j = 0; j < nodes.length; j++) {
                if (i !== j) {
                    const dx = nodes[i].x - nodes[j].x;
                    const dy = nodes[i].y - nodes[j].y;
                    const dist = Math.sqrt(dx * dx + dy * dy);
                    distances.push({ index: j, dist: dist });
                }
            }
            distances.sort((a, b) => a.dist - b.dist);
            const numConnections = Math.min(5, distances.length);
            for (let k = 0; k < numConnections; k++) {
                const j = distances[k].index;
                if (!connections.some(conn => (conn.from === i && conn.to === j) || (conn.from === j && conn.to === i))) {
                    connections.push({ from: i, to: j, dist: distances[k].dist, active: false, pulseProgress: 0 });
                }
            }
        }
        
        let time = 0;
        let lastTimestamp = 0;
        
        // Función para activar conexiones aleatorias (simulando actividad neuronal)
        function activateRandomConnections() {
            for (let conn of connections) {
                if (Math.random() < 0.02 && !conn.active) {
                    conn.active = true;
                    conn.pulseProgress = 1;
                }
            }
        }
        
        function drawNeuralNetwork() {
            if (!ctx || !canvas) return;
            
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            // Actualizar posiciones de los nodos (movimiento Browniano suave)
            for (let i = 0; i < nodes.length; i++) {
                const node = nodes[i];
                node.x += node.vx;
                node.y += node.vy;
                
                // Rebotar en los bordes con efecto de bounce suave
                if (node.x < 0) { node.x = 0; node.vx *= -0.98; }
                if (node.x > canvas.width) { node.x = canvas.width; node.vx *= -0.98; }
                if (node.y < 0) { node.y = 0; node.vy *= -0.98; }
                if (node.y > canvas.height) { node.y = canvas.height; node.vy *= -0.98; }
            }
            
            // Actualizar distancias de conexiones y pulsos
            for (let conn of connections) {
                const dx = nodes[conn.from].x - nodes[conn.to].x;
                const dy = nodes[conn.from].y - nodes[conn.to].y;
                conn.dist = Math.sqrt(dx * dx + dy * dy);
                
                if (conn.active) {
                    conn.pulseProgress -= 0.03;
                    if (conn.pulseProgress <= 0) {
                        conn.active = false;
                        conn.pulseProgress = 0;
                    }
                }
            }
            
            // Activar conexiones aleatorias cada cierto tiempo
            if (Math.random() < 0.05) {
                activateRandomConnections();
            }
            
            // Dibujar conexiones (sinapsis)
            for (let conn of connections) {
                const fromNode = nodes[conn.from];
                const toNode = nodes[conn.to];
                let opacity = Math.max(0, Math.min(0.25, 1 - conn.dist / 350));
                
                // Si la conexión está activa, aumentar opacidad y cambiar color
                let r = 0, g = 229, b = 255;
                if (conn.active) {
                    opacity = 0.8 + Math.sin(conn.pulseProgress * Math.PI) * 0.3;
                    r = 255;
                    g = 100 + Math.random() * 155;
                    b = 100 + Math.random() * 155;
                }
                
                if (opacity > 0.05) {
                    ctx.beginPath();
                    ctx.moveTo(fromNode.x, fromNode.y);
                    ctx.lineTo(toNode.x, toNode.y);
                    
                    if (conn.active) {
                        ctx.strokeStyle = `rgba(255, ${100 + Math.random() * 155}, ${100 + Math.random() * 155}, ${opacity})`;
                        ctx.lineWidth = 2.5;
                    } else {
                        const gradient = ctx.createLinearGradient(fromNode.x, fromNode.y, toNode.x, toNode.y);
                        gradient.addColorStop(0, `rgba(0, 229, 255, ${opacity * 0.7})`);
                        gradient.addColorStop(1, `rgba(0, 150, 255, ${opacity * 0.4})`);
                        ctx.strokeStyle = gradient;
                        ctx.lineWidth = 0.8;
                    }
                    ctx.stroke();
                }
            }
            
            // Dibujar nodos (neuronas)
            for (let i = 0; i < nodes.length; i++) {
                const node = nodes[i];
                
                // Efecto de pulso
                const pulse = Math.sin(time * 2.5 + node.pulsePhase) * 0.35 + 0.65;
                
                // Sombra glow
                ctx.shadowBlur = 10;
                ctx.shadowColor = `rgba(0, 229, 255, ${0.6 * pulse})`;
                
                // Color según la capa de la neurona
                let colorStart, colorEnd;
                if (node.layer === 0) {
                    colorStart = `rgba(0, 200, 255, ${0.9 * pulse})`;
                    colorEnd = `rgba(0, 100, 200, ${0.3 * pulse})`;
                } else if (node.layer === 3) {
                    colorStart = `rgba(255, 100, 0, ${0.9 * pulse})`;
                    colorEnd = `rgba(200, 50, 0, ${0.3 * pulse})`;
                } else {
                    colorStart = `rgba(0, 229, 255, ${0.9 * pulse})`;
                    colorEnd = `rgba(0, 150, 255, ${0.3 * pulse})`;
                }
                
                const gradient = ctx.createRadialGradient(node.x, node.y, 0, node.x, node.y, node.radius * 2);
                gradient.addColorStop(0, colorStart);
                gradient.addColorStop(1, colorEnd);
                
                ctx.beginPath();
                ctx.arc(node.x, node.y, node.radius * pulse, 0, Math.PI * 2);
                ctx.fillStyle = gradient;
                ctx.fill();
                
                // Núcleo brillante
                ctx.shadowBlur = 6;
                ctx.beginPath();
                ctx.arc(node.x, node.y, node.radius * 0.4, 0, Math.PI * 2);
                ctx.fillStyle = `rgba(255, 255, 255, ${0.9 * pulse})`;
                ctx.fill();
            }
            
            // Reset shadow
            ctx.shadowBlur = 0;
            
            time += 0.025;
            requestAnimationFrame(drawNeuralNetwork);
        }
        
        drawNeuralNetwork();
    })();
</script>

</body>
</html>
