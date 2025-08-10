index.html
<!DOCTYPE html>
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
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #ffffff;
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 50%, #1a1a1a 100%);
            min-height: 100vh;
            overflow-x: hidden;
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
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .particle:nth-child(1) { top: 20%; left: 10%; animation-delay: 0s; }
        .particle:nth-child(2) { top: 60%; left: 20%; animation-delay: 2s; }
        .particle:nth-child(3) { top: 40%; left: 80%; animation-delay: 4s; }
        .particle:nth-child(4) { top: 80%; left: 70%; animation-delay: 1s; }
        .particle:nth-child(5) { top: 30%; left: 50%; animation-delay: 3s; }

        header {
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 165, 0, 0.2);
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
            font-weight: 500;
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
            transition: transform 0.3s ease;
        }

        .donate-btn:hover {
            transform: translateY(-2px);
        }

        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            background: radial-gradient(circle at center, rgba(255, 140, 0, 0.1) 0%, transparent 50%);
        }

        .hero-content {
            max-width: 800px;
            padding: 0 2rem;
            z-index: 10;
            position: relative;
        }

        .hero h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #ffffff, #ff8c00);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }

        .hero-subtitle {
            font-size: 1.3rem;
            color: #cccccc;
            margin-bottom: 2rem;
            font-weight: 300;
        }

        .hero-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-primary, .btn-secondary {
            padding: 1rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(45deg, #ff8c00, #ff6b35);
            color: white;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
        }

        .btn-primary:hover, .btn-secondary:hover {
            transform: translateY(-3px);
        }

        section {
            padding: 5rem 2rem;
            position: relative;
            z-index: 10;
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

        .section-subtitle {
            text-align: center;
            font-size: 1.2rem;
            color: #cccccc;
            margin-bottom: 3rem;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid rgba(255, 165, 0, 0.2);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #ff8c00, #ff6b35);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.08);
        }

        .card:hover::before {
            opacity: 1;
        }

        .card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: #ff8c00;
        }

        .card p {
            color: #cccccc;
            line-height: 1.6;
        }

        .donations {
            background: rgba(0, 0, 0, 0.5);
            backdrop-filter: blur(10px);
        }

        .donation-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .donation-card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            text-align: center;
            border: 1px solid rgba(255, 165, 0, 0.2);
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .donation-card:hover {
            transform: translateY(-5px) scale(1.02);
            background: rgba(255, 140, 0, 0.1);
        }

        .donation-amount {
            font-size: 2rem;
            font-weight: 700;
            color: #ff8c00;
            margin-bottom: 0.5rem;
        }

        .donation-purpose {
            color: #cccccc;
            margin-bottom: 1.5rem;
        }

        .iban-section {
            background: rgba(255, 140, 0, 0.1);
            border-radius: 15px;
            padding: 2rem;
            margin: 3rem 0;
            text-align: center;
            border: 1px solid rgba(255, 140, 0, 0.3);
        }

        .iban-code {
            font-family: 'Courier New', monospace;
            font-size: 1.3rem;
            font-weight: 700;
            color: #ff8c00;
            background: rgba(0, 0, 0, 0.3);
            padding: 1rem;
            border-radius: 10px;
            margin: 1rem 0;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .copy-btn {
            background: #ff8c00;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .copy-btn:hover {
            background: #ff6b35;
            transform: scale(1.05);
        }

        .table-container {
            overflow-x: auto;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 2rem;
            margin: 2rem 0;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 800px;
        }

        th, td {
            padding: 1rem;
            text-align: left;
            border-bottom: 1px solid rgba(255, 165, 0, 0.2);
        }

        th {
            background: rgba(255, 140, 0, 0.2);
            color: #ff8c00;
            font-weight: 600;
        }

        td {
            color: #cccccc;
        }

        tr:hover {
            background: rgba(255, 140, 0, 0.1);
        }

        .timeline {
            position: relative;
            max-width: 800px;
            margin: 3rem auto;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, #ff8c00, #ff6b35);
            transform: translateX(-50%);
        }

        .timeline-item {
            position: relative;
            margin: 2rem 0;
            width: 50%;
        }

        .timeline-item:nth-child(even) {
            left: 50%;
            padding-left: 2rem;
        }

        .timeline-item:nth-child(odd) {
            padding-right: 2rem;
        }

        .timeline-content {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            padding: 1.5rem;
            border-radius: 15px;
            border: 1px solid rgba(255, 165, 0, 0.2);
            position: relative;
        }

        .timeline-date {
            color: #ff8c00;
            font-weight: 600;
            margin-bottom: 0.5rem;
        }

        footer {
            background: rgba(0, 0, 0, 0.8);
            backdrop-filter: blur(10px);
            padding: 3rem 2rem 1rem;
            border-top: 1px solid rgba(255, 165, 0, 0.2);
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            color: #ff8c00;
            margin-bottom: 1rem;
        }

        .footer-section p, .footer-section a {
            color: #cccccc;
            text-decoration: none;
            line-height: 1.8;
        }

        .footer-section a:hover {
            color: #ff8c00;
        }

        .footer-bottom {
            text-align: center;
            margin-top: 2rem;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 165, 0, 0.2);
            color: #999999;
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-subtitle {
                font-size: 1.1rem;
            }

            .hero-buttons {
                flex-direction: column;
                align-items: center;
            }

            .timeline::before {
                left: 20px;
            }

            .timeline-item {
                width: 100%;
                left: 0 !important;
                padding-left: 3rem !important;
                padding-right: 1rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .cards-grid {
                grid-template-columns: 1fr;
            }

            .iban-code {
                flex-direction: column;
                gap: 1rem;
            }
        }

        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .copy-success {
            background: #4CAF50 !important;
            transform: scale(1.1) !important;
        }
    </style>
</head>
<body>
    <div class="particles">
        <div class="particle"></div>
        <div class="particle"></div>
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
                <li><a href="#sammeln">Sammeln</a></li>
                <li><a href="#kontakt">Kontakt</a></li>
            </ul>
            <a href="#spenden" class="donate-btn">Jetzt Spenden</a>
        </nav>
    </header>

    <section class="hero" id="home">
        <div class="hero-content fade-in">
            <h1>Verzicht der Einen bringt Leben & Hoffnung für die Anderen</h1>
            <p class="hero-subtitle">Das Hilfswerk "Aktion Verzicht" leistet Unterstützung in einem Umfeld, das jüdisches Leben erschwert. Wir leben in der Haltung "weniger ist genug" und verzichten, damit mehr bleibt zum Teilen.</p>
            <div class="hero-buttons">
                <a href="#spenden" class="btn-primary">Jetzt Spenden</a>
                <a href="#projekte" class="btn-secondary">Unsere Projekte</a>
            </div>
        </div>
    </section>

    <section id="projekte">
        <div class="container">
            <h2 class="section-title fade-in">Unsere Projekte</h2>
            <p class="section-subtitle fade-in">Wir unterstützen Menschen in verschiedenen Ländern mit konkreter Hilfe und Hoffnung.</p>
            
            <div class="cards-grid">
                <div class="card fade-in">
                    <h3>🇺🇦 Ukraine - Region Rivne</h3>
                    <p>Transport und Verteilung von Hilfsgütern, Betrieb einer Suppenküche für Bedürftige in der Kriegsregion.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇺🇦 Ukraine - Boryslav</h3>
                    <p>Suppenküchen, Abgabe von Lebensmittelpaketen und Medikamenten für die notleidende Bevölkerung.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇺🇦 Ukraine - Vinnytsia</h3>
                    <p>Medizinische Hilfe, Suppenküchen und Lebensmittelpakete für verarmte jüdische Menschen.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇺🇦 Ukraine - Shepetovka</h3>
                    <p>Nothilfe für jüdische Menschen, Kinderhort, Suppenküche und Hilfsgüterverteilung.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇺🇦 Ukraine - Charkiw</h3>
                    <p>Suppenküche, Hausbesuche, Lebensmittelpakete für die jüdisch-christliche Gemeinde.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇵🇱 Polen - Fundacja Polania</h3>
                    <p>Unterstützung der polnischen Stiftung bei ihren Einsätzen in den ukrainischen Kriegsgebieten.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇵🇱 Polen - Oswiecim/Auschwitz</h3>
                    <p>Aufklärungs- und Versöhnungsarbeit, Konferenzen und Nothilfe in der Ukraine.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇧🇾 Weissrussland - Minsk</h3>
                    <p>Anlaufstellen für Bedürftige, Suppenküche und Verteilung von Lebensmittelpaketen.</p>
                </div>
                
                <div class="card fade-in">
                    <h3>🇮🇹 Italien - Grosseto, Toskana</h3>
                    <p>Comunità Brezzano - Unterstützung einer therapeutischen Lebensgemeinschaft.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="donations" id="spenden">
        <div class="container">
            <h2 class="section-title fade-in">Ihre Spende macht den Unterschied</h2>
            <p class="section-subtitle fade-in">Jeder Franken zählt. 1 kg Hilfsgüter an den Bestimmungsort zu transportieren kostet ca. Fr. 1.20. Ihre Spende kann vom steuerbaren Einkommen abgezogen werden.</p>
            
            <div class="donation-cards fade-in">
                <div class="donation-card">
                    <div class="donation-amount">CHF 25</div>
                    <p class="donation-purpose">Transportiert 20 kg Hilfsgüter</p>
                </div>
                <div class="donation-card">
                    <div class="donation-amount">CHF 50</div>
                    <p class="donation-purpose">Finanziert eine Woche Suppenküche</p>
                </div>
                <div class="donation-card">
                    <div class="donation-amount">CHF 100</div>
                    <p class="donation-purpose">Unterstützt eine Familie einen Monat</p>
                </div>
                <div class="donation-card">
                    <div class="donation-amount">CHF 250</div>
                    <p class="donation-purpose">Ermöglicht medizinische Hilfe</p>
                </div>
            </div>

            <div class="iban-section fade-in">
                <h3>Spendenkonto</h3>
                <p>Wir sind dankbar für einen Beitrag auf folgendes Konto:</p>
                <div class="iban-code">
                    <span id="iban">CH89 0900 0000 8003 0596 8</span>
                    <button class="copy-btn" onclick="copyIBAN()">IBAN Kopieren</button>
                </div>
                <p><strong>Hilfswerk Aktion Verzicht</strong><br>
                Ihre Spende ist steuerlich absetzbar</p>
            </div>
        </div>
    </section>

    <section id="sammeln">
        <div class="container">
            <h2 class="section-title fade-in">Hilfsgüter sammeln</h2>
            <p class="section-subtitle fade-in">Wir sammeln gut erhaltene und saubere Artikel für unsere Hilfstransporte.</p>
            
            <div class="cards-grid fade-in">
                <div class="card">
                    <h3>👕 Winter- und Sommerkleider</h3>
                    <p>Gut erhaltene Kleider für Kinder und Erwachsene, insbesondere <strong>Winterkleider</strong></p>
                </div>
                
                <div class="card">
                    <h3>👞 Schuhe</h3>
                    <p>Gut erhaltene Schuhe für Kinder und Erwachsene, insbesondere <strong>warme Winterschuhe</strong></p>
                </div>
                
                <div class="card">
                    <h3>🔥 Elektro-Öfen</h3>
                    <p>Für den Winter in der Ukraine sammeln wir zuverlässige elektrische Öfen in gutem Zustand!</p>
                </div>
                
                <div class="card">
                    <h3>⚡ Strom-Generatoren</h3>
                    <p>Wir suchen Stromerzeuger, um die defekte Stromversorgung der Ukraine zu überbrücken.</p>
                </div>
                
                <div class="card">
                    <h3>🛏️ Schlafsäcke, Matratzen</h3>
                    <p>Wir sammeln für die Flüchtlinge in der Ukraine saubere Schlafsäcke und Matratzen.</p>
                </div>
                
                <div class="card">
                    <h3>🏥 Sanitätsmaterial</h3>
                    <p>Gehhilfen aller Art, elastische Binden, Gazekompressen, Heftpflaster, etc.</p>
                </div>
            </div>

            <h3 class="section-title fade-in" style="margin-top: 4rem;">Sammelstellen</h3>
            <div class="table-container fade-in">
                <table>
                    <thead>
                        <tr>
                            <th>Ort</th>
                            <th>Name</th>
                            <th>Adresse</th>
                            <th>Telefon</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>3627 Heimberg</td>
                            <td>Maja Schild</td>
                            <td>Buechwaldstrasse 10</td>
                            <td>079 600 50 56</td>
                        </tr>
                        <tr>
                            <td>4055 Basel</td>
                            <td>Kirchgemeinde Thomas (Daniel Häsler)</td>
                            <td>Hegenheimerstrasse 231</td>
                            <td>061 386 92 44</td>
                        </tr>
                        <tr>
                            <td>4522 Rüttenen</td>
                            <td>Urs Zürcher</td>
                            <td>Verenahofweg 3</td>
                            <td>079 209 34 75</td>
                        </tr>
                        <tr>
                            <td>4632 Trimbach</td>
                            <td>Borner Transport und Lagerhaus AG</td>
                            <td>Industriestrasse 11</td>
                            <td>062 289 50 20</td>
                        </tr>
                        <tr>
                            <td>4852 Rothrist</td>
                            <td>Fabienne und Florian Wirz</td>
                            <td>Stockweg 19c</td>
                            <td>062 794 12 91</td>
                        </tr>
                        <tr>
                            <td>8032 Zürich</td>
                            <td>Ernst Baumann</td>
                            <td>Schleifergasse 2</td>
                            <td>078 972 22 11</td>
                        </tr>
                        <tr>
                            <td>8303 Bassersdorf</td>
                            <td>Heidi Landis</td>
                            <td>Brunnenstrasse 2</td>
                            <td>044 836 79 89</td>
                        </tr>
                        <tr>
                            <td>8712 Stäfa</td>
                            <td>Hans und Ruth Lendi</td>
                            <td>Laubstenstrasse 18i</td>
                            <td>044 926 20 50</td>
                        </tr>
                        <tr>
                            <td>8911 Rifferswil</td>
                            <td>Heinz und Helga Guidon</td>
                            <td>Zeisenbergstrasse 7</td>
                            <td>044 764 14 85</td>
                        </tr>
                        <tr>
                            <td>9545 Wängi</td>
                            <td>Vreni Immoos</td>
                            <td>Hüslibachweg 2</td>
                            <td>077 422 48 22</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </div>
    </section>

    <section>
        <div class="container">
            <h2 class="section-title fade-in">Termine</h2>
            
            <div class="timeline fade-in">
                <div class="timeline-item">
                    <div class="timeline-content">
                        <div class="timeline-date">30. August 2025</div>
                        <h3>Flohmarkt: 9h - 15h</h3>
                        <p>Brückenweg 22, 4528 Zuchwil<br>
                        Kontakt: Urs Zürcher: 079 209 34 75</p>
                    </div>
                </div>
                
                <div class="timeline-item">
                    <div class="timeline-content">
                        <div class="timeline-date">20. September 2025</div>
                        <h3>AV-Freundestreffen in Zuchwil</h3>
                        <p>ab 13:30h bis ca. 17h<br>
                        Herzlich willkommen am Brückenweg 22<br>
                        Eine Anmeldung ist nicht erforderlich!</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section>
        <div class="container">
            <h2 class="section-title fade-in">Unser Leitbild</h2>
            
            <div class="cards-grid fade-in">
                <div class="card">
                    <h3>Was wir tun:</h3>
                    <p>Das Hilfswerk "Aktion-Verzicht" leistet Unterstützung in einem Umfeld, das jüdisches Leben erschwert.</p>
                </div>
                
                <div class="card">
                    <h3>Warum wir es tun:</h3>
                    <p><em>Matthäus 25, 35-36:</em><br><br>
                    Ich war hungrig, ihr gabt mir zu essen;<br>
                    Ich war durstig, ihr gabt mir Wasser;<br>
                    Ich war fremd, ihr habt mich aufgenommen.<br>
                    Ich war nackt, ihr habt mich gekleidet;<br>
                    Ich war krank, ihr habt mich gepflegt;<br>
                    Ich war im Gefängnis, und ihr seid zu mir gekommen.</p>
                </div>
                
                <div class="card">
                    <h3>Wie wir es tun:</h3>
                    <p>Wir leben in der Haltung "weniger ist genug".<br><br>
                    Wir verzichten, damit mehr bleibt zum Teilen.<br><br>
                    Umsonst haben wir empfangen, umsonst geben wir weiter:<br><br>
                    <strong>BARMHERZIGKEIT - MISERICORDIA</strong></p>
                </div>
                
                <div class="card">
                    <h3>Was uns ausmacht:</h3>
                    <p><strong>"Taten sprechen lauter als Worte."</strong></p>
                </div>
            </div>
        </div>
    </section>

    <footer id="kontakt">
        <div class="footer-content">
            <div class="footer-section">
                <h3>Kontakt</h3>
                <p>Hilfswerk Aktion Verzicht<br>
                Schweiz<br><br>
                📧 Email: info@aktion-verzicht.ch<br>
                🌐 Web: www.aktion-verzicht.ch</p>
            </div>
            
            <div class="footer-section">
                <h3>Engagement</h3>
                <p>• Spenden<br>
                • Hilfsgüter sammeln<br>
                • Fahrer für einen guten Zweck<br>
                • Lastwagen beladen<br>
                • Ihr Hilfsprojekt - unser Knowhow</p>
            </div>
            
            <div class="footer-section">
                <h3>Spendenkonto</h3>
                <p><strong>IBAN:</strong><br>
                CH89 0900 0000 8003 0596 8<br><br>
                Ihre Spende ist steuerlich absetzbar</p>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2025 Hilfswerk Aktion Verzicht | Alle Rechte vorbehalten</p>
        </div>
    </footer>

    <script>
        function copyIBAN() {
            const iban = document.getElementById('iban').textContent;
            const button = document.querySelector('.copy-btn');
            
            navigator.clipboard.writeText(iban).then(function() {
                button.textContent = 'Kopiert! ✓';
                button.classList.add('copy-success');
                
                setTimeout(function() {
                    button.textContent = 'IBAN Kopieren';
                    button.classList.remove('copy-success');
                }, 2000);
            });
        }

        function observeElements() {
            const elements = document.querySelectorAll('.fade-in');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, { threshold: 0.1 });

            elements.forEach(el => observer.observe(el));
        }

        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        document.addEventListener('DOMContentLoaded', observeElements);

        document.querySelectorAll('.donation-card').forEach(card => {
            card.addEventListener('click', function() {
                const amount = this.querySelector('.donation-amount').textContent;
                alert(`Vielen Dank für Ihr Interesse an einer Spende von ${amount}! Verwenden Sie unser Spendenkonto: CH89 0900 0000 8003 0596 8`);
            });
        });
    </script>
</body>
</html>
