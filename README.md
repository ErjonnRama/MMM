# Klasifikimi dhe Grupimi i Kurseve Online (Udemy)

Ky projekt analizon kurse online nga platforma Udemy duke përdorur teknika të machine learning. Qëllimi kryesor është të parashikojmë lëndën e një kursi bazuar në atributet e tij si çmimi, numri i studentëve, gjatësia dhe titulli. Gjithashtu eksplorojmë se si grupohen natyrshëm kurset kur nuk përdorim etiketa.

Dataseti përmban 3,683 kurse reale nga Udemy me 4 kategori: Web Development, Business Finance, Musical Instruments dhe Graphic Design.

## Struktura e projektit

```
├── notebook.ipynb        ← Kodi i plotë me rezultate
├── data/udemy_courses.csv
├── figures/              ← Grafikët e gjeneruar
├── results/              ← Rezultatet e ruajtura (CSV)
├── Raporti_ML.docx       ← Raporti i shkruar
├── requirements.txt
└── README.md
```

## Si të ekzekutohet

```bash
python -m venv venv

# Mac/Linux:
source venv/bin/activate
# Windows:
venv\Scripts\activate

pip install -r requirements.txt
jupyter notebook notebook.ipynb
```

Kur hapet browser-i, kliko **Run All**. Ekzekutimi zgjat rreth 3-5 minuta.

## Çfarë bën kodi

Fillimisht ngarkon dhe pastron datasetin, pastaj trajnon katër klasifikues të ndryshëm: KNN, Random Forest, Logistic Regression dhe një rrjetë neurale (MLP). Për secilin klasifikues testohen kombinime të ndryshme hiperparametrash dhe zgjidhet kombinimi më i mirë. Krahasohen gjithashtu tre bashkësi veçorish të ndryshme për të parë si ndikojnë në performancë. Në fund kryhet grupimi i kurseve pa përdorur etiketat dhe rezultatet vizualizohen.

## Rezultatet

| Klasifikuesi | Saktësia | F1-macro |
|---|---|---|
| Logistic Regression | **0.929** | **0.921** |
| Random Forest | 0.922 | 0.913 |
| MLP (128,64) | 0.914 | 0.902 |
| KNN | 0.608 | 0.594 |

