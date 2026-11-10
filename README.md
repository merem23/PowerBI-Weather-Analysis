# Ecology & Weather Analytics — România (2025)

## Despre Proiect
Acest proiect Power BI realizează o analiză vizuală și statistică detaliată a **fenomenelor meteorologice și a indicatorilor de mediu (calitatea aerului) în principalele orașe din România pentru anul 2025**. Proiectul a fost dezvoltat ca studiu de caz practic, având ca scop centralizarea metricilor climatice și transformarea datelor brute în insight-uri ușor de urmărit pentru managementul de mediu.

---

Raportul este structurat pe două pagini analitice:

### 1. Pagina: Overview (Prezentare Generală)
Se concentrează pe distribuția lunară a temperaturilor și maparea cantităților de precipitații și poluare pe orașe.
*   **Average temperature by month:** Grafic de tip *Column Chart* care evidențiază evoluția temperaturilor de la valorile negative din iarnă (Ianuarie/Februarie) până la vârful sezonului cald în Iulie și August.
*   **Rainfall (mm) by city:** Matrice de indicatori vizuali pentru monitorizarea precipitațiilor totale acumulate în orașe cheie (ex: Cluj: 1,249.80 mm, Brașov: 1,227.70 mm, Iași: 1,044.80 mm, Constanța: 625.90 mm).
*   **AQI & PM25 by city:** Analiză comparativă directă între Indicele de Calitate a Aerului (AQI) și densitatea particulelor PM2.5 (evidențiată în grafic pentru orașe precum Craiova).

### 2. Pagina: Trends & Extremes (Tendințe și Extreme)
O pagină dedicată valorilor critice înregistrate la nivel național și corelațiilor geografice.
*   **Panou KPI pentru Valori Extreme:** Carduri vizuale care scot în evidență extremele climatice din 2025:
    *   *Valori Maxime:* Viteză vânt (**37.50 km/h**), Temperatură (**37.70 °C**), Precipitații (**18.70 mm**), Umiditate (**98.00%**).
    *   *Valori Minime:* Viteză vânt (**1.00 km/h**), Temperatură (**-16.90 °C**), Precipitații (**0.00 mm**), Umiditate (**28.70%**).
*   **Hartă Geografică Interactivă:** Maparea emisiilor maxime de CO2 și a particulelor PM2.5 direct pe harta României pentru identificarea rapidă a hotspot-urilor de poluare.
*   **Max Windspeed by City:** Un *Donut Chart* procentual care distribuie cota vitezei maxime a vântului pe orașe, evidențiind Constanța (16.35%) și Timișoara ca zone cu intensificări majore.

---

## Detalii Tehnice & Arhitectură

### 1. Modelarea Datelor (Data Modeling)
Pentru a asigura un timp de răspuns optim al vizualizărilor și o filtrare corectă cross-report, am implementat o arhitectură de tip **Star Schema**:
*   **Tabel de Fapte (Fact Table):** Stochează măsurătorile zilnice și valorile brute (Temperatură, Vânt, Umiditate, Precipitații, AQI, PM2.5, CO2).
*   **Tabele de Dimensiuni (Dimension Tables):** 
    *   `Dim_Locatie` (Orașele din România analizate: București, Cluj, Brașov, Constanța, Craiova, Timișoara, Iași, Pitești).
    *   `Dim_Calendar` (Axa de timp folosită pentru agregarea corectă a lunilor).

### 2. ETL & Curățarea Datelor (Power Query)
*   Datele provin dintr-o sursă Open-Source și au fost procesate pentru a elimina erorile de înregistrare.
*   Au fost setate tipurile corecte de date (tipul *Geografic* pentru localizarea corectă pe hartă și tipuri *Numerice* pentru agregatele statistice).

---

## Insight-uri Extrase din Date
1.  **Zonele cu Risc de Inundații / Precipitații Mari:** Regiunile montane și de deal (Cluj și Brașov) au înregistrat cele mai mari cantități de precipitații în 2025 (peste 1200 mm), în timp ce zona de coastă (Constanța) a rămas cea mai aridă (625.90 mm).
2.  **Potențial de Energie Eoliană / Alerte de Vânt:** Constanța domină topul vitezei vântului, sugerând un potențial eolian ridicat, dar și o expunere mai mare la furtuni.
3.  **Corelația Poluării Urbane:** Harta indică o concentrare a indicilor PM2.5 și CO2 în marile aglomerări urbane, oferind o bază de date excelentă pentru măsuri de smart-city sau politici de mediu.

---

## Cum se poate rula proiectul local
1. Clonează acest repository: `git clone https://github.com`
2. Deschide fișierul `.pbix` folosind **Power BI Desktop**.

---
**Contact:** Mara Eremia – [LinkedIn](https://www.linkedin.com/in/mara-e-79666ab5/)
