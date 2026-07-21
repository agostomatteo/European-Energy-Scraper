### European Energy Mix & CO2 Tracker: A Web Scraping ETL Pipeline

Descrizione

Progetto di raccolta e analisi del mix energetico europeo tramite web scraping del sito Nowtricity. Il dataset copre 26 paesi europei dal 2018 al 2025 (2.220 osservazioni) e include emissioni di CO₂, percentuale di rinnovabili e composizione dettagliata per fonte energetica.

# Struttura del progetto

european-energy-scraper/

 ├── data/

 │   ├── raw/          # JSON grezzi per paese (output dello scraper)

 │   └── processed/    # Dataset puliti per paese e master dataset

 ├── notebooks/

 │   ├── 0.Exploration.ipynb    # Ispezione del sito e sviluppo dello scraper

 │   ├── scrape_total.ipynb     # Scraping completo dei 26 paesi

 │   └── Data_Cleaning.ipynb    # Pulizia, validazione e costruzione dataset

 └── outputs/

     ├── Analisi.ipynb          # Analisi complete e visualizzazioni

     ├── Analisi.pdf            # Versione PDF del notebook finale

     └── figures/               # Grafici esportati

 

# Come riprodurre i risultati

1. Installa le dipendenze

pip install -r requirements.txt

 
2. Esegui i notebook in ordine

0.Exploration.ipynb    → ispezione del sito

 scrape_total.ipynb     → raccolta dati (richiede ~150 minuti)

 Data_Cleaning.ipynb    → pulizia e validazione

 Analisi.ipynb          → analisi e visualizzazioni

 
Il dataset processato è già incluso in * data/processed/ * —

 *

 puoi eseguire direttamente * Analisi.ipynb * senza riscrapare.*

Dataset
·	Fonte: Nowtricity (dati ENTSO-E)
·	Copertura: 26 paesi europei, gennaio 2018 — dicembre 2025
·	Righe: 2.220 osservazioni
·	Colonne principali: country_name, month_id, co2_g_kwh,

 renewable_perc, total_twh, fonti per percentuale
Analisi prodotte
1.	Trend storico CO₂ per le 5 principali potenze europee (2018–2025)
2.	Ranking europeo per emissioni medie e quota rinnovabile
3.	Correlazione tra rinnovabili ed emissioni (Pearson r = -0.570)
4.	Heatmap intensità carbonica europea (2025)
5.	Analisi statistica Slovenia — matrice di correlazione per anno
6.	Verifica empirica outage nucleare Krško (ottobre 2019)
7.	Grafo di similarità energetica NetworkX (2025)
8.	Evoluzione dei cluster energetici europei (2018→2021→2025)
Tecnologie utilizzate
·	Scraping: Selenium, BeautifulSoup
·	Analisi: pandas, numpy
·	Visualizzazione: matplotlib, seaborn
·	Grafi: NetworkX
