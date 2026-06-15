# kubawujec-sketch.github.io

    <!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Krosno Glass S.A. | Executive Intelligence</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <!-- Google Fonts: Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;900&display=swap" rel="stylesheet">
    
    <!-- Phosphor Icons -->
    <script src="https://unpkg.com/@phosphor-icons/web"></script>

    <style>
        :root {
            --apple-bg: #FFFFFF;
            --apple-text: #000000;
            --apple-gray-light: #F5F5F7;
            --apple-gray-mid: #E5E5EA;
            --apple-gray-dark: #86868B;
            --apple-border: #E5E5EA;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--apple-bg);
            color: var(--apple-text);
            -webkit-font-smoothing: antialiased;
            overflow-x: hidden;
        }

        /* Typography */
        h1, h2, h3, h4 { letter-spacing: -0.03em; }
        
        /* Layout */
        .app-container {
            display: grid;
            grid-template-columns: 280px 1fr;
            min-height: 100vh;
        }

        /* Sidebar Navigation */
        .sidebar {
            background-color: var(--apple-gray-light);
            border-right: 1px solid var(--apple-border);
            padding: 3rem 2rem;
            position: sticky;
            top: 0;
            height: 100vh;
            overflow-y: auto;
        }

        .nav-link {
            display: flex;
            align-items: center;
            padding: 0.875rem 1rem;
            color: var(--apple-gray-dark);
            text-decoration: none;
            border-radius: 0px; 
            margin-bottom: 0.25rem;
            transition: all 0.3s ease;
            font-weight: 400;
            cursor: pointer;
            border-left: 2px solid transparent;
        }

        .nav-link:hover {
            color: var(--apple-text);
            border-left: 2px solid var(--apple-gray-mid);
        }

        .nav-link.active {
            color: var(--apple-text);
            font-weight: 600;
            border-left: 2px solid var(--apple-text);
            background-color: rgba(0,0,0,0.03);
        }

        /* Content Area */
        .main-content {
            padding: 5rem 6rem;
            max-width: 1400px;
            background: var(--apple-bg);
        }

        /* Chart Wrappers & Interactive Cards */
        .interactive-card {
            background: var(--apple-bg);
            border: 1px solid var(--apple-border);
            border-radius: 0px;
            padding: 2rem;
            margin-bottom: 2rem;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
            position: relative;
        }

        .interactive-card:hover {
            box-shadow: 0 10px 30px rgba(0,0,0,0.05);
            border-color: var(--apple-text);
        }

        .interactive-card::after {
            content: 'Rozwiń analizę ▾';
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 0.65rem;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            color: var(--apple-gray-dark);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .interactive-card:hover::after {
            opacity: 1;
        }

        .interactive-card.expanded::after {
            content: 'Zwiń ▴';
            opacity: 1;
        }

        .chart-container {
            position: relative;
            height: 300px;
            width: 100%;
            margin-bottom: 1.5rem;
        }

        /* Storytelling Expander */
        .story-content {
            max-height: 0;
            overflow: hidden;
            opacity: 0;
            transition: max-height 0.8s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.6s ease-in-out, margin-top 0.4s ease;
            border-top: 1px solid transparent;
        }

        .story-content.expanded {
            max-height: 2500px;
            opacity: 1;
            margin-top: 1.5rem;
            padding-top: 1.5rem;
            border-top: 1px solid var(--apple-border);
        }

        /* Timeline Component */
        .timeline {
            border-left: 1px solid var(--apple-text);
            margin-left: 1rem;
            padding-left: 2.5rem;
            margin-top: 3rem;
        }

        .timeline-item {
            position: relative;
            margin-bottom: 3rem;
            cursor: pointer;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -2.85rem;
            top: 0.35rem;
            width: 0.5rem;
            height: 0.5rem;
            background-color: var(--apple-text);
            transition: transform 0.3s ease;
        }

        .timeline-item:hover::before {
            transform: scale(2);
        }

        /* Blockquotes */
        .quote-block {
            border-left: 2px solid var(--apple-text);
            padding-left: 1.5rem;
            margin: 1.5rem 0;
        }
        
        /* Elegant Tables */
        .apple-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.875rem;
            text-align: left;
        }
        .apple-table th {
            padding: 1rem;
            border-bottom: 2px solid var(--apple-text);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            font-size: 0.7rem;
            color: var(--apple-gray-dark);
        }
        .apple-table td {
            padding: 1rem;
            border-bottom: 1px solid var(--apple-border);
            color: var(--apple-text);
        }
        .apple-table tr:last-child td { border-bottom: none; }
    </style>
</head>
<body>

    <div class="app-container">
        <nav class="sidebar">
            <div class="mb-12">
                <div class="text-[10px] font-bold tracking-widest uppercase text-gray-500 mb-2">Executive Intelligence</div>
                <div class="text-2xl font-bold tracking-tight">Krosno Glass.</div>
            </div>
            
            <div class="space-y-2">
                <div class="nav-link active" onclick="switchTab('tab-onepager', this)">
                    <i class="ph ph-chart-line-up text-xl mr-3"></i> Onepager & Finanse
                </div>
                <div class="nav-link" onclick="switchTab('tab-business', this)">
                    <i class="ph ph-strategy text-xl mr-3"></i> Model Biznesowy & SWOT
                </div>
                <div class="nav-link" onclick="switchTab('tab-comms', this)">
                    <i class="ph ph-megaphone text-xl mr-3"></i> Kampanie & Brand House
                </div>
                <div class="nav-link" onclick="switchTab('tab-competitors', this)">
                    <i class="ph ph-crosshair text-xl mr-3"></i> Analiza Konkurencji
                </div>
                <div class="nav-link" onclick="switchTab('tab-trends', this)">
                    <i class="ph ph-trend-up text-xl mr-3"></i> Makrotrendy Rynkowe
                </div>
                <div class="nav-link" onclick="switchTab('tab-people', this)">
                    <i class="ph ph-quotes text-xl mr-3"></i> Ludzie & Cytaty
                </div>
            </div>

            <div class="mt-20">
                <p class="text-[10px] text-gray-400 leading-relaxed uppercase tracking-widest">
                    Zasoby zintegrowane:<br>
                    Dokument Analityczny (85 str.)<br>
                    Deep-Dive Konkurencja (2026)<br>
                    Status: Verified
                </p>
            </div>
        </nav>

        <main class="main-content">
            
            <div id="tab-onepager" class="content-tab block">
                <header class="mb-12">
                    <h2 class="text-xs uppercase tracking-widest text-gray-500 mb-2">Obszar 01</h2>
                    <h1 class="text-5xl font-bold tracking-tight mb-6">Onepager & Finanse</h1>
                    <p class="text-xl font-light text-gray-600 leading-relaxed max-w-4xl">
                        Jeden z największych producentów szkła na świecie. Ponad 100-letnia historia, 80 milionów sztuk rocznej produkcji i głęboka, rygorystyczna transformacja pod kierownictwem nowej prezes, Iwony Pik.
                    </p>
                </header>

                <div class="grid grid-cols-1 lg:grid-cols-5 gap-8 mb-16">
                    
                    <!-- Business Overview -->
                    <div class="lg:col-span-3 space-y-3">
                        <h3 class="text-xs font-bold uppercase tracking-widest text-gray-400 mb-4">Business Snapshot</h3>
                        
                        <div class="interactive-card m-0 p-5 border-t-2 border-t-black" onclick="toggleStory(this)">
                            <div class="flex justify-between items-center"><span class="font-bold text-sm">Skala Wytwórcza & Model Operacyjny</span></div>
                            <div class="story-content text-sm text-gray-700 font-light mt-2 space-y-2">
                                <p><strong>Zintegrowana huta:</strong> Pełna integracja wertykalna (od stopienia piasku po pakowanie) w jednej lokalizacji w Krośnie (4 piece hutnicze). 1400 pracowników.</p>
                                <p><strong>Wolumen:</strong> 80 mln sztuk rocznie, z czego 3 mln to unikalna produkcja ręczna (handmade) generująca najwyższe marże. Równolegle funkcjonują zautomatyzowane linie maszynowe.</p>
                            </div>
                        </div>

                        <div class="interactive-card m-0 p-5 border-t-2 border-t-gray-300" onclick="toggleStory(this)">
                            <div class="flex justify-between items-center"><span class="font-bold text-sm">Zasięg Globalny & E-commerce</span></div>
                            <div class="story-content text-sm text-gray-700 font-light mt-2 space-y-2">
                                <p><strong>Eksport >80%:</strong> Produkty docierają do 70 krajów. Główne rynki to USA, Niemcy, UK, Francja i Australia. Marka jest obecna m.in. w prestiżowej sieci Williams Sonoma (USA).</p>
                                <p><strong>DTC Surge:</strong> Przychody e-commerce urosły z zera w 2019 r. do 46 mln zł (2023). Jesienią 2025 r. kolorowe kieliszki Krosna stały się bestsellerem na Amazon.com w USA, inkasując tytuł "Zdobywcy Ameryki".</p>
                            </div>
                        </div>

                        <div class="interactive-card m-0 p-5 border-t-2 border-t-gray-300" onclick="toggleStory(this)">
                            <div class="flex justify-between items-center"><span class="font-bold text-sm">Kluczowy Pivot: OEM vs Brand Własny</span></div>
                            <div class="story-content text-sm text-gray-700 font-light mt-2 space-y-2">
                                <p><strong>Zdiagnozowany problem:</strong> Do 2025 r. aż 85% produkcji stanowiły zlecenia <em>White Label / OEM</em>. Krosno ponosiło koszty drogiej energii i emisji $CO_2$, sprzedając tanio nieobrandowane szkło. Własny brand stanowił tylko 15%.</p>
                                <p><strong>Cel nowej prezes:</strong> Radykalne odwrócenie proporcji. Wzrost udziału marki własnej do ponad 50%, odzyskanie marży detalicznej poprzez platformy DTC i powrót na GPW w 2028-2029 r.</p>
                            </div>
                        </div>
                    </div>

                    <!-- Communication Landscape -->
                    <div class="lg:col-span-2 bg-gray-50 border border-gray-200 p-6 flex flex-col justify-between">
                        <div>
                            <h3 class="text-xs font-bold uppercase tracking-widest text-black mb-4 border-b border-gray-200 pb-2">Comm Landscape</h3>
                            <div class="mb-4">
                                <div class="text-[9px] uppercase tracking-widest text-gray-500 font-bold mb-1">Key Message / Purpose</div>
                                <p class="text-sm font-light italic">"Od 100 lat dodaje blasku chwilom. Przez piękno ręcznie tworzonego szkła uświetniamy ludzkie chwile i niesiemy polskie rzemiosło w świat."</p>
                            </div>
                            <div class="mb-4">
                                <div class="text-[9px] uppercase tracking-widest text-gray-500 font-bold mb-1">Kluczowe Filary (Pillars)</div>
                                <ul class="text-xs font-medium space-y-1">
                                    <li><span class="text-gray-400">01</span> Artisanal Excellence (Rzemiosło)</li>
                                    <li><span class="text-gray-400">02</span> Innovative Tradition (Design)</li>
                                    <li><span class="text-gray-400">03</span> Moments & Emotions (Lifestyle)</li>
                                    <li><span class="text-gray-400">04</span> Global Polish Pride (Dziedzictwo)</li>
                                </ul>
                            </div>
                            <div>
                                <div class="text-[9px] uppercase tracking-widest text-gray-500 font-bold mb-1">Target Audience & Trend</div>
                                <p class="text-xs font-light text-gray-700">Osoby poszukujące <span class="font-bold">Accessible Premium</span> (30-55 lat). Komunikacja wspierana trendem "Home Entertaining" oraz odwrotem od jednorazowego plastiku (Zero-waste).</p>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="interactive-card" onclick="toggleStory(this)">
                    <h3 class="text-xl font-bold mb-6">Trakcja Finansowa i Fluktuacje (2019-2026)</h3>
                    <p class="text-xs text-gray-500 mb-4">Kliknij w kartę, aby zrozumieć rynkowe przyczyny szczytu i kryzysu.</p>
                    <div class="chart-container">
                        <canvas id="chart-finance"></canvas>
                    </div>
                    
                    <div class="story-content text-gray-800 font-light leading-relaxed space-y-4">
                        <h4 class="font-bold text-sm uppercase tracking-widest text-black mb-2">Interpretacja Analityczna (Storytelling)</h4>
                        <p><strong>Fenomen roku 2022 (Hossa):</strong> Wykres wyraźnie pokazuje szczyt przychodów (363 mln zł) i potężną rentowność operacyjną (EBITDA 78,9 mln zł). Dlaczego? To bezpośredni efekt popandemicznego boomu. Konsumenci zamknięci w domach masowo inwestowali w wyposażenie wnętrz (tzw. trend <em>home entertaining</em>).</p>
                        <p><strong>Dramat lat 2023-2024 (Korekta i Kryzys):</strong> Widzimy drastyczny spadek przychodów do 266 mln zł i zanurkowanie marży głęboko poniżej zera (-27,5 mln zł). Co się stało? Proces hutniczy jest ekstremalnie gazochłonny i energochłonny. Ceny gazu wzrosły ponad dwukrotnie, a energii trzykrotnie w stosunku do 2022 r. Dodatkowo globalny popyt na "home & living" skurczył się. Huta, operując na niskomarżowych zleceniach OEM (produkcja dla innych), nie miała "pricing power", by przenieść te koszty na klienta końcowego.</p>
                        <p><strong>Cel 2026+ (Ucieczka do przodu):</strong> Nowa strategia na 400 mln zł w 2026 i 600 mln w 2028 r. opiera się na radykalnym odcięciu nierentownych kontraktów, wejściu w model Direct-To-Consumer (DTC) na platformie Amazon oraz monetyzacji własnej marki z dużo wyższą marżą.</p>
                    </div>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mt-12">
                    <div class="border-t border-black pt-4">
                        <div class="text-3xl font-light mb-1">1 400</div>
                        <div class="text-xs font-bold text-gray-500 uppercase tracking-widest">Pracowników</div>
                        <p class="text-sm text-gray-600 mt-2 font-light">Bezpośrednie zatrudnienie w jednym, zintegrowanym wertykalnie zakładzie w Krośnie. Byt dla 5000 mieszkańców regionu.</p>
                    </div>
                    <div class="border-t border-black pt-4">
                        <div class="text-3xl font-light mb-1">> 80%</div>
                        <div class="text-xs font-bold text-gray-500 uppercase tracking-widest">Udział Eksportu</div>
                        <p class="text-sm text-gray-600 mt-2 font-light">Wysyłka do blisko 70 krajów świata. Główna wielka piątka: USA, Niemcy, UK, Francja, Australia.</p>
                    </div>
                    <div class="border-t border-black pt-4">
                        <div class="text-3xl font-light mb-1">IPO</div>
                        <div class="text-xs font-bold text-gray-500 uppercase tracking-widest">Cel Strategiczny</div>
                        <p class="text-sm text-gray-600 mt-2 font-light">Przygotowania do powrotu na Giełdę Papierów Wartościowych planowane w okolicach 2028-2029 roku.</p>
                    </div>
                </div>

                <div class="mt-20 mb-16">
                    <h3 class="text-2xl font-bold mb-2">Icebreakers: 3 Business Fun Facts</h3>
                    <p class="text-sm text-gray-500 mb-8">Nieoczywiste, zwalidowane w raporcie anegdoty rynkowe – idealne do otwarcia spotkania (Small Talk) i błyskawicznego zbudowania autorytetu.</p>
                    
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <div class="bg-white border border-gray-200 p-6 hover:border-black transition-colors duration-300 relative overflow-hidden group">
                            <div class="absolute -right-4 -top-4 text-8xl font-black text-gray-50 opacity-50 group-hover:scale-110 transition-transform duration-500 z-0">01</div>
                            <div class="relative z-10">
                                <h4 class="font-bold text-sm uppercase tracking-widest mb-3">Od Cesarzowej do Amazona</h4>
                                <p class="text-sm font-light text-gray-600 leading-relaxed">
                                    W latach 70. i 80. wyroby Krosna zdobiły stoły brytyjskiej Królowej Elżbiety II, Króla Hiszpanii i Cesarzowej Japonii. Dziś dokładnie ta sama aura europejskiego, królewskiego rzemiosła sprawiła, że Krosno zostało bestsellerem na amerykańskim Amazonie, deklasując masową konkurencję algorytmem A9.
                                </p>
                            </div>
                        </div>

                        <div class="bg-white border border-gray-200 p-6 hover:border-black transition-colors duration-300 relative overflow-hidden group">
                            <div class="absolute -right-4 -top-4 text-8xl font-black text-gray-50 opacity-50 group-hover:scale-110 transition-transform duration-500 z-0">02</div>
                            <div class="relative z-10">
                                <h4 class="font-bold text-sm uppercase tracking-widest mb-3">Dekada Mistrzostwa (10 Lat)</h4>
                                <p class="text-sm font-light text-gray-600 leading-relaxed">
                                    Krosno posiada jedyną w Polsce przyzakładową szkołę mistrzostwa hutniczego. Powód? Wykształcenie eksperta formującego najcieńsze, luksusowe kieliszki z precyzją wymaganą przez 5-gwiazdkowe hotele <strong>trwa aż 10 lat</strong>. Tego rzemiosła nie da się "outsource'ować" do taniej fabryki w Azji.
                                </p>
                            </div>
                        </div>

                        <div class="bg-white border border-gray-200 p-6 hover:border-black transition-colors duration-300 relative overflow-hidden group">
                            <div class="absolute -right-4 -top-4 text-8xl font-black text-gray-50 opacity-50 group-hover:scale-110 transition-transform duration-500 z-0">03</div>
                            <div class="relative z-10">
                                <h4 class="font-bold text-sm uppercase tracking-widest mb-3">Pułapka 85% Anonimowości</h4>
                                <p class="text-sm font-light text-gray-600 leading-relaxed">
                                    Miliony ludzi na świecie piją z Krosna, nawet o tym nie wiedząc. Aż 85% produkcji (przed 2025 r.) stanowiły zlecenia kontraktowe <em>White Label</em> dla innych marek. Firma ponosiła 100% kosztów drogiego, polskiego gazu i opłat emisyjnych, oddając cudzym markom całą rynkową premię (marżę).
                                </p>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="mt-16 border-t border-gray-200 pt-12 pb-8">
                    <h3 class="text-2xl font-bold mb-2">Executive Glossary</h3>
                    <p class="text-sm text-gray-500 mb-8">Kluczowe pojęcia analityczne i techniczne dla specyfiki biznesu Krosno Glass.</p>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-6">
                        <div class="border-l-2 border-black pl-4">
                            <h4 class="font-bold text-sm text-black mb-1">Masstige (Accessible Premium)</h4>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Zbitka słów <em>mass</em> i <em>prestige</em>. Kategoria produktów postrzeganych przez konsumenta jako luksusowe, rzemieślnicze (European Handmade), ale wycenionych na poziomie dostępnym dla klasy średniej (€15-€60). Pozwala omijać walkę cenową z Chinami, nie wymagając elitarności marek jak Lalique.</p>
                        </div>
                        
                        <div class="border-l-2 border-gray-300 pl-4">
                            <h4 class="font-bold text-sm text-black mb-1">OEM / White Label</h4>
                            <p class="text-xs text-gray-600 font-light leading-relaxed"><em>Original Equipment Manufacturer</em>. Model produkcji kontraktowej, w którym Krosno wytwarza wyroby szklane projektowane i brandowane pod logo innego (obcego) zleceniodawcy. Generuje stały wolumen, ale drastycznie kompresuje marże (Commodity pricing).</p>
                        </div>
                        
                        <div class="border-l-2 border-gray-300 pl-4">
                            <h4 class="font-bold text-sm text-black mb-1">Szkło Crystalline (Bezołowiowy Kryształ)</h4>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Zaawansowane szkło sodowe z domieszką modyfikatorów (np. tlenek boru). Osiąga wspaniałą przejrzystość, dzwonkowatość i współczynnik załamania światła na poziomie tradycyjnego kryształu ołowiowego, będąc jednak wolnym od toksycznego ołowiu. Trwalsze na matowienie w zmywarkach.</p>
                        </div>
                        
                        <div class="border-l-2 border-gray-300 pl-4">
                            <h4 class="font-bold text-sm text-black mb-1">Metoda Blow-Blow</h4>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Mechaniczny proces formowania szkła (prasowanie kropli, a następnie wydmuchiwanie). Pozwala na wielkoseryjną, zautomatyzowaną produkcję eleganckich kieliszków "z nóżką wyciąganą" (gdzie czarka i nóżka tworzą bezspoinową całość) - kluczowy produkt dla sektora B2B HoReCa.</p>
                        </div>

                        <div class="border-l-2 border-gray-300 pl-4">
                            <h4 class="font-bold text-sm text-black mb-1">EU PPWR</h4>
                            <p class="text-xs text-gray-600 font-light leading-relaxed"><em>Packaging and Packaging Waste Regulation</em>. Nowa, uderzająca w jednorazowy plastik dyrektywa unijna. Tworzy potężny, regulacyjny wiatr w żagle (Tailwind) dla branży szklarskiej, promując materiały w 100% i nieskończenie recyklowalne (tzw. Circular Economy).</p>
                        </div>

                        <div class="border-l-2 border-gray-300 pl-4">
                            <h4 class="font-bold text-sm text-black mb-1">Model DTC (Direct-To-Consumer)</h4>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Strategia ominięcia tradycyjnych hurtowników, importerów i sklepów detalicznych. Krosno sprzedaje bezpośrednio klientowi końcowemu (np. poprzez własny e-commerce lub jako Vendor na platformie Amazon), przechwytując w ten sposób pełną marżę dystrybutorską.</p>
                        </div>
                    </div>
                </div>
            </div>

            <div id="tab-business" class="content-tab hidden">
                <header class="mb-16">
                    <h2 class="text-xs uppercase tracking-widest text-gray-500 mb-2">Obszar 02</h2>
                    <h1 class="text-5xl font-bold tracking-tight mb-6">Model Biznesowy & SWOT</h1>
                    <p class="text-xl font-light text-gray-600 leading-relaxed max-w-4xl">
                        Ewolucja z "taniej fabryki" uzależnionej od obcych kontraktów w suwerenny brand <span class="font-bold">Accessible Premium</span>. Analiza struktury, przewag rynkowych i makroekonomicznych wyzwań nowej strategii.
                    </p>
                </header>

                <div class="mb-16">
                    <h3 class="text-sm font-bold uppercase tracking-widest text-black mb-6 border-b border-gray-200 pb-2">Fundament Wytwórczy: Dualny Model Biznesowy</h3>
                    
                    <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 mb-8">
                        <div class="bg-gray-50 p-8 border border-gray-200">
                            <div class="flex items-center mb-4">
                                <div class="w-2 h-2 bg-black rounded-full mr-3"></div>
                                <h4 class="text-2xl font-light tracking-tight">Segment Premium (Artisanal)</h4>
                            </div>
                            <p class="text-sm font-light text-gray-600 mb-6 leading-relaxed">
                                Największa w Europie ręczna produkcja szkła. To serce pozycjonowania marki (Heritage) i generator najwyższych marż (Premium Pricing). 
                            </p>
                            <ul class="space-y-3 text-xs font-medium border-t border-gray-200 pt-4">
                                <li class="flex justify-between"><span>Wolumen Roczny:</span> <span class="text-gray-500">~3 miliony sztuk</span></li>
                                <li class="flex justify-between"><span>Technologia:</span> <span class="text-gray-500">Ręczne formowanie (Handmade)</span></li>
                                <li class="flex justify-between"><span>Pricing (Detal):</span> <span class="text-gray-500">80 - 300+ PLN / szt.</span></li>
                                <li class="flex justify-between"><span>Kluczowe Linie:</span> <span class="text-gray-500">KROSNO D'SIGN, Celebration</span></li>
                            </ul>
                        </div>

                        <div class="bg-white p-8 border border-gray-200 shadow-sm">
                            <div class="flex items-center mb-4">
                                <div class="w-2 h-2 bg-gray-400 rounded-full mr-3"></div>
                                <h4 class="text-2xl font-light tracking-tight">Segment Masowy & HoReCa</h4>
                            </div>
                            <p class="text-sm font-light text-gray-600 mb-6 leading-relaxed">
                                Zautomatyzowane linie gwarantujące skalę, powtarzalność i penetrację kanałów profesjonalnych (gastronomia) oraz masowego retailu.
                            </p>
                            <ul class="space-y-3 text-xs font-medium border-t border-gray-200 pt-4">
                                <li class="flex justify-between"><span>Wolumen Roczny:</span> <span class="text-gray-500">~77 milionów sztuk</span></li>
                                <li class="flex justify-between"><span>Technologia:</span> <span class="text-gray-500">Maszynowa (Blow-Blow)</span></li>
                                <li class="flex justify-between"><span>Pricing (Detal):</span> <span class="text-gray-500">10 - 25 PLN / szt.</span></li>
                                <li class="flex justify-between"><span>Kluczowe Linie:</span> <span class="text-gray-500">XNO (HoReCa), Infinity</span></li>
                            </ul>
                        </div>
                    </div>

                    <div class="bg-black text-white p-8 relative overflow-hidden">
                        <div class="relative z-10 grid grid-cols-1 md:grid-cols-3 gap-8 items-center">
                            <div class="md:col-span-2">
                                <h4 class="text-[10px] font-bold uppercase tracking-widest text-gray-400 mb-2">Kluczowy Kierunek Strategiczny (Pivot 2025+)</h4>
                                <p class="text-lg font-light leading-relaxed mb-4">
                                    Historycznie huta funkcjonowała jako "OEM Trap" – 85% potężnych mocy maszynowych sprzedawano tanio pod obce marki, ponosząc 100% obciążeń energetycznych. Nowy zarząd wymusza ucieczkę do przodu: <span class="font-bold text-white">wzrost udziału marki własnej KROSNO do ponad 50%</span> oraz ekspansję Direct-To-Consumer (Amazon), aby odzyskać pełną marżę.
                                </p>
                            </div>
                            <div class="border-l border-gray-700 pl-6">
                                <i class="ph-fill ph-quotes text-3xl text-gray-600 mb-2 block"></i>
                                <p class="text-sm italic font-light text-gray-300">„Krosno to marka narodowa i taki love brand nas wszystkich. Uświadomiłam sobie, że my tego Krosna nie straciliśmy, my go po prostu zakurzyliśmy.”</p>
                                <p class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mt-4">Iwona Pik, Prezes (Sierpień 2025)</p>
                            </div>
                        </div>
                    </div>
                </div>

                <h3 class="text-2xl font-bold mb-6 mt-16">Analityczna Matryca SWOT (Deep-Dive)</h3>
                <p class="text-sm text-gray-500 mb-8">Kliknij obszar, aby rozwinąć szczegółową argumentację biznesową, KPI oraz dowody rynkowe.</p>
                
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-16">
                    <div class="interactive-card border-t-2 border-t-black m-0" onclick="toggleStory(this)">
                        <div class="flex justify-between items-start mb-2">
                            <h4 class="font-bold text-xl">S / Strengths (Siły)</h4>
                            <span class="text-xs bg-gray-100 px-2 py-1 font-bold">Wewnętrzne</span>
                        </div>
                        <p class="text-sm text-gray-600 font-light mt-1">Synergia skali i rzemiosła, 100-letnie Heritage, udowodniona trakcja DTC w USA.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="bg-gray-50 p-4 border border-gray-200">
                                <p class="text-xs font-bold uppercase tracking-widest text-black mb-3">Dowody & Argumentacja Biznesowa</p>
                                <ul class="text-sm font-light text-gray-700 space-y-4">
                                    <li><strong class="text-black">1. Bariera Rzemiosła (Artisanal Barrier):</strong> Krosno to największa ręczna huta w Europie. Szkolenie eksperta tworzącego cienkościenne kieliszki (hotel-grade) trwa 10 lat. Tej przewagi nie da się zreplikować w tanich fabrykach azjatyckich, co chroni markę w segmencie premium.</li>
                                    <li><strong class="text-black">2. Skala + Jakość (Crystalline):</strong> Własna formuła bezołowiowego kryształu (Crystalline) łącząca 80 mln mocy maszynowych z perfekcyjną przejrzystością (zmywarko-odporność), pożądana przez zachodnie sieci HoReCa.</li>
                                    <li><strong class="text-black">3. Product-Market Fit w e-commerce (USA):</strong> Jesienią 2025 r. kolorowe kieliszki Krosna zdobyły tytuł Bestsellera na amerykańskim Amazonie zaledwie 2 miesiące po debiucie. To bezprecedensowy dowód na to, że rynek masowy pożąda europejskiego "Accessible Luxury".</li>
                                    <li><strong class="text-black">4. 100-letnie Brand Equity:</strong> Historia od 1923 r. Obecność na dworze Królowej Elżbiety II. Asertywne "Heritage", na którym opiera się narracja wiarygodności, szczególnie w krajach anglosaskich.</li>
                                </ul>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card border-t-2 border-t-gray-400 m-0" onclick="toggleStory(this)">
                        <div class="flex justify-between items-start mb-2">
                            <h4 class="font-bold text-xl">W / Weaknesses (Słabości)</h4>
                            <span class="text-xs bg-gray-100 px-2 py-1 font-bold">Wewnętrzne</span>
                        </div>
                        <p class="text-sm text-gray-600 font-light mt-1">Gigantyczna presja kosztów ETS, "Pułapka OEM" (85%) i zawirowania właścicielskie.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="bg-gray-50 p-4 border border-gray-200">
                                <p class="text-xs font-bold uppercase tracking-widest text-black mb-3">Dowody & Argumentacja Biznesowa</p>
                                <ul class="text-sm font-light text-gray-700 space-y-4">
                                    <li><strong class="text-black">1. Dramat Rentowności (EBITDA 2024):</strong> Ujemna EBITDA na poziomie <span class="font-bold text-red-600">-27,5 mln zł</span> w 2024 roku, co było brutalnym efektem kosztów drogiego, węglowego prądu z polskiego mixu energetycznego.</li>
                                    <li><strong class="text-black">2. Uzależnienie od "White Label":</strong> Przez dekady huta była "fabryką dla innych". Aż 85% kontraktów to zlecenia OEM, co pozbawiło Krosno kontroli nad ceną detaliczną (Pricing Power) i kompresowało marże.</li>
                                    <li><strong class="text-black">3. Słaba globalna siła marki konsumenckiej (B2C):</strong> W Polsce Krosno to "Love Brand". W Japonii, USA czy UK klienci nie szukają marki per se (Brand Awareness jest niski względem Riedla czy Arc), muszą ją odkrywać algorytmicznie.</li>
                                    <li><strong class="text-black">4. Koncentracja Ryzyka Geograficznego:</strong> W przeciwieństwie do Arc czy Libbey, Krosno ma całą produkcję skupioną w jednym zakładzie na Podkarpaciu (wrażliwość na lokalny rynek pracy i regulacje UE).</li>
                                </ul>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card m-0" onclick="toggleStory(this)">
                        <div class="flex justify-between items-start mb-2">
                            <h4 class="font-bold text-xl">O / Opportunities (Szanse)</h4>
                            <span class="text-xs border border-black px-2 py-1 font-bold">Zewnętrzne</span>
                        </div>
                        <p class="text-sm text-gray-600 font-light mt-1">Trendy anty-plastikowe (PPWR), boom HORECA i rewolucja Direct-to-Consumer.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="bg-white p-4 border border-gray-200">
                                <p class="text-xs font-bold uppercase tracking-widest text-black mb-3">Analiza Szans Rynkowych</p>
                                <ul class="text-sm font-light text-gray-700 space-y-4">
                                    <li><strong class="text-black">1. Dyrektywa EU PPWR (Wiatr w żagle):</strong> Nowe prawo UE (2025) twardo zwalcza plastik. W 100% recyklowalne szkło zyskuje potężny popyt w B2B. To makro-tailwind dla całej branży.</li>
                                    <li><strong class="text-black">2. Premiumizacja & Accessible Luxury:</strong> Klasa średnia odrzuca tanie, jednorazowe produkty. Modne stało się <em>Home Entertaining</em> i domowe bary. Rzeźbione, kolorowe szkło Krosna idealnie wpisuje się w lifestylowe algorytmy Instagrama/TikToka.</li>
                                    <li><strong class="text-black">3. Odbicie globalnego rynku HoReCa:</strong> Branża hospitality wyceniana jest na 4,7 bln USD (rośnie szybko po pandemii). Wprowadzenie dedykowanej linii Krosno XNO (tworzonej z barmanami) to strzał w dziesiątkę.</li>
                                    <li><strong class="text-black">4. Skrócenie łańcucha dostaw (DTC):</strong> Globalne e-commerce pozwala pominąć marżo-żernych pośredników. Model Vendor na platformach (Amazon) oddaje pełen zysk detaliczny producentowi.</li>
                                </ul>
                                <div class="mt-4 p-3 bg-gray-50 text-xs border-l-2 border-black font-medium">
                                    Wniosek rynkowy: Szanse Krosna nie leżą w rewolucji technologicznej, lecz w czysto marketingowym przesunięciu modelu Dystrybucji.
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-t-2 border-red-900 bg-red-50 text-red-900" onclick="toggleStory(this)">
                        <div class="flex justify-between items-start mb-2">
                            <h4 class="font-bold text-xl">T / Threats (Zagrożenia)</h4>
                            <span class="text-xs border border-red-900 px-2 py-1 font-bold">Zewnętrzne</span>
                        </div>
                        <p class="text-sm text-red-800 font-light mt-1">Zabójcze koszty ETS, tania Azja, wymierający zawód hutnika.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="bg-white p-4 border border-red-200">
                                <p class="text-xs font-bold uppercase tracking-widest text-red-900 mb-3">Mierniki Ryzyka</p>
                                <ul class="text-sm font-light text-red-800 space-y-4">
                                    <li><strong class="text-red-900">1. Brutalny System Węglowy (EU ETS):</strong> Huty szkła są ekstremalnie gazochłonne. Prognozy mówią o wzroście opłat za certyfikaty emisji CO2 nawet do 336 EUR/tona. Konkurenci spoza UE (np. turecki Sisecam) tych opłat nie ponoszą.</li>
                                    <li><strong class="text-red-900">2. Przepaść cenowa (Chiny vs Europa):</strong> Ekspansja chińskiego kryształu dewastuje rynek w obszarze mass-market. Krosno nie może walczyć ceną bez zniszczenia marży.</li>
                                    <li><strong class="text-red-900">3. Wymierający zawód hutnika:</strong> Rzemiosło, które jest największą siłą (Premium), jest fizycznie zagrożone brakiem kadr (starzenie się ekspertów, brak młodych adeptów gotowych na 10-letni trening).</li>
                                    <li><strong class="text-red-900">4. Monopole Dystrybucyjne w USA/UK:</strong> Amerykański sektor HoReCa jest w ok. 60% zdominowany przez historyczne relacje i długoterminowe kontrakty z gigantem Libbey. Przebicie się tam "z ulicy" jest skrajnie trudne.</li>
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="mb-16 border border-gray-300 bg-white shadow-sm">
                    <div class="bg-gray-100 px-8 py-4 border-b border-gray-300">
                        <h3 class="text-lg font-bold text-black uppercase tracking-widest">Makro-Wyzwanie: Koniec Epoki "Taniej Polskiej Fabryki"</h3>
                    </div>
                    <div class="p-8">
                        <p class="text-sm text-gray-700 font-light leading-relaxed mb-6">
                            Polska, a z nią Krosno Glass, historycznie wygrywała na rynkach zachodnich doskonałą relacją jakości do (niskiej) ceny. Ten model właśnie bezpowrotnie upadł. Wzrost kosztów pracy, a przede wszystkim gigantyczne europejskie obciążenia energetyczne (EU ETS) sprawiły, że koszty polskiej produkcji zbliżyły się do zachodnich. Tymczasem zdominowanie rynków masowych przez pozbawioną klimatycznych restrykcji Azję (oraz Turcję) doprowadziło do rynkowej asymetrii.
                        </p>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
                            <div class="border-l-4 border-red-800 pl-4 bg-red-50 p-4">
                                <p class="text-[10px] font-bold uppercase text-red-900 mb-1">Dowód Rynkowy: Przepaść Cenowa (Japonia)</p>
                                <p class="text-sm font-light text-red-800">Analiza importu szkła kryształowego do wymagającej Japonii ujawnia brutalną prawdę: chińskie wyroby wjeżdżają w cenie <strong>~11 943 USD za tonę</strong>, podczas gdy europejski kryształ (np. z Francji) kosztuje astronomiczne <strong>~110 354 USD za tonę</strong>. Wniosek? Frontalna walka na dolnej półce (Commodity) oznacza natychmiastowe bankructwo polskiej huty.</p>
                            </div>
                            
                            <div class="border-l-4 border-black pl-4 bg-gray-50 p-4">
                                <p class="text-[10px] font-bold uppercase text-gray-600 mb-1">Strategia Obronna Zarządu: "Escape to Premium"</p>
                                <p class="text-sm font-light text-gray-800">Nowy zarząd odciął się od pozycjonowania kosztowego. Strategia zakłada radykalne podniesienie percepcji marki i narzucenie "premiery cenowej" poprzez e-commerce. Bronią są: <strong>Europejskie Dziedzictwo (Heritage)</strong>, rzemieślnicze know-how (czego automaty w Azji nie potrafią) oraz unikalny design (kolorowe, rzeźbiarskie szkło, algorytmicznie dopasowane do Amazon A9).</p>
                            </div>
                        </div>

                        <div class="border-t border-gray-200 pt-6">
                            <h4 class="text-sm font-bold text-black mb-4">Gdzie marka potrzebuje wsparcia agencji i konsultantów? (Wyzwania)</h4>
                            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                                <div class="bg-gray-50 p-4">
                                    <span class="text-xs font-bold text-gray-500 uppercase">Wyzwanie 01</span>
                                    <p class="text-sm font-medium mt-1 mb-2">Budowa "Brand Awareness" B2C Globalnie</p>
                                    <p class="text-xs font-light text-gray-600">Skoro unikamy walki cenowej, klienci w USA/UK muszą chcieć kupić markę Krosno (jak Riedel), a nie tylko "kieliszek z Amazona". Jak szybko zbudować kultowy status bez budżetów TV?</p>
                                </div>
                                <div class="bg-gray-50 p-4">
                                    <span class="text-xs font-bold text-gray-500 uppercase">Wyzwanie 02</span>
                                    <p class="text-sm font-medium mt-1 mb-2">Przełamanie B2B Twierdzy HORECA</p>
                                    <p class="text-xs font-light text-gray-600">Amerykańskie hotele i restauracje kupują z przyzwyczajenia u giganta Libbey (60% rynku). Z jakim "koniem trojańskim" B2B powinna wejść tam nowa linia XNO?</p>
                                </div>
                                <div class="bg-gray-50 p-4">
                                    <span class="text-xs font-bold text-gray-500 uppercase">Wyzwanie 03</span>
                                    <p class="text-sm font-medium mt-1 mb-2">Pricing Architecture</p>
                                    <p class="text-xs font-light text-gray-600">Jak wysoko można podnieść ceny produktów "Accessible Premium", by stać się luksusowym, ale jednocześnie nie stracić dotychczasowego obrotu masowego polskiej klasy średniej?</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="mt-16 border-t border-black pt-8">
                    <h3 class="text-2xl font-bold mb-6">Ocena Strategiczna: Krosno w Konkretnych Segmentach</h3>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-8">
                        <div>
                            <div class="flex items-center mb-2">
                                <i class="ph-fill ph-star text-black text-xl mr-2"></i>
                                <h4 class="font-bold text-lg uppercase tracking-widest text-black">Segment Premium (Artisanal)</h4>
                            </div>
                            <p class="text-sm text-gray-600 font-light mb-4">Rynek dóbr rzemieślniczych, limitowanych kolekcji (D'SIGN) oraz prezentów luksusowych. Bezpośrednia konkurencja z dołem portfolio marek takich jak Riedel czy Waterford.</p>
                            <ul class="text-xs space-y-2 border-l-2 border-gray-200 pl-3">
                                <li><span class="font-bold text-green-600">ZALETY (S):</span> Ekstremalnie autentyczny produkt. Ogromna elastyczność dzięki "żywej" manufakturze. Bardzo silna relacja emocjonalna z polskim konsumentem.</li>
                                <li><span class="font-bold text-red-600">SŁABOŚCI (W):</span> Słaby globalny PR designerski. Brak frontmana (Art Directora) znanego w globalnych mediach. Słaba obecność w niszowych, ekskluzywnych galeriach w stolicach zachodnich.</li>
                            </ul>
                        </div>
                        
                        <div>
                            <div class="flex items-center mb-2">
                                <i class="ph-fill ph-buildings text-black text-xl mr-2"></i>
                                <h4 class="font-bold text-lg uppercase tracking-widest text-black">Segment Masowy / HoReCa</h4>
                            </div>
                            <p class="text-sm text-gray-600 font-light mb-4">Rynek wolumenowy, szkło restauracyjne, hotelowe i codzienne B2C (Amazon, department stores). Starcie z potęgami: Arc International, Libbey, Sisecam.</p>
                            <ul class="text-xs space-y-2 border-l-2 border-gray-200 pl-3">
                                <li><span class="font-bold text-green-600">ZALETY (S):</span> Fenomenalny stosunek jakości Crystalline (przejrzystość) do ceny. Świetna, udowodniona już biegłość w optymalizacji algorytmów (DTC Amazon Marketplace).</li>
                                <li><span class="font-bold text-red-600">SŁABOŚCI (W):</span> Porażka cenowa w zderzeniu z graczami spoza UE (Turcja/Chiny - brak ETS). Konieczność polegania na sieciach dystrybutorów, którzy często faworyzują lokalnych gigantów.</li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>

            <div id="tab-comms" class="content-tab hidden">
                <header class="mb-12">
                    <h2 class="text-xs uppercase tracking-widest text-gray-500 mb-2">Obszar 03</h2>
                    <h1 class="text-5xl font-bold tracking-tight mb-6">Kampanie & Brand House</h1>
                </header>

                <div class="mb-12 border border-gray-200 bg-gray-50 p-8 shadow-sm">
                    <h3 class="text-xs font-bold uppercase tracking-widest text-black mb-6">Framework Komunikacyjny: "Get To By"</h3>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <div class="border-t-2 border-black pt-4">
                            <div class="text-xs font-bold text-gray-500 uppercase tracking-widest mb-2">Get (Kto?)</div>
                            <p class="text-sm font-light text-gray-800 leading-relaxed">Osoby 30-55 lat z klasy średniej na rynkach zachodnich oraz restauratorów hołdujących trendowi "Home Entertaining", którzy cenią autentyczność.</p>
                        </div>
                        <div class="border-t-2 border-black pt-4">
                            <div class="text-xs font-bold text-gray-500 uppercase tracking-widest mb-2">To (Akcja?)</div>
                            <p class="text-sm font-light text-gray-800 leading-relaxed">Przestali kupować anonimowe, chińskie szkło i masową ceramikę, na rzecz bezpośredniego wyboru "Accessible Premium" od Krosna.</p>
                        </div>
                        <div class="border-t-2 border-black pt-4">
                            <div class="text-xs font-bold text-gray-500 uppercase tracking-widest mb-2">By (Narzędzie)</div>
                            <p class="text-sm font-light text-gray-800 leading-relaxed">Skrócenie łańcucha DTC (algorytmy Amazon) napędzane storytellingiem 100-letniego dziedzictwa i ekskluzywnymi kooperacjami PR (np. PLL LOT, Karim Rashid).</p>
                        </div>
                    </div>
                </div>

                <div class="interactive-card mb-16 border-t-2 border-black" onclick="toggleStory(this)">
                    <h3 class="text-xl font-bold mb-4">Intensywność Inwestycji Kanałowych (Share of Voice)</h3>
                    <p class="text-xs text-gray-500 mb-6">Wizualizacja szacunkowa oparta na analizie aktywności brandu. Kliknij w kartę, aby poznać dowody analityczne i uzasadnienie wag na osiach "pajęczaka".</p>
                    <div class="chart-container" style="height: 280px;">
                        <canvas id="chart-marketing"></canvas>
                    </div>
                    <div class="story-content text-gray-800 font-light leading-relaxed mt-6">
                        <h4 class="font-bold text-sm uppercase tracking-widest text-black mb-4 border-b border-gray-200 pb-2">Jak powstał ten "Pajęczak"? Dowody Źródłowe</h4>
                        <p class="mb-4">Ewaluacja (1-10) została zrekonstruowana na podstawie twardych ruchów taktycznych Krosna, omijając spalone budżety w tradycyjnych mediach na rzecz chirurgicznych uderzeń w e-commerce i B2B.</p>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mt-6">
                            <div class="bg-gray-50 p-5 border border-gray-100 shadow-sm">
                                <strong class="block text-xs uppercase tracking-widest mb-2 text-black">E-commerce / Amazon (Waga 10/10)</strong>
                                <p class="text-sm font-light">Priorytet #1 nowej strategii DTC. Dowód: Skok przychodów online z 0 zł (2019) do 46 mln zł (2023). Błyskawiczny status bestsellera na Amazon.com w USA (2025) i nagroda "Zdobywcy Ameryki" od Amazon.pl.</p>
                            </div>
                            <div class="bg-gray-50 p-5 border border-gray-100 shadow-sm">
                                <strong class="block text-xs uppercase tracking-widest mb-2 text-black">B2B & Targi (Waga 8/10)</strong>
                                <p class="text-sm font-light">Fundamentalny kanał HoReCa. Dowód: Światowa premiera potężnej, stworzonej z barmanami profesjonalnej kolekcji XNO odbyła się na najbardziej prestiżowych targach barowych Bar Convent Berlin (BCB).</p>
                            </div>
                            <div class="bg-gray-50 p-5 border border-gray-100 shadow-sm">
                                <strong class="block text-xs uppercase tracking-widest mb-2 text-black">Co-branding & B2B PR (Waga 7/10)</strong>
                                <p class="text-sm font-light">Genialny zasięg u grupy docelowej "premium". Dowód: Kontrakt z PLL LOT (2023-2025) - dostawa 700 000 szklanek do klasy biznesowej i dedykowane malowanie kadłuba (livery) dla samolotu Boeing 737 MAX 8.</p>
                            </div>
                            <div class="bg-gray-50 p-5 border border-gray-100 shadow-sm">
                                <strong class="block text-xs uppercase tracking-widest mb-2 text-black">Media Tradycyjne / TV (Waga 1/10)</strong>
                                <p class="text-sm font-light">Dowód negatywny: Raporty nie wskazują na prowadzenie wielomilionowych kampanii telewizyjnych. Marka skutecznie alokuje kapitał z dala od nierentownych "paliw" ATL, skupiając się na lejku konwersji (Performance).</p>
                            </div>
                        </div>
                    </div>
                </div>

                <h3 class="text-2xl font-bold mb-4 mt-16">Architektura: Krosno jako "Branded House"</h3>
                <p class="text-sm font-light text-gray-600 mb-8 max-w-4xl leading-relaxed">
                    Krosno implementuje strategię <strong>Branded House (Dom Marki)</strong>, w której <em>Master Brand</em> dyktuje główne DNA dla wszystkich swoich "dzieci" (kolekcji). Podobnie jak w przypadku Apple, bez względu na to, czy klient obcuje z linią podstawową czy luksusową sub-marką, rdzennym obietnicą (Brand Promise) pozostaje 100-letnie polskie rzemiosło. Pozwala to na drastyczne obniżenie kosztów marketingu – kampania wizerunkowa głównej marki sprzedaje jednocześnie wszystkie linie produktowe.
                </p>
                
                <div class="bg-gray-50 p-8 border border-gray-200 mb-16 flex flex-col items-center relative overflow-hidden">
                    
                    <div class="w-full max-w-3xl border-b-8 border-black text-center pb-8 mb-8 relative z-10">
                        <div class="absolute -top-12 left-1/2 transform -translate-x-1/2 w-0 h-0 border-l-[350px] border-l-transparent border-r-[350px] border-r-transparent border-b-[80px] border-b-gray-200 opacity-40 z-[-1]"></div>
                        <h4 class="text-[10px] uppercase tracking-widest text-gray-500 font-bold mb-3">The Roof (Purpose / Najwyższy Cel)</h4>
                        <p class="text-xl font-light italic text-black leading-relaxed">"Przez piękno ręcznie tworzonego szkła uświetniać ludzkie chwile i nieść polskie rzemiosło przez kolejne stulecia."</p>
                    </div>

                    <div class="w-full max-w-4xl bg-white border border-gray-300 p-6 text-center mb-8 shadow-sm relative z-10">
                        <h4 class="text-[10px] uppercase tracking-widest text-gray-500 font-bold mb-2">The Umbrella / Positioning</h4>
                        <p class="text-lg font-bold text-black tracking-tight">Polska Marka "Accessible Premium"</p>
                        <p class="text-xs text-gray-600 mt-2 font-light max-w-2xl mx-auto">Światowy rzemieślnik łączący niezawodną jakość bezołowiowego kryształu (skala) z estymą 100-letniego rzemiosła artystycznego (unikalność).</p>
                    </div>

                    <div class="w-full max-w-4xl grid grid-cols-1 md:grid-cols-4 gap-4 mb-8 relative z-10">
                        <div class="bg-white border-x border-t border-gray-300 p-5 flex flex-col justify-start text-center shadow-sm h-full">
                            <h4 class="text-[9px] uppercase tracking-widest text-gray-400 font-bold mb-4 border-b border-gray-100 pb-2">Filar 1</h4>
                            <p class="text-sm font-bold text-black mb-3">Artisanal Excellence</p>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Największa ręczna huta szkła w Europie, chroniąca wymierający zawód mistrza hutniczego.</p>
                        </div>
                        <div class="bg-white border-x border-t border-gray-300 p-5 flex flex-col justify-start text-center shadow-sm h-full">
                            <h4 class="text-[9px] uppercase tracking-widest text-gray-400 font-bold mb-4 border-b border-gray-100 pb-2">Filar 2</h4>
                            <p class="text-sm font-bold text-black mb-3">Innovative Tradition</p>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Fuzja stuletniego doświadczenia z nowoczesną elastycznością produkcyjną (2500 nowych SKU w pół roku).</p>
                        </div>
                        <div class="bg-white border-x border-t border-gray-300 p-5 flex flex-col justify-start text-center shadow-sm h-full">
                            <h4 class="text-[9px] uppercase tracking-widest text-gray-400 font-bold mb-4 border-b border-gray-100 pb-2">Filar 3</h4>
                            <p class="text-sm font-bold text-black mb-3">Moments & Emotions</p>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Szkło nie jako sterylne naczynie, lecz cichy, elegancki "uświetniacz" kluczowych wspomnień życiowych.</p>
                        </div>
                        <div class="bg-white border-x border-t border-gray-300 p-5 flex flex-col justify-start text-center shadow-sm h-full">
                            <h4 class="text-[9px] uppercase tracking-widest text-gray-400 font-bold mb-4 border-b border-gray-100 pb-2">Filar 4</h4>
                            <p class="text-sm font-bold text-black mb-3">Global Polish Pride</p>
                            <p class="text-xs text-gray-600 font-light leading-relaxed">Narodowy <em>love brand</em>, ambasador polskiej estetyki z prestiżowymi ekspozycjami zagranicznymi (PLL LOT, Royals).</p>
                        </div>
                    </div>

                    <div class="w-full max-w-5xl bg-black text-white p-8 text-center shadow-xl relative z-10 border-t-4 border-gray-400">
                        <h4 class="text-[10px] uppercase tracking-widest text-gray-400 font-bold mb-4">The Foundation (Reasons To Believe / Dowody)</h4>
                        <div class="flex flex-wrap justify-center gap-x-8 gap-y-4 text-xs font-medium tracking-wide">
                            <span class="flex items-center"><i class="ph-fill ph-check-circle text-gray-500 mr-2"></i> Założenie 1923 r.</span>
                            <span class="flex items-center"><i class="ph-fill ph-check-circle text-gray-500 mr-2"></i> Obecność na 70 rynkach</span>
                            <span class="flex items-center"><i class="ph-fill ph-check-circle text-gray-500 mr-2"></i> Tytuł "Zdobywcy Ameryki" Amazon</span>
                            <span class="flex items-center"><i class="ph-fill ph-check-circle text-gray-500 mr-2"></i> Zmywarko-odporne Crystalline</span>
                            <span class="flex items-center"><i class="ph-fill ph-check-circle text-gray-500 mr-2"></i> Skala: 80 mln szt. rocznie</span>
                        </div>
                    </div>
                </div>

                <h3 class="text-2xl font-bold mb-8 mt-16">Oś Czasu Kluczowych Aktywacji Marketingowych</h3>
                <div class="timeline">
                    
                    <div class="timeline-item" onclick="toggleStory(this)">
                        <div class="text-xs font-bold text-gray-400 mb-1">2018</div>
                        <h4 class="text-lg font-bold mb-1">Soulful Glass & Rebranding</h4>
                        <p class="text-sm font-light text-gray-600">Nowe logo i pozycjonowanie na targach Ambiente we Frankfurcie.</p>
                        <div class="story-content text-sm text-gray-700 font-light mt-3">
                            <p><strong>Działanie:</strong> Agencja Fastline Advertising oraz H2O Creative przeprowadziły potężny rebranding. Wprowadzono nowe logo z dyskretnie ukrytym profilem pracującego hutnika w literach "r" i "o".</p>
                            <p class="mt-2"><strong>Wpływ:</strong> Oddzielenie estetyczne linii Casual (białe opakowania) od linii Premium (czarne, ekskluzywne pudełka). Ustanowienie hasła "Brilliance in glass since 1923".</p>
                        </div>
                    </div>

                    <div class="timeline-item" onclick="toggleStory(this)">
                        <div class="text-xs font-bold text-gray-400 mb-1">2019</div>
                        <h4 class="text-lg font-bold mb-1">KROSNO D'SIGN & Karim Rashid</h4>
                        <p class="text-sm font-light text-gray-600">Przełomowy krok w stronę globalnego designu premium.</p>
                        <div class="story-content text-sm text-gray-700 font-light mt-3">
                            <p><strong>Działanie:</strong> Powołanie ekskluzywnej sub-marki i współpraca z Karimem Rashidem ("najbardziej znanym designerem obu Ameryk"). Powstaje kolekcja SAKRED (16 form, kolorowe szkło: szmaragd, szafir, ametyst, bursztyn).</p>
                            <p class="mt-2"><strong>Wpływ:</strong> Zmiana pozycjonowania marki z dostawcy funkcjonalnego na twórcę <em>Objet d'Art</em>. Kampania szeroko komentowana w mediach premium (Vogue, Elle, Point of Design).</p>
                        </div>
                    </div>

                    <div class="timeline-item" onclick="toggleStory(this)">
                        <div class="text-xs font-bold text-gray-400 mb-1">2023</div>
                        <h4 class="text-lg font-bold mb-1">Jubileusz: "Od 100 lat dodaje blasku chwilom"</h4>
                        <p class="text-sm font-light text-gray-600">Zintegrowana kampania 360° (Focus Nation) i nagroda Orzeł Wprost.</p>
                        <div class="story-content text-sm text-gray-700 font-light mt-3">
                            <p><strong>Działanie:</strong> Holistyczna kampania skupiona wokół jubileuszu 100-lecia (1923-2023). Działania obejmowały influencer marketing, social media, dedykowane sesje foto/wideo dla 17 kolekcji oraz lifestylowy landing page.</p>
                            <p class="mt-2"><strong>Kolekcja Celebration:</strong> Premierze towarzyszyła autorska kolekcja in-house designerki Anny Grabowskiej-Szczur, inspirowana estetyką Art Deco z lat 20. XX wieku.</p>
                        </div>
                    </div>

                    <div class="timeline-item" onclick="toggleStory(this)">
                        <div class="text-xs font-bold text-gray-400 mb-1">2023 - 2025</div>
                        <h4 class="text-lg font-bold mb-1">PLL LOT: "Krosno na pokładach"</h4>
                        <p class="text-sm font-light text-gray-600">Prestiżowe partnerstwo i dystrybucja B2B (Global Polish Pride).</p>
                        <div class="story-content text-sm text-gray-700 font-light mt-3">
                            <p><strong>Działanie:</strong> Gigantyczny kontrakt na dostawę ponad 700 000 sztuk specjalnie zaprojektowanego szkła do klasy LOT Business i Premium Economy. Obejmuje m.in. pierwszą w historii PLL LOT dedykowaną "szampanówkę".</p>
                            <p class="mt-2"><strong>Wizualizacja:</strong> Pasażerski Boeing 737 MAX 8 otrzymał okolicznościowe malowanie (livery) Krosna, kursując przez dwa lata do ponad 100 portów lotniczych na całym świecie. Genialny zasięg PR-owy.</p>
                        </div>
                    </div>

                    <div class="timeline-item" onclick="toggleStory(this)">
                        <div class="text-xs font-bold text-gray-400 mb-1">2025 - 2026</div>
                        <h4 class="text-lg font-bold mb-1">DTC E-commerce: Zdobywca Ameryki na Amazon</h4>
                        <p class="text-sm font-light text-gray-600">Cyfrowa rewolucja w USA i tytuł Bestsellera.</p>
                        <div class="story-content text-sm text-gray-700 font-light mt-3">
                            <p><strong>Działanie:</strong> Przejście z modelu dystrybutorów hurtowych na model Vendor bezpośrednio na amerykańskim Amazon.com.</p>
                            <p class="mt-2"><strong>Wpływ:</strong> Piorunujący sukces. Kolorowe i teksturowane kieliszki stały się bestsellerem na największym rynku świata w zaledwie 2 miesiące. Krosno odebrało prestiżową statuetkę "Zdobywcy Ameryki" na 5. urodzinach Amazon.pl w Polsce. Sprzedaż online osiągnęła pułapy dziesiątek milionów złotych.</p>
                        </div>
                    </div>

                    <div class="timeline-item" onclick="toggleStory(this)">
                        <div class="text-xs font-bold text-gray-400 mb-1">2025 - 2026</div>
                        <h4 class="text-lg font-bold mb-1">B2B HoReCa: Launch Kolekcji XNO (Berlin)</h4>
                        <p class="text-sm font-light text-gray-600">Atak na globalną gastronomię i barmanów.</p>
                        <div class="story-content text-sm text-gray-700 font-light mt-3">
                            <p><strong>Działanie:</strong> Światowa premiera nowej, wysoce wytrzymałej kolekcji XNO ("Zaprojektowanej z Barmanami") na najbardziej elitarnych targach barowych na świecie - Bar Convent Berlin (BCB).</p>
                            <p class="mt-2"><strong>Wpływ:</strong> Otwarcie drogi do rywalizacji z gigantem Libbey o wielomilionowe kontrakty w globalnym hotelarstwie i na rynku fine-dining, gdzie trwałość Crystalline połączona z polską ceną stanowi przewagę.</p>
                        </div>
                    </div>

                </div>

                <div class="mt-24 border-t border-black pt-12">
                    <h3 class="text-2xl font-bold mb-4">Esencja Strategii: Dychotomie Komunikacyjne</h3>
                    <p class="text-sm font-light text-gray-600 mb-8 max-w-3xl leading-relaxed">Radykalne zróżnicowanie narracji (przy jednoczesnym zachowaniu tego samego parasola marki), w zależności od tego, czy mówimy do globalnego konesera poprzez DTC, czy sprzedajemy dziesiątki tysięcy sztuk zaopatrzeniowcowi HoReCa.</p>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                        <div class="border border-gray-200 bg-white shadow-sm overflow-hidden flex flex-col h-full">
                            <div class="bg-gray-100 border-b border-gray-300 p-4">
                                <h4 class="font-bold text-sm text-black uppercase tracking-widest">Wektory Sprzedaży: B2B vs DTC</h4>
                            </div>
                            <div class="flex-1 grid grid-cols-1 sm:grid-cols-2 divide-y sm:divide-y-0 sm:divide-x divide-gray-200">
                                <div class="p-6">
                                    <h5 class="text-xs font-bold text-gray-500 uppercase tracking-widest mb-3">Komunikacja B2B (HoReCa)</h5>
                                    <p class="text-xs font-light text-gray-700 leading-relaxed mb-3">Nacisk na <strong>funkcjonalność i ROI</strong>. Szkło traktowane jako narzędzie ("zaprojektowane z barmanami" - linia XNO). Język twardych korzyści: niezawodność, odporność Crystalline na matowienie.</p>
                                    <p class="text-[10px] uppercase font-bold text-gray-400">Kanały: Targi (BCB Berlin), PR menedżerski</p>
                                </div>
                                <div class="p-6 bg-gray-50">
                                    <h5 class="text-xs font-bold text-black uppercase tracking-widest mb-3">Ekspansja DTC (Amazon)</h5>
                                    <p class="text-xs font-light text-gray-700 leading-relaxed mb-3">Nacisk na <strong>lifestylową estetykę i ucieczkę od pospolitości</strong>. Walka o atencję wzrokową i algorytmy wyszukiwarek (szkło "kolorowe", "żebrowane", "rzemieślnicze").</p>
                                    <p class="text-[10px] uppercase font-bold text-gray-500">Kanały: Amazon A9, Meta Ads, Pinterest</p>
                                </div>
                            </div>
                        </div>

                        <div class="border border-gray-200 bg-white shadow-sm overflow-hidden flex flex-col h-full">
                            <div class="bg-gray-100 border-b border-gray-300 p-4">
                                <h4 class="font-bold text-sm text-black uppercase tracking-widest">Asortyment: Mass Market vs Premium</h4>
                            </div>
                            <div class="flex-1 grid grid-cols-1 sm:grid-cols-2 divide-y sm:divide-y-0 sm:divide-x divide-gray-200">
                                <div class="p-6">
                                    <h5 class="text-xs font-bold text-gray-500 uppercase tracking-widest mb-3">Linie Casual (Maszynowe)</h5>
                                    <p class="text-xs font-light text-gray-700 leading-relaxed mb-3">Codzienna dostępność. Język demokratyczny. Proste szkło dla klasy średniej o silnym potencjale giftingowym. Pakowane często w tańsze, utylitarne opakowania.</p>
                                    <p class="text-[10px] uppercase font-bold text-gray-400">Cel: Wolumen i "Cash Cow"</p>
                                </div>
                                <div class="p-6 bg-gray-50">
                                    <h5 class="text-xs font-bold text-black uppercase tracking-widest mb-3">Nisza Art Glass (D'SIGN)</h5>
                                    <p class="text-xs font-light text-gray-700 leading-relaxed mb-3">Wysoka bariera wejścia. Język wystaw i muzeów (np. Karim Rashid, Art Deco). Czarne, ekskluzywne pudełka. Ręcznie dmuchane perełki, funkcjonujące jako "halo effect".</p>
                                    <p class="text-[10px] uppercase font-bold text-gray-500">Cel: Windowanie prestiżu, High Margin</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="tab-competitors" class="content-tab hidden">
                <header class="mb-12">
                    <h2 class="text-xs uppercase tracking-widest text-gray-500 mb-2">Obszar 04</h2>
                    <h1 class="text-5xl font-bold tracking-tight mb-6">Analiza Konkurencji</h1>
                    <p class="text-xl font-light text-gray-600 leading-relaxed max-w-4xl">
                        Mapowanie globalnego pola bitwy. Od masowych potęg produkcyjnych (Sisecam, Arc), po ultra-luksusowe butiki (Lalique, Lobmeyr). Gdzie znajduje się unikalny "Błękitny Ocean" dla Krosna?
                    </p>
                </header>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-16">
                    <div class="bg-gray-50 border border-gray-200 p-6 shadow-sm border-l-4 border-l-black">
                        <div class="text-[10px] uppercase tracking-widest font-bold text-gray-500 mb-2">Sufit Luksusu (Lalique)</div>
                        <div class="text-4xl font-light mb-2">2 000 €<span class="text-lg text-gray-400">+</span></div>
                        <p class="text-xs font-light text-gray-600 leading-relaxed">Cena maksymalna za pojedynczy artystyczny kieliszek na rynku ultra-premium. Punkt aspiracyjny branży.</p>
                    </div>
                    <div class="bg-gray-50 border border-gray-200 p-6 shadow-sm border-l-4 border-l-gray-400">
                        <div class="text-[10px] uppercase tracking-widest font-bold text-gray-500 mb-2">Masowy Lider (Arc Intl.)</div>
                        <div class="text-4xl font-light mb-2">688 <span class="text-lg text-gray-400">mln €</span></div>
                        <p class="text-xs font-light text-gray-600 leading-relaxed">Przychody największego gracza w 2024 r. (produkcja 4 mln sztuk dziennie). Gigant mass-marketowy.</p>
                    </div>
                    <div class="bg-black text-white border border-gray-200 p-6 shadow-sm border-l-4 border-l-white">
                        <div class="text-[10px] uppercase tracking-widest font-bold text-gray-400 mb-2">Złoty Środek (Krosno)</div>
                        <div class="text-2xl font-bold mb-2 mt-1">Accessible Premium</div>
                        <p class="text-xs font-light text-gray-400 leading-relaxed">Unikanie zabójczej walki cenowej, dostarczając rękodzieło za 15-60 €, deklasując masówki na Amazonie.</p>
                    </div>
                </div>

                <div class="mb-16 border border-gray-200 bg-white p-8 shadow-sm">
                    <h3 class="text-sm font-bold uppercase tracking-widest text-black mb-6 border-b border-gray-200 pb-2">Matryca Pozycjonowania (Premium Strategy Grid)</h3>
                    <p class="text-sm font-light text-gray-600 mb-8">Wizualizacja "błękitnego oceanu". Krosno unika tłoku w segmencie taniej masówki (prawy dół) oraz elitarnego snobizmu bez wolumenu (lewa góra), zajmując unikalną niszę Hybrydową.</p>
                    
                    <div class="relative w-full aspect-[2/1] border-2 border-gray-100 bg-gray-50 mb-4 overflow-hidden text-xs">
                        <div class="absolute inset-0 grid grid-cols-2 grid-rows-2">
                            <div class="border-r border-b border-gray-200 p-4 relative">
                                <span class="absolute top-2 left-2 font-bold text-gray-400 opacity-50 uppercase tracking-widest">Nisza & Ultra-Luksus</span>
                                <div class="absolute top-1/4 left-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Lalique</div>
                                <div class="absolute top-1/2 left-1/3 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Lobmeyr</div>
                                <div class="absolute bottom-1/4 right-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Moser</div>
                            </div>
                            <div class="border-b border-gray-200 p-4 relative bg-gradient-to-br from-gray-50 to-gray-100">
                                <span class="absolute top-2 right-2 font-bold text-gray-400 opacity-50 uppercase tracking-widest text-right">Skala & Prestiż (Accessible)</span>
                                <div class="absolute bottom-1/4 left-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Riedel</div>
                                <div class="absolute bottom-8 left-1/2 bg-black text-white px-4 py-2 shadow-lg font-bold z-10 scale-110">Krosno Glass</div>
                            </div>
                            <div class="border-r border-gray-200 p-4 relative">
                                <span class="absolute bottom-2 left-2 font-bold text-gray-400 opacity-50 uppercase tracking-widest">Premium Rzemiosło (Lok.)</span>
                                <div class="absolute top-1/4 right-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Waterford</div>
                                <div class="absolute bottom-1/4 left-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Kosta Boda</div>
                            </div>
                            <div class="p-4 relative">
                                <span class="absolute bottom-2 right-2 font-bold text-gray-400 opacity-50 uppercase tracking-widest text-right">Mass Market & Commodity</span>
                                <div class="absolute top-1/4 left-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Zwiesel</div>
                                <div class="absolute top-1/2 right-1/4 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium">Libbey</div>
                                <div class="absolute bottom-1/4 right-8 bg-white border border-gray-300 px-3 py-1 shadow-sm font-medium text-gray-500">Sisecam / Arc Intl.</div>
                            </div>
                        </div>
                        <div class="absolute left-0 top-1/2 w-full h-px bg-gray-300"></div>
                        <div class="absolute top-0 left-1/2 h-full w-px bg-gray-300"></div>
                    </div>
                    <div class="flex justify-between text-[10px] uppercase font-bold text-gray-400 tracking-widest">
                        <span>← Rękodzieło (Artisanal)</span>
                        <span>Produkcja Masowa (Scale) →</span>
                    </div>
                </div>

                <div class="mb-16">
                    <h3 class="text-sm font-bold uppercase tracking-widest text-black mb-6">Tabela Porównawcza (Executive View)</h3>
                    <div class="overflow-x-auto border border-gray-200 shadow-sm">
                        <table class="apple-table">
                            <thead class="bg-gray-50">
                                <tr>
                                    <th>Marka</th>
                                    <th>Segment</th>
                                    <th>Cena (€/kiel)</th>
                                    <th>E-commerce</th>
                                    <th>HoReCa</th>
                                    <th>Storytelling Artystyczny</th>
                                </tr>
                            </thead>
                            <tbody>
                                <tr>
                                    <td class="font-bold text-black">Lalique (FRA)</td>
                                    <td>Ultra-Luxury</td>
                                    <td>150 - 2000+</td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Unika</span></td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Słaba</span></td>
                                    <td><span class="px-2 py-1 bg-black text-white font-medium rounded-sm">Wysoki</span></td>
                                </tr>
                                <tr>
                                    <td class="font-bold text-black">Moser (CZE)</td>
                                    <td>Prestige Crystal</td>
                                    <td>80 - 500</td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Własny butik</span></td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Słaba</span></td>
                                    <td><span class="px-2 py-1 bg-black text-white font-medium rounded-sm">Wysoki</span></td>
                                </tr>
                                <tr>
                                    <td class="font-bold text-black">Lobmeyr (AUT)</td>
                                    <td>Art Glass</td>
                                    <td>40 - 500</td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Niska</span></td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Niska</span></td>
                                    <td><span class="px-2 py-1 bg-black text-white font-medium rounded-sm">Wysoki</span></td>
                                </tr>
                                <tr class="bg-gray-50 border-l-4 border-black">
                                    <td class="font-black text-black">KROSNO (POL)</td>
                                    <td class="font-bold">Accessible Premium</td>
                                    <td class="font-bold">10 - 60</td>
                                    <td><span class="px-2 py-1 bg-black text-white font-medium rounded-sm">Amazon Bestseller</span></td>
                                    <td><span class="px-2 py-1 bg-gray-200 text-black font-medium rounded-sm">Dobra</span></td>
                                    <td><span class="px-2 py-1 bg-gray-200 text-black font-medium rounded-sm">Umiarkowany</span></td>
                                </tr>
                                <tr>
                                    <td class="font-bold text-gray-600">Riedel (AUT)</td>
                                    <td>Premium / Sci.</td>
                                    <td>15 - 250</td>
                                    <td><span class="px-2 py-1 bg-black text-white font-medium rounded-sm">Wysoka</span></td>
                                    <td><span class="px-2 py-1 bg-gray-200 text-black font-medium rounded-sm">Dobra</span></td>
                                    <td><span class="px-2 py-1 bg-gray-200 text-black font-medium rounded-sm">Średni</span></td>
                                </tr>
                                <tr>
                                    <td class="font-bold text-gray-600">Arc Intl. (FRA)</td>
                                    <td>Mass Market</td>
                                    <td>3 - 20</td>
                                    <td><span class="px-2 py-1 bg-gray-200 text-black font-medium rounded-sm">Dobra</span></td>
                                    <td><span class="px-2 py-1 bg-black text-white font-medium rounded-sm">Lider</span></td>
                                    <td><span class="px-2 py-1 bg-white border border-gray-300 text-gray-500 rounded-sm">Brak</span></td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>

                <h3 class="text-2xl font-bold mb-6 mt-16">Deep-Dive: Lekcje od Luksusowych Rywali</h3>
                <p class="text-sm font-light text-gray-600 mb-8 max-w-4xl">Rozszerzona analiza kluczowych konkurentów w segmencie premium. Co robią inaczej i czego Krosno musi się od nich nauczyć?</p>
                
                <div class="space-y-4">
                    <div class="interactive-card m-0 border-t-2 border-black" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">Lalique Group (Francja)</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-gray-100 px-2 py-1">Ultra-Luxury</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">Multidimensionalna marka lifestylowa, w której kryształ to tylko jeden z filarów (obok perfum i hotelarstwa).</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="flex items-center space-x-6 border-b border-gray-200 pb-6">
                                <div class="border-l-4 border-black pl-4">
                                    <div class="text-xs uppercase tracking-widest text-gray-500 font-bold mb-1">Przychody (2023)</div>
                                    <div class="text-2xl font-bold">179,2 mln €</div>
                                </div>
                                <div class="border-l-4 border-gray-300 pl-4">
                                    <div class="text-xs uppercase tracking-widest text-gray-500 font-bold mb-1">Segment (Cena)</div>
                                    <div class="text-2xl font-bold">150 - 2000 €</div>
                                </div>
                            </div>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div>
                                    <p class="text-xs font-bold uppercase tracking-widest text-black mb-2">Analiza Strategii (2025-2026)</p>
                                    <p class="text-sm font-light text-gray-700 leading-relaxed">
                                        Lalique pod rządami nowej CEO (Nina Müller) odeszło od bycia "fabryką kryształów". Otworzyli 5-piętrowy flagship w rezydencji Choparda na Manhattanie oraz odnowili kultowy butik przy Rue Royale w Paryżu. Sprzedają <strong>styl życia</strong>. W 2023 zawarli licencję z Mikimoto (perły), łącząc dwa ikoniczne rzemiosła. Zniknęli ze szwajcarskiej giełdy w 2024 (delisting), by w ciszy budować luksus.
                                    </p>
                                </div>
                                <div class="bg-gray-50 p-5 border border-gray-200">
                                    <p class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mb-2">Wniosek dla Krosna</p>
                                    <p class="text-sm font-medium text-black leading-relaxed">
                                        Lalique to aspiracja, nie bezpośredni rywal. Krosno powinno uczyć się od nich budowania aury luksusu (partnerstwa artystyczne), jednocześnie monetyzując to w masowym e-commerce (czego Lalique unika jak ognia).
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-t-2 border-gray-400" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">Moser (Czechy)</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-gray-100 px-2 py-1">Prestige Crystal</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">Historyczny "Król Szkła" i bezpośredni odpowiednik Krosna z Europy Środkowej, pozycjonowany o dwa stopnie wyżej.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="flex items-center space-x-6 border-b border-gray-200 pb-6">
                                <div class="border-l-4 border-black pl-4">
                                    <div class="text-xs uppercase tracking-widest text-gray-500 font-bold mb-1">Przychody (2024)</div>
                                    <div class="text-2xl font-bold">11,4 mln €</div>
                                </div>
                                <div class="border-l-4 border-gray-300 pl-4">
                                    <div class="text-xs uppercase tracking-widest text-gray-500 font-bold mb-1">Skala Produkcji</div>
                                    <div class="text-2xl font-bold">Mała (~250 prac.)</div>
                                </div>
                            </div>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div>
                                    <p class="text-xs font-bold uppercase tracking-widest text-black mb-2">Analiza Strategii (2025-2026)</p>
                                    <p class="text-sm font-light text-gray-700 leading-relaxed">
                                        Firma ma ułamek obrotów Krosna, ale gigantyczny prestiż. W 2024 zdobyli potrójne złoto na Czech Grand Design Awards. Art Director Jan Plecháč prowadzi krucjatę: "Wyjmijmy Moser z gablot". W 2025 otworzyli swój pierwszy butik w Hong Kongu, by łowić zamożnych azjatyckich klientów. Ich kampania na Designblok (szkło jadeitowe i uranowe) to majstersztyk PR-owy.
                                    </p>
                                </div>
                                <div class="bg-gray-50 p-5 border border-gray-200">
                                    <p class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mb-2">Wniosek dla Krosna</p>
                                    <p class="text-sm font-medium text-black leading-relaxed">
                                        Moser pokazuje, że szkło z Europy Środkowej może być obiektem pożądania. Krosno potrzebuje silnej twarzy w mediach wizualnych (Art Directora na miarę Plecháča) i powinno agresywnie wejść na wystawy designu, zachowując przy tym masową dostępność przez Amazon.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-t-2 border-gray-300" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">J. & L. Lobmeyr (Austria)</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-gray-100 px-2 py-1">Art Glass</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">200-letnia, rodzinna wiedeńska manufaktura. Bardziej instytucja kultury niż producent przemysłowy.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6 pt-4 border-t border-gray-100">
                                <div>
                                    <p class="text-xs font-bold uppercase tracking-widest text-black mb-2">Analiza Strategii (2025-2026)</p>
                                    <p class="text-sm font-light text-gray-700 leading-relaxed">
                                        Produkty w MoMA (Nowy Jork) i V&A. Ich absolutny "killer move": kooperacja z reżyserem filmowym Lucą Guadagnino na targach Matter and Shape w Paryżu (2026). Przedstawili tam szkło nie jako naczynie, ale jako "medium kształtowane przez światło i czas". Reprezentowali też Austrię na Expo 2025 w Osace.
                                    </p>
                                </div>
                                <div class="bg-gray-50 p-5 border border-gray-200">
                                    <p class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mb-2">Wniosek dla Krosna</p>
                                    <p class="text-sm font-medium text-black leading-relaxed">
                                        Lekcja storytellingu. Krosno powinno nawiązać współpracę z polskim artystą, reżyserem lub architektem światowej sławy (np. przy okazji Design Weeków), by udowodnić intelektualną głębię marki.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-t-2 border-gray-200" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">Fiskars Group (Waterford & Iittala)</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-gray-100 px-2 py-1">Prestige / Nordic</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">Globalny konglomerat z potężnym kapitałem. Bezpośredni rywale na rynkach UK i w Skandynawii.</p>
                        
                        <div class="story-content mt-6 space-y-6">
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6 pt-4 border-t border-gray-100">
                                <div>
                                    <p class="text-xs font-bold uppercase tracking-widest text-black mb-2">Analiza Portfolio</p>
                                    <p class="text-sm font-light text-gray-700 leading-relaxed">
                                        Grupa Fiskars (1,2 mld EUR przychodów) kontroluje Waterford (irlandzki kryształ) i Iittala (fiński design). Inwestują 15 mln EUR w modernizację fabryki w Słowenii (2024-2026). Iittala stworzyła głośną kolaborację z domem perfumeryjnym Byredo. W UK (kluczowy rynek Krosna), Waterford zgarnia rynek "premium gifting" i dominuje w prestiżowych Department Stores (John Lewis).
                                    </p>
                                </div>
                                <div class="bg-gray-50 p-5 border border-gray-200">
                                    <p class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mb-2">Wniosek dla Krosna</p>
                                    <p class="text-sm font-medium text-black leading-relaxed">
                                        Walka o półkę premium w Wielkiej Brytanii i Skandynawii będzie wymagała od Krosna czegoś więcej niż Amazonu. Konieczne są umowy dystrybucyjne z luksusowymi sieciami (John Lewis, Selfridges), aby móc zrównoważyć ofensywę Waterforda.
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div class="mt-16 bg-black text-white p-8 shadow-xl border-l-4 border-gray-400">
                    <h3 class="text-xl font-bold mb-4 uppercase tracking-widest text-gray-300 text-[11px]">3 Strategiczne Akcje dla Zarządu Krosna</h3>
                    <ul class="space-y-4 text-sm font-light leading-relaxed">
                        <li class="flex items-start">
                            <span class="font-bold text-gray-500 mr-4">01.</span>
                            <p><strong>Wyjście z "Gabloty":</strong> Skopiować mechanizm Mosera. Narzucić narrację "codziennego piękna" z potężnym Art Directorem. Przenieść nacisk z samego produktu na "emocję i design".</p>
                        </li>
                        <li class="flex items-start">
                            <span class="font-bold text-gray-500 mr-4">02.</span>
                            <p><strong>Kolaboracje Multidyscyplinarne:</strong> Lobmeyr pokazał, jak działa mariaż z filmowcem, a Iittala z perfumiarzem (Byredo). Krosno musi zaangażować globalnych twórców kultury (nie tylko inżynierów szkła), aby wejść na salony (PAD London, Milan Design Week).</p>
                        </li>
                        <li class="flex items-start">
                            <span class="font-bold text-gray-500 mr-4">03.</span>
                            <p><strong>Ucieczka w Błękitny Ocean:</strong> Utrzymać ceny 15-60 EUR. To "martwa strefa" dla Lalique (zbyt tanio) i Chin (za drogo, brak heritage). Krosno musi stać się luksusem dla klasy średniej na Amazonie.</p>
                        </li>
                    </ul>
                </div>
            </div>

            <div id="tab-trends" class="content-tab hidden">
                <header class="mb-12">
                    <h2 class="text-xs uppercase tracking-widest text-gray-500 mb-2">Obszar 05</h2>
                    <h1 class="text-5xl font-bold tracking-tight mb-6">Makrotrendy Rynkowe</h1>
                    <p class="text-xl font-light text-gray-600 leading-relaxed max-w-4xl">
                        Rynkowe wiatry w żagle i strukturalne zagrożenia. Jak globalne zmiany w e-commerce, prawie klimatycznym i nawykach lifestylowych determinują sukces marki?
                    </p>
                </header>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-16">
                    <div class="bg-gray-50 border border-gray-200 p-6 shadow-sm border-t-4 border-t-black">
                        <div class="text-[10px] uppercase tracking-widest font-bold text-gray-500 mb-2">Globalny Skok DTC</div>
                        <div class="text-4xl font-light mb-2">2,8 <span class="text-lg text-gray-400">bln $</span></div>
                        <p class="text-xs font-light text-gray-600 leading-relaxed">Szacowana wartość rynku Direct-To-Consumer do 2034. Popyt przesuwa się od hurtowników do platform Vendor (Amazon).</p>
                    </div>
                    <div class="bg-red-50 border border-red-200 p-6 shadow-sm border-t-4 border-t-red-800">
                        <div class="text-[10px] uppercase tracking-widest font-bold text-red-800 mb-2">Koszty Emisji CO2 (Prognoza)</div>
                        <div class="text-4xl font-light text-red-900 mb-2">336 <span class="text-lg text-red-700">€/t</span></div>
                        <p class="text-xs font-light text-red-800 leading-relaxed">Przerażająca prognoza cen certyfikatów EU ETS do 2040 r., uderzająca w polski, energochłonny i oparty na węglu przemysł.</p>
                    </div>
                    <div class="bg-gray-50 border border-gray-200 p-6 shadow-sm border-t-4 border-t-gray-400">
                        <div class="text-[10px] uppercase tracking-widest font-bold text-gray-500 mb-2">Odbicie HoReCa</div>
                        <div class="text-4xl font-light mb-2">4,7 <span class="text-lg text-gray-400">bln $</span></div>
                        <p class="text-xs font-light text-gray-600 leading-relaxed">Wycena globalnej branży hospitality. Restauracje premium i cocktail bary desperacko potrzebują trwałego, ładnego szkła.</p>
                    </div>
                </div>

                <div class="space-y-4">
                    
                    <div class="interactive-card m-0 border-l-4 border-black" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">01. Premiumizacja & "Luxury Home Bars"</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest text-green-600 bg-green-50 px-2 py-1">Tailwind (Szansa)</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">Odrzucenie taniej ceramiki na rzecz estetycznego, rzemieślniczego wyposażenia domowego (Home Entertaining).</p>
                        
                        <div class="story-content mt-6 space-y-4 pt-4 border-t border-gray-100">
                            <p class="text-sm text-gray-700 font-light leading-relaxed"><strong>Kontekst:</strong> Millenialsi i Generacja Z spędzają więcej czasu w domach. Post-pandemiczny nawyk "domowego barmana" sprawił, że konsumenci chętniej inwestują w luksusowe kieliszki, kryształowe dekantery i drogie dodatki, tworząc "Accessible Luxury".</p>
                            <p class="text-sm text-black font-medium leading-relaxed bg-gray-50 p-4 border-l-2 border-black"><strong>Impact dla Krosna:</strong> Krosno idealnie wpasowuje się w niszę. Jest droższe i ładniejsze niż produkty z dyskontu, ale tańsze niż Riedel. Sprzedaje "lifestyle", a nie tylko funkcjonalne naczynie.</p>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-l-4 border-black" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">02. Estetyka #GlassTok (Kolor i Tekstura)</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest text-green-600 bg-green-50 px-2 py-1">Tailwind (Szansa)</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">Powrót szkła barwionego w masie i struktury żebrowanej (ribbed / fluted glass) w algorytmach SoMe.</p>
                        
                        <div class="story-content mt-6 space-y-4 pt-4 border-t border-gray-100">
                            <p class="text-sm text-gray-700 font-light leading-relaxed"><strong>Kontekst:</strong> W latach 2025-2026 estetyka minimalistycznego, gładkiego szkła ustępuje miejsca wyrazistym, rzeźbiarskim formom. Kolorowe kieliszki i wazony z ryflowaniem biją rekordy popularności na TikToku (#GlassTok, #HomeDecor).</p>
                            <p class="text-sm text-black font-medium leading-relaxed bg-gray-50 p-4 border-l-2 border-black"><strong>Impact dla Krosna:</strong> To absolutny strzał w dziesiątkę. Właśnie dzięki limitowanym, kolorowym kieliszkom Krosno zdobyło w 2025 r. tytuł bestsellera na amerykańskim Amazonie, pokonując gigantów. Marka ma technologiczne zaplecze do barwienia masy szklanej (udowodnione kolekcją SAKRED Karima Rashida).</p>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-l-4 border-black" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg">03. Regulacje UE: "Circular Economy" (PPWR)</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest text-green-600 bg-green-50 px-2 py-1">Tailwind (Szansa)</span>
                        </div>
                        <p class="text-sm font-light text-gray-600">Szkło wygrywa z plastikiem. W 100% i nieskończenie recyklowalny materiał zyskuje potężne wsparcie prawne.</p>
                        
                        <div class="story-content mt-6 space-y-4 pt-4 border-t border-gray-100">
                            <p class="text-sm text-gray-700 font-light leading-relaxed"><strong>Kontekst:</strong> W lutym 2025 r. weszła w życie unijna dyrektywa Packaging and Packaging Waste Regulation (PPWR), która brutalnie uderza w jednorazowy plastik. Przemysł europejski osiąga 93% skuteczności w recyklingu stłuczki szklanej.</p>
                            <p class="text-sm text-black font-medium leading-relaxed bg-gray-50 p-4 border-l-2 border-black"><strong>Impact dla Krosna:</strong> Naturalny wiatr w żagle w B2B. Hotele i restauracje (HoReCa) masowo wymieniają akcesoria plastikowe i ceramiczne na trwałe szkło. Szkło Crystalline Krosna wpisuje się w ten ekologiczny trend bezbłędnie (brak komunikacji tego atutu to największy dotychczasowy błąd marki).</p>
                        </div>
                    </div>

                    <div class="interactive-card m-0 border-l-4 border-red-800" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-2">
                            <h4 class="font-bold text-lg text-red-900">04. Zabójcze Koszty Energii i System ETS</h4>
                            <span class="text-[9px] font-bold uppercase tracking-widest text-red-600 bg-red-50 px-2 py-1 border border-red-200">Krytyczne Zagrożenie</span>
                        </div>
                        <p class="text-sm font-light text-red-800">Cena emisji CO2 i gazu dla polskiego przemysłu zabija marże i zdolność do konkurowania z Turcją/Azją.</p>
                        
                        <div class="story-content mt-6 space-y-4 pt-4 border-t border-red-100">
                            <p class="text-sm text-gray-700 font-light leading-relaxed"><strong>Kontekst:</strong> Hutnictwo szkła polega na roztapianiu piasku kwarcowego w temperaturach powyżej 1500°C. To proces ekstremalnie gazochłonny. Polska, ze swoim węglowym mixem energetycznym, nakłada na huty potężne koszty certyfikatów EU ETS. Rywale spoza Unii (chińskie fabryki, turecki Sisecam) operują poza tymi podatkami.</p>
                            <p class="text-sm text-red-900 font-medium leading-relaxed bg-red-50 p-4 border-l-2 border-red-800"><strong>Impact dla Krosna:</strong> Brutalny. To dlatego marża EBITDA zanurkowała do poziomu -27,5 mln zł w 2024 r. Zarząd (Pik) inwestuje miliony w wanny LED i panele słoneczne (prognoza -18 mln zł/rok oszczędności), ale makro-bariera w postaci drogiej polskiej energii zmusza Krosno do trwałej ucieczki w segmenty z wysoką marżą detaliczną (Premium). Walka na dole drabinki cenowej oznacza bankructwo.</p>
                        </div>
                    </div>

                </div>
            </div>

            <div id="tab-people" class="content-tab hidden">
                <header class="mb-16">
                    <h2 class="text-xs uppercase tracking-widest text-gray-500 mb-2">Obszar 06</h2>
                    <h1 class="text-5xl font-bold tracking-tight mb-6">Ludzie, Wizjonerzy & Cytaty</h1>
                    <p class="text-xl font-light text-gray-600 leading-relaxed max-w-4xl">
                        Kapitałem firmy rzemieślniczej nie są wyłącznie maszyny, lecz narracje i historie ludzi, którzy ją prowadzą i rzucają jej wyzwania. Zbiór kluczowych cytatów zarządzających Krosnem oraz strategicznych głosów z firm konkurencyjnych.
                    </p>
                </header>

                <div class="space-y-6">
                    
                    <div class="interactive-card border-t-2 border-black m-0" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-4">
                            <div>
                                <h3 class="text-2xl font-bold">Iwona Pik</h3>
                                <p class="text-xs font-bold uppercase tracking-widest text-gray-400 mt-1">Prezes Zarządu / Główna Właścicielka (od Sierpnia 2025)</p>
                            </div>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-gray-100 px-2 py-1">Wizja Krosna</span>
                        </div>
                        <p class="text-sm font-light text-gray-600 mb-4">Inwestorka (m.in. Polski Holding Rybny), która wprowadza rygorystyczny styl "hands-on" i stawia na ucieczkę od pułapki OEM.</p>
                        
                        <div class="story-content mt-4 pt-4 border-t border-gray-100">
                            <div class="space-y-6">
                                <div class="quote-block">
                                    <p class="text-xl font-light italic mb-3 text-black">„Krosno to marka narodowa i taki love brand nas wszystkich. Uświadomiłam sobie, że my tego Krosna nie straciliśmy, my go po prostu zakurzyliśmy.”</p>
                                    <p class="text-sm font-medium text-gray-500">Komentarz analityczny: Podsumowanie patologii, w którą wpadła huta - wybitny brand był niszczony przez to, że aż 85% produktów sprzedawano z ukrytym logo, nabijając marżę zagranicznym podmiotom.</p>
                                </div>
                                <div class="quote-block">
                                    <p class="text-xl font-light italic mb-3 text-black">„Myślę, że możemy dojść do 600 mln zł w ciągu trzech lat. Chcemy podwoić sprzedaż.”</p>
                                    <p class="text-sm font-medium text-gray-500">Komentarz analityczny: Wypowiedź dla "Biznes Klasa" (Money.pl). Agresywny target wzrostu (+30-33% r/r), oparty na odzyskaniu marży w e-commerce i monetyzacji "Accessible Premium".</p>
                                </div>
                                <div class="quote-block">
                                    <p class="text-xl font-light italic mb-3 text-black">„Jestem na trzech zmianach. Przychodzę o 6 rano [...] o 23 jeszcze idę czasami na mechaniczną przejść się po zakładzie.”</p>
                                    <p class="text-sm font-medium text-gray-500">Komentarz analityczny: Mikrozarządzanie i kontrola operacyjna. Przeciwieństwo "zarządzania z Excela" przez zagraniczne fundusze, które historycznie doprowadziło firmę do kryzysu rentowności w 2024 roku.</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="interactive-card border-t-2 border-gray-400 m-0" onclick="toggleStory(this)">
                        <div class="flex justify-between items-center mb-4">
                            <div>
                                <h3 class="text-2xl font-bold">Paweł Szymański</h3>
                                <p class="text-xs font-bold uppercase tracking-widest text-gray-400 mt-1">Były CEO (2017-2021) / Architekt MBO i Rebrandingu</p>
                            </div>
                            <span class="text-[9px] font-bold uppercase tracking-widest bg-gray-100 px-2 py-1">Dziedzictwo</span>
                        </div>
                        <p class="text-sm font-light text-gray-600 mb-4">Eks-CFO PKN Orlen. Człowiek, który ustawił fundamenty estetyczne Krosna we współpracy z H2O Creative.</p>
                        
                        <div class="story-content mt-4 pt-4 border-t border-gray-100">
                            <div class="quote-block">
                                <p class="text-xl font-light italic mb-3 text-black">„Wszystkie marki i osoby zarządzające muszą myśleć trzytorowo: zachować szacunek do tego, co było w przeszłości, ale jednocześnie odważnie redefiniować przyszłość.”</p>
                                <p class="text-sm font-medium text-gray-500">Komentarz analityczny: Filozofia, która stała za "ewolucyjnym" a nie "rewolucyjnym" rebrandingiem logo. Stare Krosno przeszło w nowe bez utraty rzemieślniczego rodowodu (hutnik ukryty w literach).</p>
                            </div>
                        </div>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="interactive-card border-t-2 border-gray-300 m-0" onclick="toggleStory(this)">
                            <div class="flex justify-between items-start mb-4">
                                <div>
                                    <h3 class="text-xl font-bold">Twórcy & Projektanci</h3>
                                    <p class="text-[9px] font-bold uppercase tracking-widest text-gray-400 mt-1">Kreatorzy Artystyczni</p>
                                </div>
                            </div>
                            <p class="text-sm font-light text-gray-600 mb-4">Karim Rashid (Zewnętrzny Guru) oraz Anna Grabowska-Szczur (Ekspertka In-House z 36-letnim stażem).</p>
                            
                            <div class="story-content mt-4 pt-4 border-t border-gray-100 space-y-4">
                                <div class="quote-block border-l-2 border-gray-300">
                                    <p class="text-sm font-light italic mb-2 text-black">„Razem z Krosno podzielamy filozofię pędu do przodu i reinterpretacji rzeźbiarskich możliwości szkła.”</p>
                                    <p class="text-[10px] font-bold text-gray-500 uppercase tracking-widest">Karim Rashid (O kolekcji SAKRED)</p>
                                </div>
                                <div class="bg-gray-50 p-4 border border-gray-100">
                                    <p class="text-xs font-bold text-black uppercase tracking-widest mb-2">Fundament In-House (Mistrzowie)</p>
                                    <p class="text-xs font-light text-gray-700 leading-relaxed">
                                        Największym skarbem firmy są anonimowi twórcy i mistrzowie. Wykształcenie eksperta formującego cienkościenne kieliszki "hotel-grade" <strong>wymaga 10 lat szlifowania sztuki</strong>. To bariera, której Chińczycy nie pokonają. Anna Grabowska-Szczur jest autorką jubileuszowej linii Celebration, dowodząc, że design wewnętrzny Krosna dotrzymuje kroku trendom.
                                    </p>
                                </div>
                            </div>
                        </div>

                        <div class="interactive-card border-t-2 border-gray-300 m-0" onclick="toggleStory(this)">
                            <div class="flex justify-between items-start mb-4">
                                <div>
                                    <h3 class="text-xl font-bold">Kluczowe Narracje Marki</h3>
                                    <p class="text-[9px] font-bold uppercase tracking-widest text-gray-400 mt-1">Materiały Korporacyjne (Owned Media)</p>
                                </div>
                            </div>
                            <p class="text-sm font-light text-gray-600 mb-4">Cytaty i hasła, które stanowią rdzenną obietnicę marki (Brand Promise) na rynku konsumenckim i w e-commerce.</p>
                            
                            <div class="story-content mt-4 pt-4 border-t border-gray-100 space-y-4">
                                <div class="p-3 bg-gray-50">
                                    <p class="text-sm font-light italic text-black">„Prawdopodobnie ostatnia na świecie huta o takich umiejętnościach w ręcznej produkcji.”</p>
                                </div>
                                <div class="p-3 bg-gray-50">
                                    <p class="text-sm font-light italic text-black">„Z pasji do tworzenia i jakości powstała nasza marka, która od 1923 roku dodaje blasku chwilom.”</p>
                                </div>
                                <div class="p-3 bg-gray-50">
                                    <p class="text-sm font-light italic text-black">„Każdy kieliszek to małe dzieło sztuki.”</p>
                                </div>
                            </div>
                        </div>
                    </div>

                    <div class="mt-16 border-t-4 border-black pt-12">
                        <h3 class="text-2xl font-bold mb-2">Głosy Konkurencji (Benchmark Rynkowy)</h3>
                        <p class="text-sm text-gray-600 mb-8 max-w-4xl font-light">Co mówi konkurencja z segmentu luksusowego (Art Glass & Prestige Crystal)? Ich słowa definiują, w jakim kierunku zmierza branża, stanowiąc darmową, genialną lekcję strategii dla polskiej huty.</p>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                            <div class="border border-gray-200 bg-white p-6 shadow-sm relative overflow-hidden group">
                                <div class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mb-4">Nina Müller — CEO Lalique Group</div>
                                <p class="text-lg font-light italic text-black leading-relaxed mb-6">
                                    „Otwarcie naszego flagshipu w Nowym Jorku jest dowodem na transformację Lalique z domu kryształowego w multidimensionalną markę lifestyle'ową — taką, która buduje ku przyszłości.”
                                </p>
                                <div class="bg-gray-50 p-4 border-l-2 border-black">
                                    <h5 class="text-[9px] font-bold uppercase text-black tracking-widest mb-1">Czego Krosno powinno się tu nauczyć?</h5>
                                    <p class="text-xs font-light text-gray-700">Lalique nie sprzedaje już tylko "kryształu". Sprzedaje lifestyle (dołączając perfumy, biżuterię Mikimoto). Krosno musi przestać być tylko "producentem szklanek" na Amazonie, a stać się marką z kategorii "Sztuka Domowego Życia".</p>
                                </div>
                            </div>

                            <div class="border border-gray-200 bg-white p-6 shadow-sm relative overflow-hidden group">
                                <div class="text-[10px] font-bold uppercase tracking-widest text-gray-500 mb-4">Jan Plecháč — Art Director Moser</div>
                                <p class="text-lg font-light italic text-black leading-relaxed mb-6">
                                    „Chcę wyjąć Moser z gablot — przywrócić go do codziennego życia. Szklane obiekty powinny być częścią naszego otoczenia, ilustrować atmosferę, a nie stać na półce.”
                                </p>
                                <div class="bg-gray-50 p-4 border-l-2 border-black">
                                    <h5 class="text-[9px] font-bold uppercase text-black tracking-widest mb-1">Czego Krosno powinno się tu nauczyć?</h5>
                                    <p class="text-xs font-light text-gray-700">Moser to ultra-prestiżowa czeska marka, która zeszła ze snobistycznego piedestału, by być "codziennym pięknem". Krosno już jest "codziennym pięknem" (Accessible Premium) - musi jedynie podnieść swój designerski PR i postawić na silnego Dyrektora Artystycznego w mediach wizerunkowych.</p>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
            
        </main>
    </div>

    <script>
        Chart.defaults.font.family = "'Inter', sans-serif";
        Chart.defaults.color = '#86868B'; 
        Chart.defaults.plugins.tooltip.backgroundColor = 'rgba(0, 0, 0, 0.9)';
        Chart.defaults.plugins.tooltip.padding = 16;
        Chart.defaults.plugins.tooltip.cornerRadius = 0; 
        Chart.defaults.plugins.tooltip.titleFont = { size: 13, weight: 'bold', family: "'Inter', sans-serif" };
        Chart.defaults.plugins.tooltip.bodyFont = { size: 12, family: "'Inter', sans-serif" };

        let chartInstances = {};

        function initCharts(tabId) {
            
            if (tabId === 'tab-onepager' && !chartInstances['finance']) {
                const canvas = document.getElementById('chart-finance');
                if(canvas) {
                    const ctx = canvas.getContext('2d');
                    chartInstances['finance'] = new Chart(ctx, {
                        type: 'bar',
                        data: {
                            labels: ['2019', '2021', '2022 (Szczyt Hossa)', '2023', '2024 (Kryzys/Koszty)', '2026 (Cel)'],
                            datasets: [
                                {
                                    label: 'Przychody (mln PLN)',
                                    data: [237.3, 280, 363.0, 312, 266.7, 400],
                                    backgroundColor: '#E5E5EA',
                                    hoverBackgroundColor: '#000000',
                                    order: 2,
                                    borderRadius: 0
                                },
                                {
                                    label: 'EBITDA (mln PLN)',
                                    data: [-13.9, null, 78.9, null, -27.5, null],
                                    type: 'line',
                                    borderColor: '#000000',
                                    backgroundColor: '#000000',
                                    borderWidth: 2,
                                    pointRadius: 5,
                                    pointBackgroundColor: '#fff',
                                    spanGaps: true,
                                    tension: 0.1,
                                    order: 1
                                }
                            ]
                        },
                        options: {
                            responsive: true, maintainAspectRatio: false,
                            scales: { y: { grid: { color: '#F5F5F7' }, beginAtZero: true }, x: { grid: { display: false } } },
                            plugins: { legend: { position: 'top', labels: { usePointStyle: true, boxWidth: 8 } } }
                        }
                    });
                }
            }

            if (tabId === 'tab-comms' && !chartInstances['marketing']) {
                const canvas = document.getElementById('chart-marketing');
                if(canvas) {
                    const ctx = canvas.getContext('2d');
                    chartInstances['marketing'] = new Chart(ctx, {
                        type: 'radar',
                        data: {
                            labels: ['Amazon Ads & E-commerce', 'B2B (HoReCa & Targi)', 'Social Media (Focus Nation)', 'Influencer & PR', 'B2B Co-branding (LOT)', 'Media Tradycyjne (TV/Prasa)'],
                            datasets: [{
                                label: 'Oszacowana Intensywność (Skupienie Budżetu)',
                                data: [10, 8, 8, 6, 7, 1],
                                backgroundColor: 'rgba(0, 0, 0, 0.05)',
                                borderColor: '#000000',
                                pointBackgroundColor: '#000000',
                                borderWidth: 1.5,
                            }]
                        },
                        options: {
                            responsive: true, maintainAspectRatio: false,
                            scales: { r: { angleLines: { color: '#E5E5EA' }, grid: { color: '#F5F5F7' }, ticks: { display: false }, suggestedMin: 0, suggestedMax: 10 } },
                            plugins: { legend: { display: false } }
                        }
                    });
                }
            }

            if (tabId === 'tab-competitors' && !chartInstances['positioning']) {
                const canvas = document.getElementById('chart-positioning');
                if(canvas) {
                    const ctx = canvas.getContext('2d');
                    chartInstances['positioning'] = new Chart(ctx, {
                        type: 'scatter',
                        data: {
                            datasets: [
                                { label: 'Lalique & Lobmeyr (Ultra-Luxury)', data: [{x: 1, y: 9.8}, {x: 1.5, y: 9.3}], backgroundColor: '#E5E5EA', pointRadius: 8 },
                                { label: 'Moser (Prestige Crystal)', data: [{x: 2.5, y: 8.5}], backgroundColor: '#D1D1D6', pointRadius: 10 },
                                { label: 'Riedel & Waterford (Prestige)', data: [{x: 4.0, y: 7.0}, {x: 3.5, y: 7.5}], backgroundColor: '#C7C7CC', pointRadius: 8 },
                                { label: 'Arc Int. & Libbey (Mass/HoReCa)', data: [{x: 9, y: 2.5}, {x: 9.5, y: 2}], backgroundColor: '#E5E5EA', pointRadius: 10 },
                                { label: 'Sisecam (Commodity)', data: [{x: 10, y: 1}], backgroundColor: '#E5E5EA', pointRadius: 12 },
                                { label: 'KROSNO (Accessible Premium - "Złoty Środek")', data: [{x: 6.5, y: 5.5}], backgroundColor: '#000000', pointRadius: 16, pointStyle: 'rect' }
                            ]
                        },
                        options: {
                            responsive: true, maintainAspectRatio: false,
                            scales: {
                                x: { title: { display: true, text: 'Niszowa/Butikowa Dystrybucja ←   |   SKALA, E-COMMERCE & MASOWOŚĆ   |   → Globalny Wolumen Marketowy' }, min: 0, max: 11, ticks: {display: false}, grid: {color: '#F5F5F7'} },
                                y: { title: { display: true, text: 'Niska Cena (Commodity) ←   |   PRESTIŻ / EKSKLUZYWNA CENA (Artisanal)   |   → Ultra Luksus' }, min: 0, max: 11, ticks: {display: false}, grid: {color: '#F5F5F7'} }
                            },
                            plugins: { legend: { position: 'bottom', labels: { usePointStyle: true, boxWidth: 8, font: {size: 11} } } }
                        }
                    });
                }
            }
        }

        // Nawigacja
        function switchTab(tabId, element) {
            document.querySelectorAll('.content-tab').forEach(tab => {
                tab.classList.add('hidden');
                tab.classList.remove('block');
            });
            document.getElementById(tabId).classList.remove('hidden');
            document.getElementById(tabId).classList.add('block');
            
            document.querySelectorAll('.nav-link').forEach(link => link.classList.remove('active'));
            element.classList.add('active');

            setTimeout(() => initCharts(tabId), 50);
        }

        // Interaktywne akordeony storytellingowe
        function toggleStory(element) {
            const container = element.parentElement;
            container.querySelectorAll('.interactive-card.expanded, .timeline-item.expanded').forEach(el => {
                if (el !== element) {
                    el.classList.remove('expanded');
                    const story = el.querySelector('.story-content');
                    if(story) story.classList.remove('expanded');
                }
            });

            element.classList.toggle('expanded');
            const storyContent = element.querySelector('.story-content');
            if(storyContent) {
                storyContent.classList.toggle('expanded');
            }
        }

        window.addEventListener('DOMContentLoaded', () => {
            initCharts('tab-onepager');
        });
    </script>
</body>
</html>
