index.html <!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hilfswerk Aktion Verzicht - Verzicht der Einen bringt Leben & Hoffnung für die Anderen</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            color: #ffffff;
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 50%, #1a1a1a 100%);
            min-height: 100vh;
        }

        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: rgba(255, 165, 0, 0.3);
            border-radius: 50%;
            animation: float 6s infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .particle:nth-child(1) { top: 20%; left: 10%; animation-delay: 0s; }
        .particle:nth-child(2) { top: 60%; left: 20%; animation-delay: 2s; }
        .particle:nth-child(3) { top: 40%; left: 80%; animation-delay: 4s; }

        header {
            background: rgba(0, 0, 0, 0.9);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #ff8c00;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #ffffff;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #ff8c00;
        }

        .donate-btn {
            background: linear-gradient(45deg, #ff8c00, #ff6b35);
            color: white;
            padding: 0.7rem 1.5rem;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffffff, #ff8c00);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-subtitle {
            font-size: 1.3rem;
            color: #cccccc;
            margin-bottom: 2rem;
            max-width: 800px;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff8c00, #ff6b35);
            color: white;
            padding: 1rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            margin: 1rem;
        }

        section {
            padding: 5rem 2rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            color: #ff8c00;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 165, 0, 0.2);
            transition: transform 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
        }

        .card h3 {
            color: #ff8c00;
            margin-bottom: 1rem;
        }

        .card p {
            color: #cccccc;
        }

        .iban-section {
            background: rgba(255, 140, 0, 0.1);
            border-radius: 15px;
            padding: 2rem;
            margin: 3rem 0;
            text-align: center;
        }

        .iban-code {
            font-family: monospace;
            font-size: 1.3rem;
            color: #ff8c00;
            background: rgba(0, 0, 0, 0.3);
            padding: 1rem;
            border-radius: 10px;
            margin: 1rem 0;
        }

        footer {
            background: rgba(0, 0, 0, 0.9);
            padding: 3rem 2rem;
            text-align: center;
            color: #cccccc;
        }

        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero h1 { font-size: 2.5rem; }
            .cards-grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="particles">
        <div class="particle"></div>
        <div class="particle"></div>
        <div class="particle"></div>
    </div>

    <header>
        <nav>
            <div class="logo">Hilfswerk Aktion Verzicht</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#projekte">Projekte</a></li>
                <li><a href="#spenden">Spenden</a></li>
                <li><a href="#kontakt">Kontakt</a></li>
            </ul>
            <a href="#spenden" class="donate-btn">Jetzt Spenden</a>
        </nav>
    </header>

    <section class="hero" id="home">
        <div>
            <h1>Verzicht der Einen bringt Leben & Hoffnung für die Anderen</h1>
            <p class="hero-subtitle">Das Hilfswerk "Aktion Verzicht" leistet Unterstützung in einem Umfeld, das jüdisches Leben erschwert.</p>
            <a href="#spenden" class="btn-primary">Jetzt Spenden</a>
        </div>
    </section>

    <section id="projekte">
        <div class="container">
            <h2 class="section-title">Unsere Projekte</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>🇺🇦 Ukraine - Region Rivne</h3>
                    <p>Transport und Verteilung von Hilfsgütern, Suppenküche.</p>
                </div>
                <div class="card">
                    <h3>🇺🇦 Ukraine - Boryslav</h3>
                    <p>Suppenküchen, Lebensmittelpakete und Medikamente.</p>
                </div>
                <div class="card">
                    <h3>🇵🇱 Polen - Fundacja Polania</h3>
                    <p>Unterstützung bei Einsätzen in ukrainischen Kriegsgebieten.</p>
                </div>
                <div class="card">
                    <h3>🇮🇹 Italien - Grosseto</h3>
                    <p>Comunità Brezzano - therapeutische Lebensgemeinschaft.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="spenden">
        <div class="container">
            <h2 class="section-title">Spenden</h2>
            <div class="iban-section">
                <h3>Spendenkonto</h3>
                <p>Wir sind dankbar für einen Beitrag auf folgendes Konto:</p>
                <div class="iban-code">CH89 0900 0000 8003 0596 8</div>
                <p><strong>Hilfswerk Aktion Verzicht</strong><br>Steuerlich absetzbar</p>
            </div>
        </div>
    </section>

    <footer id="kontakt">
        <h3>Kontakt</h3>
        <p>Hilfswerk Aktion Verzicht<br>
        📧 info@aktion-verzicht.ch<br>
        🌐 www.aktion-verzicht.ch</p>
        <p>&copy; 2025 Hilfswerk Aktion Verzicht</p>
    </footer>
</body>
</html>

