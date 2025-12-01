# 🌿 Climatic Resilience and Fragility Analysis (CRAF)

[🇮🇹 Versione in italiano qui](#versione-italiana)

This repository contains the analytical workflow, datasets, and processing scripts used to develop the climatic fragility and resilience assessment for the Bologna metropolitan area.  
The work integrates thermal, land-cover, morphological, and socio-environmental indicators to identify areas exposed to heat and to support evidence-based climate adaptation planning.

---

## 🧭 Scope

The analysis combines:
- land surface temperature (LST) data,
- vegetation and land-cover metrics,
- accessibility and structural components,
- socio-environmental indicators,

to produce the **Climatic Fragility Index (CFI)** and related metrics for climate-resilient urban planning.

Methodological reference:

> **Investigating Social Vulnerability to Extreme Heat: Heat Islands and Climate Shelters in Urban Contexts: The Case of Bologna**  
> *ISPRS International Journal of Geo-Information (2024)*  
> 📄 https://tustorage.ulb.tu-darmstadt.de/server/api/core/bitstreams/5655dda2-e4a6-47c5-861a-4aa6102fe31d/content

---

## 📁 Repository Structure

```
craf/
│
├── notebooks/                      # Jupyter notebooks for each analytical step
│   ├── 01_clip_gdal.ipynb 
│   ├── 02_resampling.ipynb  
│   ├── 03_hot_and_cold_spot.ipynb  
│   ├── 04_NDVI_for_CSI.ipynb  
│   ├── 05_bus_stop.ipynb  
│   ├── 06_disabled_parking.ipynb 
│   ├── 07_accessibility.ipynb  
│   └── ...
│
├── data/                        # Input and processed datasets
│   ├── Climatic_fragility/
│   └── ...
│
├── docs/                        # web mapping
├── requirements.txt             # Python dependencies
└── README.md
```

---

## 📊 Data Sources

| Category               | Source                                   | Purpose                                      |
|-----------------------|-------------------------------------------|-----------------------------------------------|
| **Thermal**           | ECOSTRESS LST (NASA JPL)                  | Hot/cold spot detection                       |
| **Land Cover**        | Sentinel-2, Copernicus Urban Atlas        | Vegetation and blue-space extraction          |
| **Topography**        | Copernicus DEM                            | Slope and morphology                          |
| **Socio-Environmental** | ISTAT Census, Climate Shelter Index     | Sensitivity and adaptive capacity             |
| **Administrative**    | Comune di Bologna – Statistical Areas      | Spatial zoning for analysis                   |
| **Meteorological**    | Meteoblue, ERA5 Reanalysis                | LST pattern validation                        |

Large raster and vector files are hosted externally.

---

## 🧮 Processing Workflow

The workflow is executed through a sequence of Jupyter notebooks.  
Each step integrates a thematic dataset, leading to the final climatic fragility output.

### 📘 Processing Chain

```
Clip/Resample → 03_hot_and_cold_spot.ipynb
           ↓
NDVI computation → 04_NDVI_for_CSI.ipynb
           ↓
Accessibility + Structures → 08_identify_structures_for_CSI.ipynb
           ↓
Combine indicators → 09_new_CSI.ipynb
           ↓
Integrate all components → 10_climatic_fragility.ipynb
           ↓
Final index → 11_fragility.ipynb
```


### 📔 Notebook Execution Order

1. 01_clip_gdal.ipynb  
2. 02_resampling.ipynb  
3. 03_hot_and_cold_spot.ipynb  
4. 04_NDVI_for_CSI.ipynb  
5. 05_bus_stop.ipynb  
6. 06_disabled_parking.ipynb  
7. 07_accessibility.ipynb  
8. 08_identify_structures_for_CSI.ipynb  
9. 09_new_CSI.ipynb  
10. 10_climatic_fragility.ipynb  
11. 11_fragility.ipynb  

---

## 📊 Climatic Fragility Index (CFI) – Summary

The index ranges from **0.0 to 1.0**, with higher values indicating higher fragility.

| Range          | Level       | Description |
|----------------|-------------|-------------|
| **0.00–0.25**  | Very Low    | Strong vegetation and cooling capacity |
| **0.26–0.45**  | Low         | Balanced exposure and resilience |
| **0.46–0.60**  | Moderate    | Intermediate fragility |
| **0.61–0.75**  | High        | Heat-exposed areas with limited mitigation |
| **0.76–1.00**  | Very High   | Dense or industrial urban areas |

Observed range in Bologna:

> **0.18 ≤ CFI ≤ 0.81**

Examples:  
- Moderate: *Triumvirato–Pietra*, *Casteldebole*  
- High: *Piazza dell’Unità*, *Villaggio della Barca*  
- Very Low: *Osservanza*, *San Michele in Bosco*


---

## ⚙️ How to Use

1. **Clone the repository**
   ```bash
   git clone https://github.com/TALEA-platform/craf.git
   cd craf
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run notebooks** from the `source/` folder.

4. **Outputs** are saved in:
   ```
   data/Climatic_fragility/outputs/
   ```

---

## 📍 Study Area

**Bologna, Italy** — area for climatic fragility validation.

---

## 🧩 Project Status

**Ongoing (2025)** — continuous updates expected.

---

# 🇮🇹 Versione Italiana {#versione-italiana}

Questo repository contiene il workflow analitico, i dataset e gli script utilizzati per sviluppare l’analisi della fragilità e resilienza climatica per l’area metropolitana di Bologna.  
L’analisi integra indicatori termici, di uso del suolo, morfologici e socio-ambientali per identificare le aree esposte al calore e supportare la pianificazione climatica basata sull’evidenza.

---

## 🧭 Obiettivo

L’analisi combina:
- dati di temperatura superficiale (LST),
- metriche di vegetazione e copertura del suolo,
- componenti strutturali e di accessibilità,
- indicatori socio-ambientali,

per produrre il **Climatic Fragility Index (CFI)** e indicatori correlati.

Riferimento metodologico:

> **Investigating Social Vulnerability to Extreme Heat: Heat Islands and Climate Shelters in Urban Contexts: The Case of Bologna**  
> *ISPRS International Journal of Geo-Information (2024)*

---

## 📁 Struttura del Repository

```
craf/
│
├── notebooks/                      # Jupyter notebooks for each analytical step
│   ├── 01_clip_gdal.ipynb 
│   ├── 02_resampling.ipynb  
│   ├── 03_hot_and_cold_spot.ipynb  
│   ├── 04_NDVI_for_CSI.ipynb  
│   ├── 05_bus_stop.ipynb  
│   ├── 06_disabled_parking.ipynb 
│   ├── 07_accessibility.ipynb  
│   └── ...
│
├── data/                        # Input and processed datasets
│   ├── Climatic_fragility/
│   └── ...
│
├── docs/                        # web mapping
├── requirements.txt             # Python dependencies
└── README.md
```

---

## 📊 Fonti Dati

| Categoria | Fonte | Uso |
|----------|--------|------|
| **Termici** | ECOSTRESS LST (NASA JPL) | Rilevamento hotspot e coldspot |
| **Uso del suolo** | Sentinel-2, Copernicus Urban Atlas | Estrazione aree verdi e blu |
| **Topografia** | Copernicus DEM | Morfologia e pendenza |
| **Socio-ambientali** | ISTAT, Climate Shelter Index | Sensibilità e capacità adattiva |
| **Amministrative** | Aree statistiche Comune di Bologna | Unità di analisi |
| **Meteorologiche** | ERA5 | Validazione dei pattern termici |

File raster e vector molto grandi sono disponibili su altre sorgenti

---

## 🧮 Flusso di lavoro

La pipeline si sviluppa attraverso una sequenza di notebook dedicati a singoli set di dati tematici.<Br/>
Ogni fase integra un set di dati tematici, che porta al risultato finale sulla fragilità climatica.


### 📘 Catena di esecuzione

```
Clip/Resample → 03_hot_and_cold_spot.ipynb
           ↓
NDVI computation → 04_NDVI_for_CSI.ipynb
           ↓
Accessibility + Structures → 08_identify_structures_for_CSI.ipynb
           ↓
Combine indicators → 09_new_CSI.ipynb
           ↓
Integrate all components → 10_climatic_fragility.ipynb
           ↓
Final index → 11_fragility.ipynb
```

### 📔 ordine di esecuzione dei notebook

1. 01_clip_gdal.ipynb  
2. 02_resampling.ipynb  
3. 03_hot_and_cold_spot.ipynb  
4. 04_NDVI_for_CSI.ipynb  
5. 05_bus_stop.ipynb  
6. 06_disabled_parking.ipynb  
7. 07_accessibility.ipynb  
8. 08_identify_structures_for_CSI.ipynb  
9. 09_new_CSI.ipynb  
10. 10_climatic_fragility.ipynb  
11. 11_fragility.ipynb  

---

## 📊 Sintesi CFI

Indice compreso tra **0.0 e 1.0**.  
Valori osservati a Bologna: **0.18 ≤ CFI ≤ 0.81**.

---

Esempi:  
- Moderato: *Triumvirato–Pietra*, *Casteldebole*  
- Alto: *Piazza dell’Unità*, *Villaggio della Barca*  
- Molto Basso: *Osservanza*, *San Michele in Bosco*


---

## ⚙️ Come si usa

1. **Clona il repository**
   ```bash
   git clone https://github.com/TALEA-platform/craf.git
   cd craf
   ```

2. **Installa le dipendenze**
   ```bash
   pip install -r requirements.txt
   ```

3. **Esegui i notebook** dalla cartella `notebooks/`.

4. I **risultati** sono salvati in:
   ```
   data/Climatic_fragility/outputs/
   ```

---

## 📍 Area di Studio

**Bologna, Itala** - area per la convalida della fragilità climatica.


