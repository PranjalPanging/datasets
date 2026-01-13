# Mising Language Resources (Tani)

This directory serves as the definitive computational hub for the **Mising language** (*ISO 639-3: mrg*). Mising is a major linguistic constituent of the **Tani branch** within the Trans-Himalayan (Sino-Tibetan) language family, spoken predominantly across the Brahmaputra Valley of Assam and the jurisdictional foothills of Arunachal Pradesh, India.

Despite its robust speaker population, Mising remains digitally under-resourced. This repository provides the structural groundwork for **Natural Language Processing (NLP)**, **Neural Machine Translation (NMT)**, and **Computational Morphological Analysis**.

---

## 📌 Linguistic Rigor: The MAK Standard

To eliminate phonetic ambiguity in Machine Learning training, all datasets in this directory strictly adhere to the **MAK (Mising Agom Kébang)** standardized orthography. This ensures that the data is not merely "text," but a precise phonological representation of the language.

### 1. Central Vowel Precision (/ɨ/ and /ə/)
The most critical technical feature of this repository is the high-fidelity representation of Mising's central vowels. In non-standard or "casual" datasets, these are often merged into standard front vowels, leading to catastrophic loss of semantic data during model training.

* **The Barred-i (`í`):** This character represents the **high central unrounded vowel** (/ɨ/). Within the International Phonetic Alphabet (IPA), this is identified as the "i with a bar/cross." It is a distinctive phonological marker of the Tani group and is phonemically distinct from the high front vowel `/i/`.
* **The Accented-E (`é`):** This represents the **close-mid central unrounded vowel** (/ə/ or /ɘ/). The `é` diacritic is utilized specifically to distinguish this phoneme from the standard mid-front English `/e/`.



### 2. Phonemic Vowel Elongation (:)
In Mising, vowel length is a **primary semantic carrier**. The duration of a vowel dictates the fundamental meaning of a word. The absence of the elongation marker renders strings linguistically incorrect or changes the definition entirely.

**Key Example of Semantic Shift:**
* **mé:nam** (with elongation): Means "to love" or "to think."
* **ménam** (without elongation): Means "to leave it".

---

## 🗂 Key Resource: MEND (100k)

### [Mising-English Numerical Dataset (MEND)](./numbers/)
MEND is an expansive parallel corpus designed for digit-to-text normalization and morphological stacking analysis.

* **Volume:** 100,000 parallel entries ($Arabic Numeral \rightarrow Mising Text \rightarrow English Text$).
* **Recursive Morphological Stacking:** This dataset captures the recursive nature of Tani numeration. High-order values are constructed through systematic root stacking (e.g., `lí:lí:` for $10^4$ and `yí:lí:lí:` for $10^5$), preserving the indigenous mathematical logic of the Mising oral tradition.
* **Multimodal Formats:** * **`.jsonl`**: Structured for Large Language Model (LLM) fine-tuning.
    * **`.csv`**: Optimized for tabular data processing and statistical analysis.
    * **`.pdf`**: Provided for human-readable linguistic verification and archival.

---

## ⚖️ Licensing & Data Portability

All resources within this language hub are released under the **MIT License**. 

> **Architectural Note:** A redundant `LICENSE` file is maintained within this subdirectory. This ensures that if the `/mising/` directory is isolated or cloned independently of the parent repository, the legal permissions, non-liability clauses, and curator attribution remain permanently coupled with the data.

**Curator:** Pranjal Panging  
**Linguistic Standard:** Mising Agom Kébang (Official)  
**Release Year:** 2026