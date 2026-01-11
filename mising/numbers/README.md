# Mising-English Numerical Dataset (MEND)

[![Dataset](https://img.shields.io/badge/Dataset-JSONL--CSV-orange)](#) 
[![Scale](https://img.shields.io/badge/Scale-100k_Entries-blue)](#)
[![Language](https://img.shields.io/badge/Language-Mising--English-green)](#)

**MEND** is a high-fidelity parallel corpus providing a systematic mapping of integers to their verbal forms in both English and Mising. This 100,000-entry dataset is designed to support **Computational Linguistics** research and the development of **NLP tools** (such as NMT and ITN) for the Mising language, adhering to the **MAK (Mising Agom Kébang)** standardized orthography.

---

## 📝 Project Description
The Mising-English Numerical Dataset (MEND) serves as a foundational resource for the digit-to-text normalization of the Mising language. By mapping Arabic numerals (1–100,000) to both English and Mising text, it provides a clean, algorithmic dataset for training machine learning models to understand the recursive morphology of Tani languages.

## 📊 Dataset Specifications
- **Format:** `.jsonl` (JSON Lines) for primary data; `.csv` for general use.
- **Scale:** 100,000 unique parallel records (1 to 100,000).

### Data Schema
Each entry in the `.jsonl` file follows the standard translation format, making it compatible with Hugging Face and PyTorch data loaders:
```json
{
  "id": 1050,
  "translation": {
    "en": "one thousand and fifty",
    "mi": "yí:língko yí:ngo"
  }
}
```

## 📥 Quick Downloads
Access the dataset and documentation directly from this repository:

| File | Description | Format |
| :--- | :--- | :--- |
| [**MEND_100k.jsonl**](./MEND_100k.jsonl?download=true) | Primary training data for NLP/NMT models. | `JSONL` |
| [**MEND_100k.csv**](./MEND_100k.csv?download=true) | Spreadsheet version for general analysis. | `CSV` |
| [**MEND_100k.pdf**](./MEND_100k.pdf?download=true) | Human-readable dictionary (1–100,000). | `PDF` |

## 🧠 Linguistic Patterns & Morphological Logic

The Mising numerical system is a **multiplicative-decimal** system. The dataset is generated using a recursive logic that breaks numbers into their constituent powers of ten, applying specific roots and suffixes according to the MAK (Mising Agom Kébang) standard.

### 1. Base Units (0–9)
The fundamental building blocks used as standalone values or as multipliers for higher denominations:

| Digit | Standalone (Units) | Root (Multipliers) |
| :--- | :--- | :--- |
| 0 | `abín` |   |
| 1 | `ako` | `ko` |
| 2 | `annyi` | `nyi` |
| 3 | `aum` | `um` |
| 4 | `appi:` | `pi:` |
| 5 | `angngo` | `ngo` |
| 6 | `akkéng` | `kéng` |
| 7 | `kíníd` | `níd` |
| 8 | `pi:nyi` | `pi:nyi` |
| 9 | `konang` | `nang` |

### 2. Positional Multipliers (Powers of Ten)
The system scales using specific prefixes and recursive roots. For base denominations (100, 1,000, 10,000), an explicit "one" multiplier (**ko**) is used to maintain mathematical clarity.

| Power | Denomination | Mising Logic | Example |
| :--- | :--- | :--- | :--- |
| **10¹** | Tens | `yí:` | 30 = `yí:um` |
| **10²** | Hundreds | `lí:` | 400 = `lí:pi:` |
| **10³** | Thousands | `yí:lí:` | 5,000 = `yí:lí:ngo` |
| **10⁴** | Ten-Thousands | `lí:lí:` | 10,000 = `lí:lí:ko` |
| **10⁵** | Lakh | `yí:lí:lí:` | 100,000 = `yí:lí:língko` |



### 3. Compounding & Connectives
To join different place values, the logic uses specific "bridge" suffixes to indicate the remainder:

- **The "Teen" Rule (11–19):** Uses the prefix `yí:` followed by a unit-specific suffix (e.g., 12 is `yí:la:nyí`).
- **Standard Compounds (21–99):** Follows the structure `yí:[root]` (the ten) + `la:[unit]` (the remainder). Example: 22 is `yí:nyí la:nyí`.

### 4. Morphological Orthography & Phonology
This dataset strictly follows the **MAK Standard** to ensure high-quality training data for NLP:

- **Central Vowels (`í` & `é`):** - **`í`**: Represents the high central unrounded vowel (/ɨ/). Phonetically, this is the "barred-i" or "i with a cross" in the IPA.
  - **`é`**: Represents the close-mid central unrounded vowel (/ə/). This specific character is used instead of a standard English 'e' to denote its unique central quality in Mising.
  - These central vowels are distinctive markers of the Mising language. Precise representation in this dataset prevents "vowel merging" errors in Machine Learning models.
- **Vowel Length (`:`):** The colon is used as a diacritic to indicate **vowel elongation** (e.g., `lí:` vs `li`). In numerical terms, length is a semantic carrier; removing the elongation mark changes the mathematical value or renders the word incorrect.
- **Recursive Stacking:** Higher powers are formed by stacking roots (e.g., `lí:lí:` for 10,000).

## ⚖️ License & Attribution

### License
This dataset is licensed under the **MIT License**. 

**Why this license?** The MIT License is highly permissive, allowing for both academic and commercial use. It encourages the integration of Mising linguistic data into global NLP frameworks while ensuring the author is protected from liability.

### Attribution
If you utilize the **MEND** dataset for research, machine learning models, or linguistic applications, please cite the work as follows:

**Project:** Mising-English Numerical Dataset (MEND)  
**Curator:** Pranjal Panging  
**Year:** 2026  

### Citation (BibTeX)
For academic papers and documentation:

```bibtex
@dataset{panging2026mend,
  author = {Panging, Pranjal},
  title = {Mising-English Numerical Dataset (MEND): A 100k Parallel Corpus},
  year = {2026},
  publisher = {GitHub},
  version = {1.0.0},
  note = {MAK Standard Orthography; High Central Vowels (í/e) preserved},
  url = {https://github.com/pranjalpanging/datasets/tree/main/mising/numbers},
  howpublished = {\url{[https://github.com/pranjalpanging/datasets/tree/main/mising/numbers](https://github.com/pranjalpanging/datasets/tree/main/mising/numbers)}}
}
```