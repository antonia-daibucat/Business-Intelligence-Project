# Business-Intelligence-Project

📊 Analiza economico-financiară a companiilor din industria prelucrării lemnului și fabricării mobilei — Județul Mureș (2021–2024)

Proiect de Business Intelligence realizat în Tableau Prep Builder și Tableau Desktop, având ca scop analiza evoluției economico-financiare a companiilor din sectorul prelucrării lemnului și fabricării mobilei din județul Mureș, în perioada 2021–2024.


📁 Structura proiectului

├── Analiza_companii_final.twbx              # Workbook Tableau Desktop (dashboards + story)
├── Date_financiare_firme_MS_curatate.tflx   # Flow Tableau Prep Builder
├── Documentatie.pdf                          # Documentația completă a proiectului
└── README.md


⚠️ Fișierul .tflx este un flow "linked" (nu conține datele brute incluse), iar .twbx este un packaged workbook. Pentru rulare completă este nevoie de sursele de date originale.

🗂️ Sursele de date

Datele utilizate în acest proiect sunt publice și provin din:


data.gov.ro – platforma de date deschise a Guvernului României, secțiunea situații financiare publicate de Ministerul Finanțelor (bilanțuri anuale 2021–2024: bilanț complet/prescurtat, microîntreprinderi, informații de referință).
ONRC – Oficiul Național al Registrului Comerțului – date privind firmele înregistrate (CUI, denumire, județ, localitate, cod CAEN, formă juridică, stare firmă).


Datele au fost prelucrate exclusiv în scop academic, pentru realizarea acestui proiect universitar.

🎯 Obiectivele proiectului


Integrarea datelor financiare (Ministerul Finanțelor) cu datele ONRC pentru firmele din județul Mureș
Analiza evoluției cifrei de afaceri, profitului net, numărului de salariați și altor indicatori financiari
Clasificarea companiilor după dimensiune, cifră de afaceri și profitabilitate
Identificarea companiilor performante și a tendințelor sectoriale
Realizarea unor dashboard-uri interactive în Tableau Desktop


🏭 Codurile CAEN analizate

Cod CAENActivitateSegment1610Tăierea și rindeluirea lemnuluiProducție primară1623Fabricarea altor elemente de dulgherie și tâmplărie pentru construcțiiProducție secundară1629Fabricarea altor produse din lemn; plută, paie și materiale vegetale împletiteProducție secundară3109Fabricarea de mobilă n.c.a.Producție finală4673Comerț cu ridicata al materialului lemnos și al materialelor de construcțieDistribuție

🔧 Pregătirea datelor (Tableau Prep)

Flow-ul de curățare și integrare a datelor (Date_financiare_firme_MS_curatate.tflx) parcurge următoarele etape:


Încărcare surse – fișierele Ministerului Finanțelor (web_bl_bs_sl, web_UU, web_IR) pentru anii 2021–2024 + fișierele ONRC
Cleaning per fișier – redenumire câmpuri, corectare tipuri de date, eliminare valori NULL
Union per an – reunirea celor 3 tipuri de bilanț pentru fiecare an
Union global – reunirea tuturor anilor într-un singur set ("date financiare")
Filtrare ONRC – firme active din județul Mureș
Join CAEN – selecția codurilor CAEN relevante
Join final – integrarea datelor financiare cu lista firmelor din sector (pe CUI)
Câmpuri calculate – Clasificare CA, Clasificare Profitabilitate, Clasificare dimensiune firmă
Export – fișier .hyper pentru Tableau Desktop


📈 Vizualizări și Dashboard-uri (Tableau Desktop)

Proiectul conține 14 foi de lucru, 2 dashboard-uri interactive și o secțiune Story cu 6 story points.

Dashboard 1 – Analiză companii Mureș


KPI-uri: Cifra de afaceri totală, Profit net total, Nr. salariați, Nr. total firme
Hartă interactivă a județului Mureș
Evoluția profitului net pe CAEN (Line Chart)
TreeMap CAEN
Filtre globale (CAEN, Localitate)


Dashboard 2 – Top N companii


Clasament dinamic (parametri: Indicator + Top N)
CA vs Profit (Scatter Plot)
HeatMap CAEN pe an
Titluri dinamice


🧮 Câmpuri calculate principale


Profit Margin = SUM(Profit net) / SUM(Cifra de afaceri netă)
Rata îndatorării = SUM(Datorii) / (Active imobilizate + Active circulante)
Growth Rate (YoY)
Clasificare performanță, Clasificare CA, Clasificare Profitabilitate, Clasificare dimensiune firmă


🧩 Concluzii principale


Codul CAEN 4673 (comerț cu ridicata material lemnos) domină autoritar cifra de afaceri și profitul sectorului în toți cei 4 ani analizați
Sectorul 3109 (fabricare mobilă) a scăzut aproape la zero până în 2024
Profitul este concentrat în doar câteva companii (lider: BLUEFOREST DEVELOPMENT)
Activitatea economică e concentrată geografic în Târnăveni, Sovata și Solovăstru


🖥️ Cum se rulează proiectul


Descarcă/clonează acest repository
Instalează Tableau Desktop (sau Tableau Reader pentru vizualizare read-only) și Tableau Prep Builder
Deschide Analiza_companii_final.twbx în Tableau Desktop pentru dashboard-uri și story
Deschide Date_financiare_firme_MS_curatate.tflx în Tableau Prep Builder pentru flow-ul de curățare a datelor

Notă: flow-ul face referire la fișierele sursă originale (data.gov.ro / ONRC); pentru rulare completă, sursele trebuie redescărcate separat


📄 Documentație completă

Documentația detaliată a proiectului (metodologie, capturi de ecran, interpretări economice) se află în Documentatie.pdf.

📜 Licență / Uz

Proiect realizat exclusiv în scop academic (Business Intelligence, 2025–2026). Datele sunt publice, provenind de pe data.gov.ro (Ministerul Finanțelor) și ONRC.
