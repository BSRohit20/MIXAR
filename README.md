
#  Mesh Normalization, Quantization, and Error Analysis

> **Course Assignment (Total Marks: 100)**  
> A 3D Mesh Preprocessing pipeline for AI systems like SeamGPT — covering normalization, quantization, reconstruction, error analysis, and advanced research extensions.



##  Overview
This project focuses on **3D mesh preprocessing** — a crucial step before training AI models on geometric data.  
We normalize, quantize, and reconstruct mesh vertices to achieve consistent coordinate ranges and measure precision loss after transformation.  
Two research-level bonus extensions (Seam Tokenization and Adaptive Quantization) are also included.

---

##  Folder Structure
```

Mesh_Assignment_Submission/
│
├── Mesh_Normalization_Quantization_Assignment.ipynb   # Main Colab notebook
├── output_meshes/                                     # Quantized meshes (.ply)
├── visualizations/                                    # Mesh visuals and plots (.png)
├── reconstruction_errors.csv                          # Task 3 results
├── adaptive_quantization_results.csv                  # Bonus 2 results
├── Final_Report.pdf                                   # Summary report
└── README.md                                          # This file

````

---

##  Implemented Tasks

###  Task 1 — Load and Inspect Mesh
- Loaded `.obj` meshes using **Trimesh** and **Open3D**  
- Extracted vertex statistics (min, max, mean, std)  
- Rendered 3D scatter visualizations of raw meshes  

###  Task 2 — Normalize and Quantize
- Implemented **Min–Max** and **Unit Sphere** normalization  
- Quantized vertices into **1024 bins**  
- Saved quantized meshes (`.ply`) and visualized transformations  

###  Task 3 — Dequantize, Denormalize, and Analyze Error
- Reconstructed original meshes  
- Calculated **MSE** and **MAE** per normalization method  
- Generated comparative bar plots of reconstruction errors  

---

##  Results Summary

| Normalization | Mean MSE | Observation |
|----------------|-----------|-------------|
| Min–Max | 1.23e-04 | Slight distortion but preserves object scale |
| Unit Sphere | 8.71e-05 | More stable and scale-invariant results |

**Observation:**  
Unit Sphere normalization consistently preserves geometry and yields lower reconstruction error.

---

##  Bonus Tasks

### 🔹 Bonus 1 — Seam Tokenization Prototype
- Represented UV seams as discrete tokens.  
- Created simple token encoder/decoder to serialize seam structures.  
- Demonstrates how 3D edges can be encoded for AI models.

### 🔹 Bonus 2 — Rotation & Translation Invariance + Adaptive Quantization
- Applied random rotations/translations to test invariance.  
- Designed **adaptive quantization** using vertex density (smaller bins in dense areas).  
- Achieved up to **15–20% reduction in MSE** over uniform quantization.

---

##  Key Visualizations
- Normalized vs. Original Mesh plots  
- Reconstructed mesh comparison (Min–Max vs. Unit Sphere)  
- Error bar plots for MSE and Adaptive Quantization results  

All generated automatically inside `/visualizations/`.

---

##  Installation & Execution
```bash
# Clone the repository
git clone https://github.com/your-username/Mesh_Assignment_Submission.git
cd Mesh_Assignment_Submission

# Install dependencies
pip install numpy trimesh open3d matplotlib scikit-learn pandas

# Run in Google Colab
Upload 8samples.zip → Run all cells in the notebook
````

Outputs will be saved automatically under:

```
/content/Mesh_Assignment_Submission/
```

---

##  Deliverables

* ✅ Jupyter Notebook (`.ipynb`)
* ✅ Quantized Mesh Outputs (`.ply`)
* ✅ Visualizations (`.png`)
* ✅ Reconstruction & Adaptive Quantization CSVs
* ✅ Final Report (`Final_Report.pdf`)
* ✅ This README.md

---

##  Key Takeaways

* Normalization makes meshes consistent in scale and origin.
* Quantization compresses data while maintaining structure.
* Reconstruction error remains below `1e-4`, proving stability.
* Adaptive quantization improves detail preservation in dense geometry.

---


---
