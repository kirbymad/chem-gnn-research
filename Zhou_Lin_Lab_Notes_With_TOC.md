
# 🧠 Research Notes: Zhou Lin Lab – FBGNN-MBE Project

## 📚 Table of Contents
1. [Current Role](#current-role)
2. [Project Overview](#project-overview)
   - [Objective](#objective)
   - [Method](#method)
3. [Directory Breakdown (on Unity HPC)](#directory-breakdown-on-unity-hpc)
4. [What Model Am I Working With?](#what-model-am-i-working-with)
   - [Fragment-Based Graph Neural Network with MBE](#fragment-based-graph-neural-network-with-mbe-fbgnn-mbe)
   - [How to Inspect the Model](#how-to-inspect-the-model)
5. [Related GNN Models and Tools](#related-gnn-models-and-tools)
6. [Notes to Self](#notes-to-self)

## 📍 Current Role
I am working as an undergraduate researcher under **Siqi Chen** in the **Zhou Lin Lab** at UMass Chemical Engineering. Our project focuses on developing a **Fragment-Based Graph Neural Network** (FBGNN) model integrated with **Many-Body Expansion (MBE)** theory to predict full-dimensional **potential energy surfaces (FD-PES)**.

---

## 🧪 Project Overview

### ✳️ Objective
- Efficiently model large molecular and material systems using **first-principles QM data**.
- Apply **Many-Body Expansion (MBE)** to fragment large systems.
- Use a **Graph Neural Network (GNN)** to learn fragment interactions and predict system-level energies.

### 🧬 Method
- Divide complex chemical systems into **1-body, 2-body, ... n-body** fragments.
- Perform **Q-Chem** calculations to get reference energies.
- Train a custom GNN (FBGNN) on these fragment features.
- Predict many-body energy corrections to reconstruct the total energy.

---

## 🗂️ Directory Breakdown (on Unity HPC)

```bash
/home/chakr25p_mtholyoke_edu
```

| Folder/File              | Purpose |
|--------------------------|---------|
| `MBE`, `MBE_new`, `mbe`  | Scripts and model configs for Many-Body Expansion and GNN integration. |
| `mbe_models`             | Contains training scripts, GNN architectures, and evaluation code. |
| `mbe_dataset`            | Stores fragment energies and metadata used for training/testing the GNN. |
| `in_memory_data`         | Likely contains preprocessed datasets or fast-access memory maps. |
| `q-chem`                 | Q-Chem input/output files for first-principles QM calculations. |
| `chem_environment.yml`   | YAML file defining Python/conda dependencies for this project. |
| `copy_env.sh`, `copy.sh` | Scripts to clone working environments or copy files across directories. |
| `nmr-to-structure`       | Likely a utility for converting NMR spectra into molecular structures. |
| `scratch`                | Temporary files and outputs from simulations or job runs. |
| `catalyst_files.tar.gz`  | Possibly an archived dataset or benchmark file. |
| `ondemand`               | May relate to Open OnDemand usage or visual sessions. |

---

## 🧠 What Model Am I Working With?

### ✅ Fragment-Based Graph Neural Network with MBE (FBGNN-MBE)

- Combines **fragment-wise QM calculations** with a **GNN architecture**.
- Designed to capture many-body energy contributions and build FD-PES.
- Custom GNN likely defined in `mbe_models/train.py` or `run_models.py`.

### 🔍 How to Inspect the Model

```bash
cd mbe_models
grep -i model *.py
```

Look for architecture classes like `FBGNNModel`, `GraphNet`, or `MPNN`.

---

## 🔗 Related GNN Models and Tools

| Model         | Description | Relevance |
|---------------|-------------|-----------|
| [FragGen](https://github.com/HaotianZhangAI4Science/FragGen) | 3D fragment-wise molecule generation | ⭐⭐⭐⭐ |
| [GraphFP](https://github.com/lvkd84/GraphFP) | Fragment-level pretraining & finetuning | ⭐⭐⭐⭐ |
| [FragNet](https://github.com/InformaticsMatters/fragnet) | Fragment network analysis toolbox | ⭐⭐⭐ |
| [MolGAT](https://github.com/mesfind/molgnn) | GNN for property prediction | ⭐⭐ |
| [MGSSL](https://github.com/zaixizhang/MGSSL) | Motif-based self-supervised learning | ⭐⭐ |
| [Subgraphormer](https://github.com/BarSGuy/Subgraphormer) | Transformer-based subgraph model | ⭐ |
| [ESC-GNN](https://github.com/pkuyzy/ESC-GNN) | Efficient substructure counting | ⭐ |

---

## 📌 Notes to Self

- Check `MBE_new` for the most up-to-date scripts/configs.
- `q-chem` is where input/output files for QM calculations live.
- Make sure your `chem_environment.yml` is synced with `conda env`.
- Keep backups of your datasets and results outside of Unity—storage is not backed up!
- Use `copy_env.sh` to reproduce Siqi’s working environment.
- Useful command:
  ```bash
  unity-compute  # to switch to a compute node
  ```

---

👩‍🔬 Authored by: **Puja Chakraborty**  
🧪 Undergraduate Researcher  
🔬 Zhou Lin Lab, UMass Amherst
