# 🧠 Human-Relatedness Embedding

Understanding how human cognition relates to distributed word representations — exploring how **similarity**, **association**, and **relatedness** emerge in high-dimensional embedding spaces.

---

## 📘 Core Concepts

| Concept | Meaning |
|:--------|:---------|
| **Similarity** | How much two concepts share in meaning or category (e.g., *dog* and *wolf*). |
| **Association** | How frequently or contextually two concepts occur together (e.g., *dog* and *bone*). |
| **Relatedness** | The actual cognitive state representing how the brain internally connects two concepts — integrating both similarity and association. |

---

## ⚙️ Methodology

- Used **pre-trained GloVe embeddings** (50D, 100D, 200D, 300D).  
- Computed **cosine similarity** between word pairs.  
- Compared model predictions with **human judgments** from:
  - **SimLex-999** (similarity-focused dataset)
  - **MEN** (relatedness-focused dataset)
- Calculated **Pearson correlation** and **R² (linear regression)** to evaluate model–human alignment.

---

## 📊 Results

### **1. SimLex-999 Dataset**

| Embedding Dimension | Correlation (Similarity) | Correlation (Association) | R² Score |
|:--------------------:|:------------------------:|:--------------------------:|:---------:|
| 50D | 0.29 | 0.26 | 0.0517 |
| 100D | 0.33 | 0.28 | 0.0775 |
| 200D | 0.36 | 0.30 | 0.1010 |
| 300D | 0.39 | 0.32 | 0.1249 |

**Interpretation (SimLex-999):**
- Correlation gradually increases with dimensionality but remains modest.
- Even at 300D, R² ≈ 0.125 → embeddings capture limited alignment with human similarity.
- Association correlations are slightly lower → volunteer bias and constrained judgments likely affect data quality.

---

### **2. MEN Dataset**

| Embedding Dimension | Correlation (Cosine vs Human) | R² Score |
|:--------------------:|:-----------------------------:|:---------:|
| 50D | 0.67 | 0.4459 |
| 100D | 0.70 | 0.4941 |
| 200D | 0.72 | 0.5221 |
| 300D | 0.74 | 0.5537 |

**Interpretation (MEN):**
- Significantly stronger alignment with human ratings.  
- Correlation and R² improve steadily as dimension increases.  
- At 300D, correlation = 0.74, R² = 0.55 → ~55% of human-relatedness variance is predictable via cosine similarity.  
- Suggests MEN better captures **true cognitive relatedness** — emphasizing contextual and associative semantics.

---

### **3. Core Comparative Insights**

| Dataset | Human Judgment Type | Best Correlation (300D) | Best R² (300D) | Interpretation |
|:---------|:--------------------|:-----------------------:|:----------------:|:----------------|
| **SimLex-999** | Pure similarity + association (biased) | 0.39 | 0.125 | Weak alignment — constrained, linguistic focus |
| **MEN** | Free association / relatedness | 0.74 | 0.554 | Strong alignment — reflects human cognitive relatedness |

---

## 🧩 Summary of Observations

1. **Human Relatedness = f(Similarity, Association)**  
   - MEN’s higher alignment supports the idea that relatedness arises from both similarity and association.  
   - Purely similarity-based data (SimLex) fails to capture the full cognitive structure of meaning.

2. **Cognitive Geometry is Higher-Dimensional**  
   - Correlation and R² increase consistently with embedding dimensionality.  
   - Suggests that the human mind represents concepts in a **high-dimensional semantic space (>300D)**.  
   - Each added dimension captures subtle cues — emotional, contextual, or functional — enriching human-like understanding.

3. **SimLex-999 is Limited**  
   - Despite increasing dimensions, SimLex remains poorly aligned.  
   - Indicates that constrained human ratings fail to represent the full complexity of cognitive relationships.

---

## 🧠 Conclusions

1. **Relatedness = f(Similarity, Association)**  
   Human understanding of meaning emerges from the fusion of categorical similarity and contextual association.  
   Datasets that capture both (like MEN) are closer to cognitive reality.

2. **Human Cognitive Space is High-Dimensional (>300D)**  
   The steady improvement with dimensionality suggests that human conceptual organization operates in a vast semantic space.  
   Meaning is distributed, continuous, and deeply multidimensional.

---

## 🧪 Tools & Libraries
- Python (NumPy, Pandas, Scikit-learn)
- Matplotlib, Seaborn
- Gensim (for GloVe embeddings)
- Jupyter Notebook

---

## 📈 How to Run

```bash
git clone https://github.com/vivek-bhave/Human-Relatedness-embedding.git
cd Human-Relatedness-embedding
jupyter notebook

🧭 Future Work

Extend to BERT embeddings for contextual understanding.

Compare with human association networks (e.g., WordNet).

Explore cross-linguistic or domain-specific embeddings.

🧑‍💻 Author

Vivek Chandrakant Bhave
MS (AI & DS), ABV-IIITM Gwalior
Exploring connections between human cognition and artificial representation learning.

🕊️ License

MIT License © 2025 Vivek Bhave