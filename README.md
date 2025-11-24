# 📚 Similarity Matrix and Language Clustering

## 🧠 Overview

This project explores relationships among **Philippine languages** using computational similarity measures and clustering techniques.
 By analyzing parallel corpora from Bible translations and applying TF-IDF, cosine similarity, and hierarchical clustering (UPGMA), we visualize how languages group according to lexical and orthographic similarity.

Our key questions:

1. Which Philippine languages appear most closely related?
2. How do non-Philippine languages (Spanish and English) fit within the clustering structure?

------

## 🧩 Methodology Summary

### 1. **Data Sources**

- Texts sourced from publicly available **Bible translations** for 16 languages.
- Each corpus normalized and capped at **50,000 tokens** for comparability.
- Languages analyzed:
   Ilocano, Kapampangan, Maguindanao, Ibanag, Tausug, Pangasinan, Kankanaey, Tagalog, Cebuano, Hiligaynon, Bikol, Maranao, Waray, Chavacano, Spanish, and English.

### 2. **Preprocessing**

- Lowercasing, removal of digits and URLs.
- Retained essential characters such as `ñ` and accented vowels.
- Generated **character-level n-grams (n=3)**.

### 3. **Feature Engineering & Similarity Computation**

- Constructed **TF-IDF vectors** per language.
- Computed **cosine similarity**, then converted to **distance = 1 − cosine**.
- Exported similarity and distance matrices as CSV files.

### 4. **Clustering & Visualization**

- Applied **UPGMA hierarchical clustering** to derive a dendrogram.
- Performed **Classical Multidimensional Scaling (MDS)** for 2D visualization.
- Evaluated the dendrogram using the **Cophenetic Correlation Coefficient (r = 0.935)**.
- Generated heatmaps and dendrogram visuals using `matplotlib`.

------

## 🧭 Project Structure

```
📁 Similarity-Matrix-Language-Clustering
│
├── data_clean/
│   ├── aklanon.txt
│   ├── bikol.txt
│   ├── cebuano.txt
│   ├── chavacano.txt
│   ├── english.txt
│   ├── hiligaynon.txt
│   ├── ibanag.txt
│   ├── ilocano.txt
│   ├── kankanaey.txt
│   ├── kapampangan.txt
│   ├── maguindanao.txt
│   ├── maranao.txt
│   ├── pangasinan.txt
│   ├── spanish.txt
│   ├── tagalog.txt
│   ├── tausug.txt
│   └── waray.txt
│
├── data_raw/
│   ├── pdf/
│   │    └── (raw PDF source files)
│   ├── bikol.txt
│   ├── cebuano.txt
│   ├── chavacano.txt
│   ├── english.txt
│   ├── hiligaynon.txt
│   ├── ibanag.txt
│   ├── ilocano.txt
│   ├── kankanaey.txt
│   ├── kapampangan.txt
│   ├── maguindanao.txt
│   ├── maranao.txt
│   ├── pangasinan.txt
│   ├── spanish.txt
│   ├── tagalog.txt
│   ├── tausug.txt
│   └── waray.txt
│
├── notebooks/
│   ├── _archive/
│   ├── 00_setup.ipynb
│   ├── 01_prepare_texts.ipynb
│   ├── 02a_ngrams_tf_similarity.ipynb
│   ├── 02b_cluster_upgma.ipynb
│   ├── 02c_mds_2d.ipynb
│   ├── 02d_eval_cophenetic.ipynb
│   └── 03_report.ipynb
│
├── outputs/
│   ├── cosine_heatmap.png
│   ├── cosine.csv
│   ├── dendrogram.png
│   ├── distance_heatmap.png
│   ├── distance.csv
│   ├── mds_annotated.png
│   ├── mds_annotated.svg
│   ├── mds.csv
│   ├── mds.png
│   └── similarity_distance.pkl
│
└── (README.md, report.pdf, etc.)

```

------

## 🧰 Tools & Environment

| Tool         | Version | Purpose                   |
| ------------ | ------- | ------------------------- |
| Python       | 3.12    | Core environment          |
| pandas       | 2.x     | Data processing           |
| scikit-learn | 1.x     | TF-IDF, cosine similarity |
| matplotlib   | 3.x     | Visualization             |
| numpy        | 1.x     | Numerical computation     |

------

## 🧾 References

- Manning, C.D., Raghavan, P., & Schütze, H. (2008). *Introduction to Information Retrieval.*
- Sokal, R. R., & Michener, C. D. (1958). *A statistical method for evaluating systematic relationships.*
- Borg, I., & Groenen, P. J. F. (2005). *Modern Multidimensional Scaling.*
- McMahon, A., & McMahon, R. (2005). *Language Classification by Numbers.*

