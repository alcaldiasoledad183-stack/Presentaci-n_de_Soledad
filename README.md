<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Soledad | Biografía, Patrimonio y Cultura Viva</title>
    <link href="https://fonts.googleapis.com/css2?family=Sora:wght@300;400;600;700;800&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --navy: #0a1628;
            --navy2: #112240;
            --gold: #f5c842;
            --gold2: #e6a817;
            --green: #1a7a47;
            --green2: #0e5c34;
            --orange: #e67e22;
            --red: #c0392b;
            --white: #f8f4ec;
            --text: #e8e0d0;
            --muted: #b0c4de;
            --card-bg: rgba(10, 22, 40, 0.75);
            --border: rgba(245, 200, 66, 0.2);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        html { scroll-behavior: smooth; }

        body {
            font-family: 'DM Sans', sans-serif;
            background: var(--navy);
            color: var(--text);
            overflow-x: hidden;
        }

        .bg-canvas {
            position: fixed;
            top: 0; left: 0;
            width: 100vw; height: 100vh;
            z-index: -2;
            background: radial-gradient(circle at 20% 30%, rgba(26,122,71,0.15) 0%, rgba(10,22,40,0.95) 80%);
        }
        .grid-overlay {
            position: fixed;
            inset: 0;
            z-index: -1;
            background-image: linear-gradient(rgba(245,200,66,0.03) 1px, transparent 1px),
                              linear-gradient(90deg, rgba(245,200,66,0.03) 1px, transparent 1px);
            background-size: 50px 50px;
        }

        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 12px 40px;
            background: rgba(10,22,40,0.85);
            backdrop-filter: blur(12px);
            border-bottom: 1px solid var(--border);
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 20px;
            flex-wrap: wrap;
        }
        .header-logo img {
            height: 52px;
            object-fit: contain;
        }
        .menu-toggle {
            display: none;
            font-size: 1.8rem;
            color: var(--gold);
            background: none;
            border: none;
            cursor: pointer;
        }
        nav {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }
        nav a {
            text-decoration: none;
            color: #ddd;
            font-size: 0.85rem;
            font-weight: 600;
            padding: 6px 18px;
            border-radius: 40px;
            transition: all 0.2s;
            letter-spacing: 0.03em;
        }
        nav a:hover {
            color: var(--gold);
            background: rgba(245,200,66,0.1);
        }
        @media (max-width: 768px) {
            header {
                padding: 12px 20px;
                flex-wrap: wrap;
            }
            .menu-toggle {
                display: block;
            }
            nav {
                display: none;
                width: 100%;
                flex-direction: column;
                align-items: center;
                gap: 10px;
                margin-top: 15px;
                padding-top: 15px;
                border-top: 1px solid var(--border);
            }
            nav.active {
                display: flex;
            }
            nav a {
                width: 100%;
                text-align: center;
                padding: 10px;
            }
        }

        .section {
            position: relative;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 100px 40px;
            background-size: cover;
            background-position: center;
        }
        .section::before {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, rgba(10,22,40,0.85) 0%, rgba(10,22,40,0.7) 100%);
            z-index: 0;
        }
        .section-container {
            position: relative;
            z-index: 1;
            max-width: 1300px;
            width: 100%;
            margin: 0 auto;
        }
        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }
        .section-tag {
            display: inline-block;
            background: rgba(245,200,66,0.15);
            backdrop-filter: blur(4px);
            padding: 6px 20px;
            border-radius: 40px;
            font-size: 0.75rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.1em;
            color: var(--gold);
            margin-bottom: 20px;
        }
        .section-title {
            font-family: 'Sora', sans-serif;
            font-size: clamp(2rem, 5vw, 3.2rem);
            font-weight: 700;
            color: #fff;
            line-height: 1.2;
        }
        .section-title em {
            color: var(--gold);
            font-style: normal;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .card {
            background: var(--card-bg);
            backdrop-filter: blur(8px);
            border: 1px solid var(--border);
            border-radius: 28px;
            padding: 32px;
            transition: transform 0.3s ease, box-shadow 0.3s;
        }
        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 35px rgba(0,0,0,0.3);
            border-color: rgba(245,200,66,0.4);
        }
        .card-icon {
            font-size: 2rem;
            color: var(--gold);
            margin-bottom: 20px;
        }
        .card h3 {
            font-family: 'Sora', sans-serif;
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 16px;
            color: #fff;
        }
        .card p, .card li {
            color: var(--muted);
            line-height: 1.6;
            font-size: 0.95rem;
        }
        .card ul {
            padding-left: 20px;
            margin-top: 12px;
        }
        .badge-list {
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            margin-top: 20px;
        }
        .badge-list span {
            background: rgba(245,200,66,0.1);
            padding: 6px 14px;
            border-radius: 40px;
            font-size: 0.75rem;
            color: var(--gold);
            border: 1px solid rgba(245,200,66,0.3);
        }
        .inline-image {
            margin-top: 24px;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(0,0,0,0.2);
        }
        .inline-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.4s;
        }
        .inline-image img:hover {
            transform: scale(1.02);
        }
        .timeline {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-top: 30px;
        }
        .milestone {
            background: rgba(0,0,0,0.4);
            backdrop-filter: blur(4px);
            border-left: 3px solid var(--gold);
            padding: 20px;
            border-radius: 20px;
            flex: 1;
        }
        .milestone strong {
            color: var(--gold);
            font-size: 1.1rem;
            display: block;
            margin-bottom: 8px;
        }

        .two-col {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }
        .person-card {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        .person-img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--gold);
            margin-bottom: 16px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }
        .mayor-img {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--gold);
            margin-bottom: 20px;
            box-shadow: 0 8px 25px rgba(0,0,0,0.4);
        }
        .hero-section {
            min-height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.7)), url('soledad-hero.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            text-align: center;
            justify-content: center;
            position: relative;
        }
        .hero-content {
            max-width: 800px;
            padding: 20px;
            animation: fadeUp 1s ease;
        }
        .hero-eyebrow {
            display: inline-block;
            background: rgba(245,200,66,0.2);
            backdrop-filter: blur(4px);
            padding: 6px 20px;
            border-radius: 40px;
            color: var(--gold);
            font-weight: 700;
            letter-spacing: 0.1em;
            font-size: 0.75rem;
            margin-bottom: 25px;
        }
        .hero-content h1 {
            font-family: 'Sora', sans-serif;
            font-size: clamp(2.5rem, 6vw, 4.5rem);
            font-weight: 800;
            color: #fff;
            line-height: 1.1;
            margin-bottom: 20px;
        }
        .hero-content h1 span {
            color: var(--gold);
        }
        .hero-content p {
            font-size: 1.2rem;
            color: #e0e0e0;
            margin-bottom: 35px;
        }
        .hero-pills {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
        }
        .pill {
            padding: 10px 24px;
            border-radius: 40px;
            font-weight: 600;
            background: rgba(0,0,0,0.5);
            backdrop-filter: blur(4px);
            color: #fff;
        }
        .pill-green {
            background: var(--green);
        }
        .pill-gold {
            background: rgba(245,200,66,0.2);
            border: 1px solid var(--gold);
        }

        .stats-bar {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            background: rgba(17,34,64,0.8);
            backdrop-filter: blur(12px);
            border-radius: 60px;
            margin: -40px auto 60px;
            max-width: 1000px;
            padding: 25px 20px;
            gap: 20px;
            position: relative;
            z-index: 2;
        }
        .stat {
            text-align: center;
            flex: 1;
        }
        .stat-num {
            font-family: 'Sora', sans-serif;
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--gold);
        }
        .stat-label {
            font-size: 0.8rem;
            color: var(--muted);
        }

        .table-wrapper {
            overflow-x: auto;
            margin-top: 20px;
            border-radius: 20px;
        }
        .climate-table {
            width: 100%;
            min-width: 600px;
            border-collapse: collapse;
            font-size: 0.85rem;
            background: rgba(0,0,0,0.3);
        }
        .climate-table th, .climate-table td {
            border: 1px solid var(--border);
            padding: 8px 6px;
            text-align: center;
            color: var(--muted);
        }
        .climate-table th {
            background: rgba(245,200,66,0.15);
            color: var(--gold);
            font-weight: 600;
        }

        details {
            background: rgba(0,0,0,0.2);
            border-radius: 20px;
            padding: 12px 20px;
            margin-top: 20px;
        }
        summary {
            font-weight: 700;
            cursor: pointer;
            color: var(--gold);
            padding: 10px 0;
        }
        .barrios-scroll {
            max-height: 300px;
            overflow-y: auto;
            margin-top: 15px;
        }
        .barrios-columns {
            column-count: 3;
            column-gap: 20px;
        }
        .barrios-columns ul {
            margin: 0;
            padding-left: 20px;
            list-style: none;
        }
        .barrios-columns li {
            font-size: 0.8rem;
            margin-bottom: 4px;
            break-inside: avoid;
        }
        .map-link {
            color: var(--gold);
            text-decoration: none;
            border-bottom: 1px dashed;
        }
        .audio-player {
            margin-top: 20px;
            width: 100%;
            background: rgba(0,0,0,0.4);
            border-radius: 40px;
            padding: 10px;
        }
        audio {
            width: 100%;
            border-radius: 40px;
        }
        @media (max-width: 768px) {
            .barrios-columns { column-count: 2; }
            .section { padding: 80px 20px; }
            .stats-bar { margin-top: -30px; border-radius: 30px; }
            .mayor-img { width: 150px; height: 150px; }
        }

        footer {
            background: rgba(5,12,25,0.95);
            border-top: 1px solid var(--border);
            padding: 50px 40px 30px;
            text-align: center;
        }
        footer p {
            color: var(--muted);
            font-size: 0.85rem;
            line-height: 1.6;
        }
        .motto {
            font-family: 'Sora', sans-serif;
            color: var(--gold);
            font-size: 1rem;
            margin: 20px 0;
        }

        .float-btn {
            position: fixed;
            bottom: 25px;
            right: 25px;
            width: 55px;
            height: 55px;
            background: linear-gradient(135deg, var(--orange), var(--red));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.3rem;
            cursor: pointer;
            box-shadow: 0 5px 20px rgba(0,0,0,0.3);
            transition: transform 0.2s;
            z-index: 999;
        }
        .float-btn:hover {
            transform: scale(1.1);
        }

        @keyframes fadeUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }
        .reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
<div class="bg-canvas"></div>
<div class="grid-overlay"></div>

<header>
    <div class="header-logo">
        <img src="logo-alcaldia.png" alt="Alcaldía de Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%20100%20100%22%3E%3Crect%20width%3D%22100%22%20height%3D%22100%22%20fill%3D%22%231a7a47%22%2F%3E%3Ctext%20x%3D%2250%25%22%20y%3D%2250%25%22%20dominant-baseline%3D%22middle%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%20font-size%3D%2214%22%3EAlcaldía%3C%2Ftext%3E%3C%2Fsvg%3E';">
    </div>
    <button class="menu-toggle" id="menuToggle"><i class="fas fa-bars"></i></button>
    <nav id="mainNav">
        <a href="#inicio">Inicio</a>
        <a href="#identidad">Identidad</a>
        <a href="#patrimonio">Patrimonio</a>
        <a href="#gobierno">Gobierno</a>
        <a href="#cultura">Cultura</a>
        <a href="#carnaval">Carnaval</a>
        <a href="#decima">La Décima</a>
        <a href="#entretenimiento">Parque Muvdi</a>
        <a href="#personajes">Personajes</a>
        <a href="#actualidad">Actualidad</a>
        <a href="#naturaleza">Geografía</a>
        <a href="#bolivar">Bolívar</a>
    </nav>
</header>

<script>
    const toggleBtn = document.getElementById('menuToggle');
    const mainNav = document.getElementById('mainNav');
    if (toggleBtn) {
        toggleBtn.addEventListener('click', () => {
            mainNav.classList.toggle('active');
        });
        document.querySelectorAll('#mainNav a').forEach(link => {
            link.addEventListener('click', () => {
                mainNav.classList.remove('active');
            });
        });
    }
</script>

<!-- Hero -->
<section id="inicio" class="hero-section">
    <div class="hero-content">
        <div class="hero-eyebrow"><i class="fas fa-landmark"></i> NUESTRO MUNICIPIO</div>
        <h1>Soledad, <span>Atlántico</span><br>Emporio Cultural del Caribe Colombiano</h1>
        <p>Uno de los municipios más antiguos y poblados de la región Caribe. Cuna del merecumbé, capital mundial de la butifarra, con una herencia histórica colonial y un presente vibrante de cultura, industria y desarrollo urbano.</p>
        <div class="hero-pills">
            <span class="pill pill-green"><i class="fas fa-drumstick-bite"></i> Butifarra</span>
            <span class="pill pill-gold"><i class="fas fa-music"></i> Merecumbé</span>
            <span class="pill pill-green"><i class="fas fa-church"></i> Patrimonio</span>
        </div>
    </div>
</section>

<!-- Stats Bar -->
<div class="stats-bar reveal">
    <div class="stat"><div class="stat-num">686k+</div><div class="stat-label">Habitantes (2025)</div></div>
    <div class="stat"><div class="stat-num">1598</div><div class="stat-label">Fundación</div></div>
    <div class="stat"><div class="stat-num">67 km²</div><div class="stat-label">Extensión</div></div>
    <div class="stat"><div class="stat-num">10°54′N</div><div class="stat-label">Coordenadas</div></div>
</div>

<!-- Identidad -->
<section id="identidad" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">SÍMBOLOS Y TERRITORIO</div>
            <h2 class="section-title">Identidad de <em>Soledad</em></h2>
        </div>
        <div class="two-col reveal">
            <div class="card">
                <div class="card-icon"><i class="fas fa-map-marker-alt"></i></div>
                <h3>Ubicación</h3>
                <p>Soledad se ubica en la costa Norte de Colombia, departamento del Atlántico, parte del área metropolitana de Barranquilla. Limita al norte con Barranquilla, al sur con Malambo, al oriente con el río Magdalena y al occidente con Galapa. Altitud: 26 msnm. Clima tropical seco.</p>
                <div class="badge-list"><span>10°54′N</span><span>74°46′O</span><span>Gentilicio: Soledeño/a</span></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-flag"></i></div>
                <h3>Bandera</h3>
                <p>Dos franjas horizontales: superior azul, inferior verde. Representa la riqueza de sus tierras y la conexión con el cielo y la naturaleza.</p>
                <div class="inline-image">
                    <img src="bandera-soledad.png" alt="Bandera de Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22150%22%20viewBox%3D%220%200%20300%20150%22%3E%3Crect%20width%3D%22300%22%20height%3D%2275%22%20fill%3D%22%233366cc%22%2F%3E%3Crect%20y%3D%2275%22%20width%3D%22300%22%20height%3D%2275%22%20fill%3D%22%23339933%22%2F%3E%3C%2Fsvg%3E';">
                </div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-shield-alt"></i></div>
                <h3>Escudo</h3>
                <p>Resume la lucha independentista. Un pilar central simboliza fuerza, decisión y empuje del pueblo soledeño.</p>
                <div class="inline-image">
                    <img src="escudo-soledad.png" alt="Escudo de Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22150%22%20height%3D%22150%22%20viewBox%3D%220%200%20150%20150%22%3E%3Crect%20width%3D%22150%22%20height%3D%22150%22%20fill%3D%22%23d4af37%22%2F%3E%3Ctext%20x%3D%2275%22%20y%3D%2280%22%20text-anchor%3D%22middle%22%20fill%3D%22%23000%22%20font-size%3D%2220%22%3EEscudo%3C%2Ftext%3E%3C%2Fsvg%3E';">
                </div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-music"></i></div>
                <h3>Himno de Soledad</h3>
                <p>Letra de José Miguel Orozco y música de Francisco "Pacho" Galán. Celebra la fundación, el paso de Bolívar y el orgullo de Soledad.</p>
                <div class="badge-list"><span>“Venciendo rudezas de indígena selva...”</span></div>
                <div class="inline-image">
                    <img src="himno-soledad.png" alt="Partitura del Himno de Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22150%22%3E%3Crect%20width%3D%22300%22%20height%3D%22150%22%20fill%3D%22%23444%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%2275%22%20fill%3D%22%23f5c842%22%20text-anchor%3D%22middle%22%3EHimno%3C%2Ftext%3E%3C%2Fsvg%3E';">
                </div>
                <div class="audio-player">
                    <p style="font-size:0.7rem; margin-top:8px;">Himno Oficial de Soledad</p>
                </div>
            </div>
        </div>
        <div class="card reveal" style="margin-top: 30px;">
            <h3>Reseña histórica</h3>
            <p>En 1598, bajo el capitán Antonio Moreno Estupiñán, se estableció un criadero de cerdos con ocho indígenas, origen de “La Porquera de San Antonio”. En 1640, Melchor Caro tramitó la fundación legal. En 1743 se creó la parroquia y el 20 de enero de 1744 se inauguró oficialmente como parroquia San Antonio de Padua. El 8 de marzo de 1814 se le otorgó el título de villa con el nombre de <strong>Soledad de Colombia</strong>.</p>
            <div class="timeline">
                <div class="milestone"><strong>1598</strong> Fundación del criadero “La Porquera”</div>
                <div class="milestone"><strong>1640</strong> Gestión de Melchor Caro</div>
                <div class="milestone"><strong>1744</strong> Creación parroquia San Antonio de Padua</div>
                <div class="milestone"><strong>1814</strong> Título de Villa “Soledad de Colombia”</div>
            </div>
        </div>
    </div>
</section>

<!-- Patrimonio -->
<section id="patrimonio" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">LEGADO ARQUITECTÓNICO</div>
            <h2 class="section-title">Patrimonio <em>histórico y cultural</em></h2>
        </div>
        <div class="cards-grid reveal">
            <div class="card">
                <div class="card-icon"><i class="fas fa-church"></i></div>
                <h3>Iglesia San Antonio de Padua</h3>
                <p>Construida desde 1598, finalizada a finales del siglo XIX. Es el templo más antiguo en pie en el Atlántico. Su altar es barroco churrigueresco, patrimonio del Ministerio de Cultura.</p>
                <div class="inline-image"><img src="iglesia-san-antonio.jpg" alt="Iglesia San Antonio" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23664422%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3EIglesia%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-home"></i></div>
                <h3>Casa Museo Simón Bolívar</h3>
                <p>Edificación colonial donde el Libertador pernoctó en 1830 antes de su viaje a Santa Marta. Punto clave del patrimonio bolivariano.</p>
                <div class="inline-image"><img src="casa-museo-bolivar.jpg" alt="Casa Museo Bolívar" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%238b5a2b%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3ECasa Museo%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-theater-masks"></i></div>
                <h3>Teatro Olimpia</h3>
                <p>Construido hacia 1925, estilo republicano. Centro cultural y de entretenimiento de Soledad antes de la televisión. Patrimonio cultural.</p>
                <div class="inline-image"><img src="teatro-olimpia.jpg" alt="Teatro Olimpia" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23996633%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3ETeatro%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-tree"></i></div>
                <h3>Plaza Mayor de Soledad</h3>
                <p>Remodelada en 2022, corazón religioso y cultural. Rodea la iglesia y la Casa Museo. Punto de encuentro gastronómico y turístico.</p>
                <div class="inline-image"><img src="plaza-mayor-soledad.jpg" alt="Plaza Mayor" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23228b22%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3EPlaza Mayor%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
        </div>
    </div>
</section>

<!-- Gobierno (Alcaldesa, datos, clima, barrios) -->
<section id="gobierno" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">GOBIERNO Y TERRITORIO</div>
            <h2 class="section-title">Alcaldesa y <em>Datos completos</em></h2>
        </div>
        <div class="two-col reveal">
            <div class="card person-card" style="align-items: center;">
                <img src="alcira-sandoval.jpg" alt="Alcira Sandoval Ibáñez" class="mayor-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22200%22%20height%3D%22200%22%3E%3Ccircle%20cx%3D%22100%22%20cy%3D%22100%22%20r%3D%2298%22%20fill%3D%22%23b87333%22%2F%3E%3Ctext%20x%3D%22100%22%20y%3D%22115%22%20text-anchor%3D%22middle%22%20fill%3D%22%23fff%22%3EAlcaldesa%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-user-tie"></i></div>
                <h3>Alcira Sandoval Ibáñez</h3>
                <p><strong>Alcaldesa Municipal (2024-2027)</strong><br>Líder social y política con amplia trayectoria en gestión pública. Su administración impulsa la reactivación económica, el mejoramiento del espacio público y el fortalecimiento de la cultura ciudadana. Proyectos enfocados en movilidad sostenible, turismo patrimonial y apoyo a emprendedores locales. Alcira es Médico Cirujano de profesión, egresada de la Universidad libre, Especialista en Economia Social y Solidaria, en formación de la Universidad Minuto de Dios. En el periodo 2019-2023, fue elegida Concejal del municipio de Soledad. Cuarta alcaldesa de Soledad electa por voto Popular. Ordenó la pavimentación de los 500M del tramo de la Calle 30 denominada como (Sector de Tauro). </p>
                <div class="badge-list"><span>Gobierno de la gente</span><span>Plan de Desarrollo “Soledad Avanza”</span></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-chart-pie"></i></div>
                <h3>Densidad y Estadísticas</h3>
                <p><strong>Población total (2025):</strong> 686.339 hab.<br>
                <strong>Urbana:</strong> 685.458 hab. (99.8%)<br>
                <strong>Rural:</strong> 881 hab.<br>
                <strong>Densidad:</strong> 10.089,76 hab/km²<br>
                <strong>Extensión rural:</strong> Solo el 2% del territorio.<br>
                <strong>Altitud media:</strong> 26 m s. n. m.<br>
                <strong>Clima:</strong> Tropical seco (Aw)<br>
                <strong>Coordenadas exactas:</strong> 10°54′35″N 74°47′09″O</p>
            </div>
        </div>
        <div class="card reveal" style="margin-top: 20px;">
            <h3><i class="fas fa-cloud-sun"></i> Parámetros climáticos promedio</h3>
            <div class="table-wrapper">
                <table class="climate-table">
                    <thead><tr><th>Mes</th><th>Ene</th><th>Feb</th><th>Mar</th><th>Abr</th><th>May</th><th>Jun</th><th>Jul</th><th>Ago</th><th>Sep</th><th>Oct</th><th>Nov</th><th>Dic</th><th>Anual</th></tr></thead>
                    <tbody>
                        <tr><td>Temp. máx. abs. (°C)</td><td>38.2</td><td>37.6</td><td>37.8</td><td>39.5</td><td>39.3</td><td>39.8</td><td>39.2</td><td>39.0</td><td>38.4</td><td>38.6</td><td>38.4</td><td>39.5</td><td>39.8</td></tr>
                        <tr><td>Temp. máx. media (°C)</td><td>31.4</td><td>31.7</td><td>32.4</td><td>33.1</td><td>33.4</td><td>33.2</td><td>32.9</td><td>33.3</td><td>33.0</td><td>32.5</td><td>32.2</td><td>31.7</td><td>32.6</td></tr>
                        <tr><td>Temp. media (°C)</td><td>26.7</td><td>26.8</td><td>27.2</td><td>27.8</td><td>28.2</td><td>28.2</td><td>28.0</td><td>28.1</td><td>27.8</td><td>27.4</td><td>27.5</td><td>27.1</td><td>27.6</td></tr>
                        <tr><td>Temp. mín. media (°C)</td><td>23.6</td><td>23.9</td><td>24.2</td><td>24.9</td><td>24.9</td><td>24.8</td><td>24.6</td><td>24.6</td><td>24.1</td><td>23.9</td><td>24.1</td><td>24.0</td><td>24.3</td></tr>
                        <tr><td>Temp. mín. abs. (°C)</td><td>18.0</td><td>18.0</td><td>18.8</td><td>18.8</td><td>18.0</td><td>20.5</td><td>19.4</td><td>20.9</td><td>20.0</td><td>14.9</td><td>18.5</td><td>19.5</td><td>14.9</td></tr>
                        <tr><td>Lluvias (mm)</td><td>1.2</td><td>0.5</td><td>1.9</td><td>31.8</td><td>118.0</td><td>83.0</td><td>92.1</td><td>112.6</td><td>160.5</td><td>169.6</td><td>95.6</td><td>37.5</td><td>904.3</td></tr>
                        <tr><td>Días de lluvia (≥)</td><td>0</td><td>0</td><td>1</td><td>4</td><td>9</td><td>10</td><td>8</td><td>11</td><td>14</td><td>16</td><td>9</td><td>3</td><td>85</td></tr>
                        <tr><td>Horas de sol</td><td>285.2</td><td>246.4</td><td>244.9</td><td>210.0</td><td>189.1</td><td>201.0</td><td>217.0</td><td>207.7</td><td>171.0</td><td>167.4</td><td>186.0</td><td>244.9</td><td>2570.6</td></tr>
                        <tr><td>Humedad relativa (%)</td><td>79</td><td>78</td><td>77</td><td>79</td><td>81</td><td>82</td><td>81</td><td>82</td><td>84</td><td>86</td><td>84</td><td>81</td><td>81.2</td></tr>
                    </tbody>
                </table>
            </div>
        </div>
        <div class="card reveal">
            <h3><i class="fas fa-building"></i> División territorial: Barrios de Soledad</h3>
            <p>El municipio está conformado por aproximadamente <strong>190 barrios</strong> que representan el 98% del área urbana. A continuación se listan la mayoría de ellos:</p>
            <details>
                <summary><i class="fas fa-list-ul"></i> Ver todos los barrios (más de 180)</summary>
                <div class="barrios-scroll">
                    <div class="barrios-columns">
                        <ul>
                            <li>Altos De Jesús</li><li>Altos de La Metropolitana</li><li>Altos de La Villa</li><li>Altos de Los Almendros</li><li>Altos de Los Robles</li><li>Altos de Sevilla</li><li>Antonio Nariño</li><li>Barrio Centro</li><li>Bella Jerusalén</li><li>Bella Murillo</li><li>Bello Horizonte</li><li>Cachimbero</li><li>Ciudad Bolívar</li><li>Ciudad Bonita</li><li>Ciudad Camelot</li><li>Ciudad Caribe</li><li>Ciudad Caribe IV</li><li>Ciudad Fallace</li><li>Ciudad Paraíso</li><li>Ciudad Salitre</li><li>Ciudad Transmetro</li><li>Ciudadela Metropolitana</li><li>Costa De Oro</li><li>Costa Hermosa</li><li>Cruz de Mayo</li><li>Cuchilla de Los Ángeles</li><li>Dieciséis de Junio</li><li>Doce de Octubre</li><li>Don Bosco</li><li>El Cabrera</li><li>El Carnero</li><li>El Centenario</li><li>El Cortijo</li><li>El Encanto</li><li>El Esfuerzo</li><li>El Ferrocarril</li><li>El Hipódromo</li><li>El Manantial</li><li>El Oasis</li><li>El Pasito</li><li>El Porvenir</li><li>El Recuerdo</li><li>El Triunfo</li><li>El Tucán</li><li>Jardín de Villa Estadio</li><li>Juan Domínguez Romero</li><li>La Arboleda</li><li>La Bonanza</li><li>La Candelaria</li><li>La Candelaria I</li><li>La Candelaria II</li><li>La Central</li><li>La Esperanza</li><li>La Farruca</li><li>La Fe</li><li>La Floresta I</li><li>La Floresta II</li><li>La Ilusión</li><li>La Inmaculada</li><li>La Loma</li><li>La María</li><li>La Puerta De Oro</li><li>La Rivera</li><li>La Victoria</li><li>Las Colonias</li><li>Las Colonias II</li><li>Las Cometas</li><li>Las Ferias</li><li>Las Gaviotas</li><li>Las Gaviotas II</li><li>Las Moras IV</li><li>Las Moras Norte</li><li>Las Moras Occidente</li><li>Las Nubes</li><li>Las Trinitarias</li><li>Linda María</li><li>Linda María II</li><li>Los Almendros</li><li>Los Almendros II</li><li>Los Almendros III</li><li>Los Arrayanes</li><li>Los Balcanes</li><li>Los Cedros</li><li>Los Cerezos</li><li>Los Cusules</li><li>Los Fundadores</li><li>Los Loteros</li><li>Los Mangos</li><li>Los Robles</li><li>Los Robles IV</li><li>Los Robles VIII</li><li>Los Robles IX</li><li>Los Robles X</li><li>Los Rosales</li><li>Manuela Beltrán</li><li>Martha Gisella</li><li>Montecarmelo</li><li>Normandía</li><li>Normandía Norte</li><li>Nueva Esperanza</li><li>Nueva Jerusalén</li><li>Nuevo Éxito</li><li>Nuevo Horizonte</li><li>Nuevo Horizonte II</li><li>Nuevo Milenio</li><li>Nuevo Triunfo</li><li>Portal de Las Moras</li><li>Portal de Los Nogales</li><li>Prado De Soledad</li><li>Primero de Mayo</li><li>Pumarejo</li><li>Renacer</li><li>Reserva de Los Almendros</li><li>Rigoberta Menchu</li><li>Ríos de Agua Viva</li><li>Salamanca</li><li>Salcedo</li><li>San Antonio</li><li>San Bernardo</li><li>San Juan Eudes</li><li>San Vicente</li><li>Si Nos Dejan</li><li>Siete de Agosto</li><li>Sitio Hermoso</li><li>Soledad Dos Mil</li><li>Tajamar</li><li>Tajamar II</li><li>Urbanización Ciudad Del Parque</li><li>Urbanización El Parque</li><li>Urbanización El Rio</li><li>Urbanización Las Moras</li><li>Urbanización María de los Ángeles</li><li>Urbanización Parque Muvdi</li><li>Urbanización Portal de Jordán</li><li>Urbanización Portal de San Antonio</li><li>Urbanización Salamanca</li><li>Urbanización Santana</li><li>Urbanización Sol Real</li><li>Urbanización Terranova</li><li>Urbanización Terranova II</li><li>Urbanización Villa Mónaco</li><li>Urbanización Villa Soledad</li><li>Urbanización Villa Viola</li><li>Veinte de Julio</li><li>Veintitrés de Noviembre</li><li>Villa Adela I</li><li>Villa Adela II</li><li>Villa Angelita</li><li>Villa Anita</li><li>Villa Campanos II</li><li>Villa Carmen I</li><li>Villa Carmen II</li><li>Villa Cecilia</li><li>Villa de Aragón</li><li>Villa Del Carmen</li><li>Villa Del Rey</li><li>Villa Estadio</li><li>Villa Estadio II</li><li>Villa Estadio Sector Norte</li><li>Villa Estefany</li><li>Villa Esther</li><li>Villa Gladis</li><li>Villa Karla I</li><li>Villa Katanga</li><li>Villa Katanga II</li><li>Villa Las Moras I</li><li>Villa Las Moras II</li><li>Villa Lozano</li><li>Villa María</li><li>Villa María Silena</li><li>Villa Merly</li><li>Villa Mónica</li><li>Villa Murillo</li><li>Villa Rosa</li><li>Villa Salamar</li>
                        </ul>
                    </div>
                </div>
                <small style="color:var(--muted)">*Lista representativa de la gran mayoría de barrios del municipio.</small>
            </details>
        </div>
    </div>
</section>

<!-- Cultura (butifarra, fiestas, personajes originales) -->
<section id="cultura" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">TRADICIÓN VIVA</div>
            <h2 class="section-title">Patrimonio <em>gastronómico y fiestas</em></h2>
        </div>
        <div class="two-col reveal">
            <div class="card">
                <div class="card-icon"><i class="fas fa-drumstick-bite"></i></div>
                <h3>Butifarra Soledeña</h3>
                <p>Declarada patrimonio cultural e inmaterial en 2013. Embutido de origen catalán, elaborado con carne de res y cerdo, acompañado de bollo de yuca. El festival se celebra el 15 y 16 de noviembre.</p>
                <div class="inline-image"><img src="butifarra-plato.jpg" alt="Butifarra soledeña" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23cd7f32%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3EButifarra%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
                <div class="badge-list"><span>Capital mundial de la butifarra</span><span>Festival en noviembre</span></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-calendar-alt"></i></div>
                <h3>Fiestas Principales</h3>
                <ul>
                    <li><strong>Fiestas Patronales San Antonio de Padua</strong> (10-15 junio, día central 13 junio): alboradas, procesiones, misas solemnes y eventos folclóricos.</li>
                    <li><strong>Festival de la Butifarra</strong> (noviembre): cultura, emprendimiento y arte.</li>
                </ul>
                <div class="inline-image"><img src="fiestas-patronales.jpg" alt="Fiestas San Antonio" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23996633%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3EFiestas%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
        </div>
        <div class="reveal" style="margin-top: 50px;">
            <div class="section-header">
                <div class="section-tag">CUNA DE ARTISTAS</div>
                <h2 class="section-title">Personajes <em>representativos</em></h2>
            </div>
            <div class="cards-grid">
                <div class="card person-card">
                    <img src="pacho-galan.jpg" alt="Pacho Galán" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%20viewBox%3D%220%200%20120%20120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23b8860b%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20text-anchor%3D%22middle%22%20fill%3D%22%23fff%22%3EPG%3C%2Ftext%3E%3C%2Fsvg%3E';">
                    <div class="card-icon"><i class="fas fa-guitar"></i></div>
                    <h3>Pacho Galán</h3>
                    <p>Cantante, compositor, director de orquesta. Creador del merecumbé, autor de "El Sanjuanero", ícono del folclor costeño.</p>
                </div>
                <div class="card person-card">
                    <img src="alci-acosta.jpg" alt="Alci Acosta" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%20viewBox%3D%220%200%20120%20120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23cd7f32%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20text-anchor%3D%22middle%22%20fill%3D%22%23fff%22%3EAA%3C%2Ftext%3E%3C%2Fsvg%3E';">
                    <div class="card-icon"><i class="fas fa-piano"></i></div>
                    <h3>Alcibíades Acosta</h3>
                    <p>Pianista, compositor y bolerista, una de las voces más emblemáticas de la música romántica colombiana.</p>
                </div>
                <div class="card person-card">
                    <img src="rafael-campo-miranda.jpg" alt="Rafael Campo Miranda" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%20viewBox%3D%220%200%20120%20120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23555%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20text-anchor%3D%22middle%22%20fill%3D%22%23fff%22%3ERCM%3C%2Ftext%3E%3C%2Fsvg%3E';">
                    <div class="card-icon"><i class="fas fa-music"></i></div>
                    <h3>Rafael Campo Miranda</h3>
                    <p>Compositor de música costeña, autor de "La Cumbia Cienaguera" y decenas de himnos del folclor colombiano.</p>
                </div>
                <div class="card person-card">
                    <img src="checo-acosta.jpg" alt="Checo Acosta" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%20viewBox%3D%220%200%20120%20120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%233a6ea5%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20text-anchor%3D%22middle%22%20fill%3D%22%23fff%22%3ECA%3C%2Ftext%3E%3C%2Fsvg%3E';">
                    <div class="card-icon"><i class="fas fa-drum"></i></div>
                    <h3>Checo Acosta</h3>
                    <p>Cantante de música tropical y folclórica, embajador de la cultura costeña con más de 30 años de trayectoria.</p>
                </div>
                <div class="card person-card">
                    <img src="erain-mejia-donado.jpg" alt="Efrain Mejía Donado" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%20viewBox%3D%220%200%20120%20120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%234b6e42%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20text-anchor%3D%22middle%22%20fill%3D%22%23fff%22%3EEMD%3C%2Ftext%3E%3C%2Fsvg%3E';">
                    <div class="card-icon"><i class="fas fa-hand-sparkles"></i></div>
                    <h3>Efrain Mejía Donado</h3>
                    <p>Reconocido músico, compositor e investigador folclórico, experto en tradiciones del Caribe colombiano. Gestor cultural que ha llevado el folclor soledeño a escenarios nacionales, preservando el merecumbé y las músicas ancestrales.</p>
                </div>
            </div>
        </div>
    </div>
</section>

<!-- Carnaval -->
<section id="carnaval" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">FIESTA Y ALEGRÍA</div>
            <h2 class="section-title">Carnaval de <em>Soledad</em></h2>
        </div>
        <div class="two-col reveal">
            <div class="card">
                <div class="card-icon"><i class="fas fa-mask"></i></div>
                <h3>El carnaval más auténtico</h3>
                <p>Se celebra anualmente desde el sábado hasta el martes antes del Miércoles de Ceniza (febrero-marzo). Comienza el segundo sábado de enero con verbenas populares. Es la fiesta folclórica y cultural más importante del municipio.</p>
                <div class="inline-image"><img src="carnaval-soledad.jpg" alt="Carnaval Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23e67e22%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23fff%22%3ECarnaval%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-crown"></i></div>
                <h3>Reina del Carnaval y Lectura del Bando</h3>
                <p>La Reina del carnaval es designada anualmente y mediante la Lectura del Bando (mediados de enero) promulga la única "ley": bailar y gozar. Barrios eligen sus reinas y participan en el Reinado Reina de Reinas.</p>
                <div class="inline-image"><img src="reina-carnaval.jpg" alt="Reina del Carnaval" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23c0392b%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23f5c842%22%3EReina%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
        </div>
    </div>
</section>

<!-- La Décima Soledeña -->
<section id="decima" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">PATRIMONIO ORAL</div>
            <h2 class="section-title">La Décima <em>Soledeña</em></h2>
        </div>
        <div class="card reveal">
            <div class="card-icon"><i class="fas fa-microphone-alt"></i></div>
            <h3>Patrimonio Cultural e Inmaterial del Atlántico</h3>
            <p>La décima soledeña es una expresión poética oral y musical, declarada Patrimonio Cultural e Inmaterial del Atlántico. Consiste en estrofas de diez versos octosílabos con rima consonante, utilizadas para narrar historias, costumbres y la identidad del municipio de Soledad. Transmitida de generación en generación, es un símbolo de la memoria viva del Caribe colombiano.</p>
            <div class="inline-image">
            </div>
            <div class="badge-list"><span>Versos octosílabos</span><span>Rima consonante</span><span>Tradición oral</span><span>Patrimonio del Atlántico</span></div>
        </div>
    </div>
</section>

<!-- Parque Muvdi -->
<section id="entretenimiento" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">DIVERSIÓN Y FAMILIA</div>
            <h2 class="section-title">Parque <em>Muvdi</em></h2>
        </div>
        <div class="card reveal">
            <div class="card-icon"><i class="fas fa-tree"></i> <i class="fas fa-swimmer"></i></div>
            <h3>Parque Muvdi: un espacio multifacético</h3>
            <p>Es un espacio que combina áreas deportivas, acuáticas y de ocio. Los visitantes destacan su ambiente renovado y la variedad de actividades que permiten pasar un día entero sin salir del recinto. Ideal para disfrutar en familia, con zonas de piscinas, canchas, juegos infantiles y áreas verdes.</p>
            <div class="inline-image">
                <img src="parque-muvdi.jpg" alt="Parque Muvdi Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23378a3a%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23f5c842%22%3EParque%20Muvdi%3C%2Ftext%3E%3C%2Fsvg%3E';">
            </div>
            <div class="badge-list"><span>Zona de piscinas</span><span>Canchas deportivas</span><span>Área de picnic</span><span>Entretenimiento familiar</span></div>
        </div>
    </div>
</section>

<!-- Otros personajes ilustres -->
<section id="personajes" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">MEMORIA Y ORGULLO</div>
            <h2 class="section-title">Otros <em>hijos ilustres</em></h2>
        </div>
        <div class="cards-grid reveal">
            <div class="card person-card">
                <img src="gabriel-escorcia-gravini.jpg" alt="Gabriel Escorcia" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23554%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EGEG%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-feather-alt"></i></div>
                <h3>Gabriel Antonio Escorcia Gravini</h3>
                <p>Poeta colombiano, autor de la décima "La gran miseria humana". Considerado uno de los mejores poetas de la historia de Soledad. Su obra fue convertida en paseo vallenato por Lisandro Meza.</p>
            </div>
            <div class="card person-card">
                <img src="juan-jimenez-gayaspa.jpg" alt="Juan Jiménez" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%236a4e2e%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EJJG%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-trumpet"></i></div>
                <h3>Juan Jiménez Gayaspá</h3>
                <p>Gran músico y precursor de la música de viento en Soledad. Su legado vive en matrimonios y fiestas patronales, clave en el folclor del Atlántico.</p>
            </div>
            <div class="card person-card">
                <img src="gabriel-segura-miranda.jpg" alt="Gabriel Segura" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23996633%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EGSM%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-microphone-alt"></i></div>
                <h3>Gabriel Segura Miranda</h3>
                <p>"El Rey de la Décima". Músico, compositor y decimero de tiempo completo. Sus décimas más conocidas: "Santo y parrandero" y "Con sus fiestas novembrinas".</p>
            </div>
            <div class="card person-card">
                <img src="rafael-urbano-lafaurie.jpg" alt="Rafael Urbano" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23356b8f%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3ERUL%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-history"></i></div>
                <h3>Rafael Urbano Lafaurie</h3>
                <p>Fundador de la Academia de Historia de Soledad, primer corresponsal del municipio. Incidencia social y cultural invaluable.</p>
            </div>
            <div class="card person-card">
                <img src="lizeth-mahecha.jpg" alt="Lizeth Mahecha" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23a44%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3ELM%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-futbol"></i></div>
                <h3>Lizeth Mahecha Arévalo</h3>
                <p> Abogada y reina de belleza colombiana que fue ganadora del título Señorita Colombia en 1989.</p>
            </div>
            <div class="card person-card">
                <img src="henry-zambrano.jpg" alt="Henry Zambrano" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23555%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EHZ%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-futbol"></i></div>
                <h3>Henry Zambrano Sandoval</h3>
                <p>Exfutbolista profesional, referente deportivo.</p>
            </div>
            <div class="card person-card">
                <img src="ricardo-ciciliano.jpg" alt="Ricardo Ciciliano" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23447733%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3ERC%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-futbol"></i></div>
                <h3>Ricardo Ciciliano</h3>
                <p>Futbolista profesional, talento soledeño.</p>
            </div>
            <div class="card person-card">
                <img src="melissa-martinez.jpg" alt="Melissa Martínez" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23c44%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EMM%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-tv"></i></div>
                <h3>Melissa Martínez</h3>
                <p>Periodista y presentadora, orgullo soledeño.</p>
            </div>
            <div class="card person-card">
                <img src="jose-enamorado.jpg" alt="José Enamorado" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%23556b2f%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EJE%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-futbol"></i></div>
                <h3>José Enamorado</h3>
                <p>Joven promesa del fútbol.</p>
            </div>
            <div class="card person-card">
                <img src="jordan-barrera.jpg" alt="Jordan Barrera" class="person-img" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22120%22%20height%3D%22120%22%3E%3Ccircle%20cx%3D%2260%22%20cy%3D%2260%22%20r%3D%2258%22%20fill%3D%22%2370502e%22%2F%3E%3Ctext%20x%3D%2260%22%20y%3D%2275%22%20fill%3D%22%23fff%22%3EJB%3C%2Ftext%3E%3C%2Fsvg%3E';">
                <div class="card-icon"><i class="fas fa-futbol"></i></div>
                <h3>Jordan Barrera</h3>
                <p>Futbolista profesional en ascenso.</p>
            </div>
        </div>
    </div>
</section>

<!-- Actualidad -->
<section id="actualidad" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">DESARROLLO Y CONECTIVIDAD</div>
            <h2 class="section-title">Transporte, <em>economía e importancia</em></h2>
        </div>
        <div class="two-col reveal">
            <div class="card">
                <div class="card-icon"><i class="fas fa-plane"></i> <i class="fas fa-bus"></i></div>
                <h3>Infraestructura clave</h3>
                <ul>
                    <li>Aeropuerto Internacional Ernesto Cortissoz</li>
                    <li>Terminal de Transportes de Barranquilla (ubicada en Soledad)</li>
                    <li>Sistema masivo Transmetro y corredores viales</li>
                </ul>
                <div class="inline-image"><img src="terminal-transporte.jpg" alt="Terminal de Transportes Barranquilla" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22150%22%20viewBox%3D%220%200%20300%20150%22%3E%3Crect%20width%3D%22300%22%20height%3D%22150%22%20fill%3D%22%23445566%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%2280%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3ETerminal%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
                <div class="inline-image" style="margin-top: 10px;"><img src="aeropuerto-cortissoz.jpg" alt="Aeropuerto Cortissoz" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22150%22%20viewBox%3D%220%200%20300%20150%22%3E%3Crect%20width%3D%22300%22%20height%3D%22150%22%20fill%3D%22%23334455%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%2280%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3EAeropuerto%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
                <p>Estos ejes generan impacto directo en la economía y conectividad metropolitana.</p>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-chart-line"></i></div>
                <h3>Centros comerciales y comercio</h3>
                <p>Soledad alberga importantes centros comerciales como Nuestro Atlántico, Carnaval y Gran Plaza del Sol, puntos de entretenimiento y economía local.</p>
                <div class="inline-image"><img src="centro-comercial-nuestro-atlantico.jpg" alt="CC Nuestro Atlántico" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23556b2f%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3ECC%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
                <div class="inline-image" style="margin-top: 10px;"><img src="centro-comercial-carnaval.jpg" alt="CC Carnaval" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23855e3a%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3ECC%20Carnaval%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
                <div class="inline-image" style="margin-top: 10px;"><img src="gran-plaza-del-sol.jpg" alt="Gran Plaza del Sol" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%20viewBox%3D%220%200%20300%20200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23c9ae5d%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20text-anchor%3D%22middle%22%20fill%3D%22%23f5c842%22%3EGran Plaza%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
        </div>
        <div class="card reveal" style="margin-top: 30px;">
            <h3>Importancia actual</h3>
            <p>Soledad es uno de los municipios más poblados del Atlántico. Su historia refleja mezcla de culturas, identidad y memoria colectiva. Conocer su pasado fortalece el sentido de pertenencia y educa a las nuevas generaciones para mantener vivas las tradiciones, el orgullo por su legado y el impulso hacia un futuro próspero.</p>
            <div class="badge-list"><span>Capital de la butifarra</span><span>Cuna del merecumbé</span><span>Patrimonio bolivariano</span><span>Centro metropolitano</span></div>
        </div>
    </div>
</section>

<!-- Geografía e Hidrología -->
<section id="naturaleza" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">NATURALEZA Y TERRITORIO</div>
            <h2 class="section-title">Hidrología y <em>zona rural</em></h2>
        </div>
        <div class="two-col reveal">
            <div class="card">
                <div class="card-icon"><i class="fas fa-water"></i></div>
                <h3>Río Magdalena y arroyos</h3>
                <p>El río Magdalena bordea Soledad por el oriente. Arroyos significativos: Don Juan, El Salao, El Platanal, caño Soledad y Ciénaga de la Bahía.</p>
                <div class="inline-image"><img src="rio-magdalena-soledad.jpg" alt="Río Magdalena" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23206a5d%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23f5c842%22%3ER%C3%ADo%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
            <div class="card">
                <div class="card-icon"><i class="fas fa-tree"></i></div>
                <h3>Zona rural</h3>
                <p>Solo el 2% del territorio es rural. Vereda Isla Cabica en el río Magdalena, además de fincas al suroeste en límites con Galapa y Malambo. Tierras planas y cenagosas cerca al río.</p>
                <div class="inline-image"><img src="isla-cabica.jpg" alt="Isla Cabica" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%233a6ea5%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23f5c842%22%3EVereda%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
            </div>
        </div>
        <div class="card reveal">
            <div class="card-icon"><i class="fas fa-map"></i></div>
            <h3>Localización geográfica</h3>
            <p><a class="map-link" href="#" onclick="alert('Soledad en el departamento del Atlántico, área metropolitana de Barranquilla.'); return false;">Ver mapa en el Atlántico</a> | <a class="map-link" href="#" onclick="alert('Soledad en la costa Caribe de Colombia.'); return false;">Ubicación en Colombia</a></p>
            <div class="inline-image"><img src="mapa-soledad-atlantico.png" alt="Mapa Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23405a7a%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23f5c842%22%3EMapa%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
        </div>
    </div>
</section>

<!-- Simón Bolívar -->
<section id="bolivar" class="section">
    <div class="section-container">
        <div class="section-header reveal">
            <div class="section-tag">HUELLAS DEL LIBERTADOR</div>
            <h2 class="section-title">Simón Bolívar en <em>Soledad</em></h2>
        </div>
        <div class="card reveal">
            <div class="card-icon"><i class="fas fa-landmark"></i></div>
            <h3>Tres visitas históricas</h3>
            <ul>
                <li><strong>22 de agosto de 1820:</strong> Primera visita, anima tropas para la retoma del Caribe, recibido por el General Mariano Montilla.</li>
                <li><strong>28 de diciembre de 1820:</strong> Acompaña a Antonio Nariño en su postulación como representante; el Consejo Electoral se reúne en la Parroquia San Antonio de Padua.</li>
                <li><strong>4 de octubre de 1830:</strong> Última visita, hospedado en la casa de Pedro Juan Visbal (hoy Casa Museo Bolivariano). Escribe 23 cartas, entre ellas la "última proclama". Permanece hasta el 7 de noviembre, luego parte a Santa Marta donde fallece el 17 de diciembre.</li>
            </ul>
            <p>Además, en 1860 Soledad fue campo de batalla entre liberales y conservadores.</p>
            <div class="inline-image"><img src="bolivar-soledad.jpg" alt="Bolívar en Soledad" onerror="this.src='data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20width%3D%22300%22%20height%3D%22200%22%3E%3Crect%20width%3D%22300%22%20height%3D%22200%22%20fill%3D%22%23992233%22%2F%3E%3Ctext%20x%3D%22150%22%20y%3D%22110%22%20fill%3D%22%23f5c842%22%3EBol%C3%ADvar%3C%2Ftext%3E%3C%2Fsvg%3E';"></div>
        </div>
    </div>
</section>

<footer>
    <p>Alcaldía Municipal de Soledad · Secretaría de Cultura y Turismo</p>
    <p class="motto">“Soledad, corazón del Caribe: historia, tradición, poesía, carnaval y libertad”</p>
    <p>Plaza Mayor de Soledad · Casa Museo Simón Bolívar · Iglesia San Antonio de Padua</p>
    <p>Secretaría de Cultura: cultura@soledad-atlantico.gov.co · Línea de atención: 605 319 79 38</p>
</footer>

<div class="float-btn" onclick="alert('📍 Soledad: cuna del merecumbé, butifarra, poetas y gestas libertarias. ¡Orgullo soledeño!')">
    <i class="fas fa-map-marked-alt"></i>
</div>

<script>
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add('visible');
            }
        });
    }, { threshold: 0.1 });
    document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            e.preventDefault();
            const target = document.querySelector(this.getAttribute('href'));
            if (target) target.scrollIntoView({ behavior: 'smooth' });
        });
    });
</script>
</body>
</html>
