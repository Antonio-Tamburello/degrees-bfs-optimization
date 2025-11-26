# Six Degrees of Separation: Optimizing BFS in CS50AI “Degrees” Problem

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![CS50AI](https://img.shields.io/badge/CS50-AI-red.svg)](https://cs50.harvard.edu/ai/)
[![Kaggle](https://img.shields.io/badge/Run%20on-Kaggle-blue?logo=kaggle)](https://www.kaggle.com/code/antoniotamburello/six-degrees-of-separation-optimizing-bfs-cs50ai)

**Language:**  
🇬🇧 [English Version](#english-version) | 🇮🇹 [Versione Italiana](#versione-italiana)

---

<a id="english-version"></a>

# 🇬🇧 English Version

## Project Overview

During **Harvard’s CS50 Introduction to AI with Python**, I implemented a BFS solution to the classic **[Six Degrees of Separation](https://en.wikipedia.org/wiki/Six_degrees_of_separation)** problem. While analyzing the runtime behavior, I identified an inefficiency: **the target node was always added to the frontier before being processed**, causing an unnecessary extra iteration. This led me to implement a simple but impactful optimization.

The optimization introduces an **early exit check** that detects the target before adding it to the frontier, reducing the number of explored nodes and improving execution time while fully preserving BFS correctness and shortest-path guarantees.

This repository includes:

- A clear comparison between the standard BFS and the optimized BFS
- Optional DFS implementation for completeness
- A Jupyter notebook with benchmarks, analysis, and visualizations
- A clean, production-quality codebase reflecting professional engineering practices

---

## Key Results

| Metric              | BFS Standard | BFS Optimized |
| ------------------- | ------------ | ------------- |
| Avg. Execution Time | 4582.94ms    | 7.52ms        |
| Nodes Explored      | 631          | 11            |
| Path Length         | Identical    | Identical     |

**Performance Improvement:** ~99.8%

---

## The Optimization

The early-exit optimization checks whether a neighboring node is the target _before_ adding it to the frontier:

```python
if person_id == target:
    return construct_path(child)

frontier.add(child)
```

This small modification eliminates an extra cycle of the main BFS loop and avoids redundant operations, especially impactful in dense graphs.

---

## Repository Structure

```
degrees/
├── degrees_comparison.ipynb      # Full benchmark and analysis notebook
├── degrees.py                    # Standard BFS implementation
├── degrees_optimized.py          # Optimized BFS
├── util.py                       # Core data structures
├── large/                        # IMDb dataset
│   ├── people.csv
│   ├── movies.csv
│   └── stars.csv
└── requirements.txt
```

---

## Run Locally

```bash
git clone https://github.com/yourusername/degrees.git
cd degrees

pip install -r requirements.txt
jupyter notebook degrees_comparison.ipynb
```

---

## Open in Kaggle

Open the notebook directly in your browser:

👉 **[Open the Notebook on Kaggle](https://www.kaggle.com/code/antoniotamburello/six-degrees-of-separation-optimizing-bfs-cs50ai)**

---

<a id="versione-italiana"></a>

# 🇮🇹 Versione Italiana

## Panoramica del Progetto

Durante il corso **CS50 Introduction to AI with Python** di Harvard, ho implementato una soluzione BFS al classico problema dei **[Six Degrees of Separation](https://en.wikipedia.org/wiki/Six_degrees_of_separation)**. Analizzando il comportamento in esecuzione, ho identificato un'inefficienza: **il nodo target veniva sempre aggiunto alla frontier prima di essere processato**, causando un'iterazione extra non necessaria. Questo mi ha portato a implementare un'ottimizzazione semplice ma di impatto.

L'ottimizzazione introduce un **early exit check** che rileva il target prima di aggiungerlo al frontier, riducendo il numero di nodi esplorati e migliorando il tempo di esecuzione pur preservando completamente la correttezza della BFS e le garanzie del percorso più breve.

Questa repository include:

- Un confronto tra la BFS standard e la BFS ottimizzata
- Implementazione DFS opzionale per completezza
- Un notebook Jupyter con benchmark, analisi e visualizzazioni
- Una codebase pulita e di qualità professionale che riflette pratiche ingegneristiche professionali

---

## Risultati Chiave

| Metrica            | BFS Standard | BFS Ottimizzato |
| ------------------ | ------------ | --------------- |
| Tempo Medio Esec.  | 4582.94ms    | 7.52ms          |
| Nodi Esplorati     | 631          | 11              |
| Lunghezza Percorso | Identica     | Identica        |

**Miglioramento delle Prestazioni:** ~99.8%

---

## L'Ottimizzazione

L'ottimizzazione **early exit check** verifica se un nodo vicino è il target _prima_ di aggiungerlo al frontier:

```python
if person_id == target:
    return construct_path(child)

frontier.add(child)
```

Questa piccola modifica elimina un ciclo extra del loop principale BFS ed evita operazioni ridondanti, con un impatto particolare nei grafi densi.

---

## Struttura della Repository

```
degrees/
├── degrees_comparison.ipynb      # Notebook completo di benchmark e analisi
├── degrees.py                    # Implementazione BFS standard
├── degrees_optimized.py          # BFS Ottimizzata
├── util.py                       # Strutture dati fondamentali
├── large/                        # Dataset IMDb
│   ├── people.csv
│   ├── movies.csv
│   └── stars.csv
└── requirements.txt
```

---

## Esecuzione Locale

```bash
git clone https://github.com/yourusername/degrees.git
cd degrees

pip install -r requirements.txt
jupyter notebook degrees_comparison.ipynb
```

---

## Apri su Kaggle

Apri il notebook direttamente nel tuo browser:

👉 **[Apri il Notebook su Kaggle](https://www.kaggle.com/code/antoniotamburello/six-degrees-of-separation-optimizing-bfs-cs50ai)**

---

## Author

**Antonio Tamburello** — Senior Lead Frontend Engineer
LinkedIn: https://www.linkedin.com/in/antonio-tamburello/
