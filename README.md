# Klasifikimi dhe Grupimi i Kurseve Online (Udemy) — Projekt Machine Learning

Parashikimi i lëndës (*subject*) së një kursi Udemy nga atributet e tij, dhe grupimi i kurseve pa etiketa.
Dataseti: [Udemy Online Education Courses (Kaggle)](https://www.kaggle.com/datasets/yusufdelikkaya/udemy-online-education-courses) — 3,683 kurse, 4 klasa.

## Struktura

```
├── notebook.ipynb        ← I gjithë kodi (i ekzekutuar, me rezultate të dukshme)
├── data/udemy_courses.csv
├── figures/              ← Figurat e gjeneruara nga notebook-u
├── results/              ← Tabelat e rezultateve (CSV + JSON)
├── Raporti_ML.docx       ← Raporti i plotë (Hyrje … Referencat)
├── requirements.txt
└── README.md
```

## Si të ekzekutohet

```bash
# 1. Krijoni mjedisin
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt

# 2. Hapni notebook-un
jupyter notebook notebook.ipynb

# 3. Run All — ekzekutimi i plotë zgjat ~3–5 minuta
```

Notebook-u i ruan automatikisht figurat në `figures/` dhe tabelat në `results/`.

## Çfarë përmban

- **4 klasifikues** nga familje të ndryshme: KNN (distancë), Random Forest (pemë), Logistic Regression (linear), MLP (rrjetë neurale me 2 arkitektura: `(64,)` dhe `(128,64)`)
- **GridSearchCV** (3-fold) për çdo klasifikues — vlerat e testuara dhe të zgjedhura dokumentohen
- **3 bashkësi veçorish**: numerike, SelectKBest top-4, numerike + TF-IDF(titull)→SVD(50)
- **Metrika**: saktësia, precizioni, recall, F1-macro + matricat e konfuzionit
- **Grupimi**: K-Means (elbow + siluetë, k-means++ vs random) + Agglomerative; ARI/NMI kundrejt klasave reale; vizualizim PCA
- **Rezultati kryesor**: 92.9% saktësi (Logistic Regression); grupimi natyror ndjek popullaritetin, jo lëndën

## Rezultatet kryesore

| Klasifikuesi | Saktësia | F1-macro |
|---|---|---|
| Logistic Regression | **0.929** | **0.921** |
| Random Forest | 0.922 | 0.913 |
| MLP (128,64) | 0.914 | 0.902 |
| KNN | 0.608 | 0.594 |

## Shënim për dorëzimin në GitHub

Repositori duhet të jetë publik dhe të dy anëtarët duhet të kenë commite individuale.
Sugjerohet ndarja: anëtari 1 — parapërpunimi + klasifikimi; anëtari 2 — feature engineering + grupimi + raporti,
me commite të vazhdueshme gjatë punës (jo një commit i vetëm në fund).
 
