# 🧠 Prediksi Keramaian di Tempat Wisata Menggunakan MCNN  
### *(Studi Kasus: Gacoan)*  


![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge)
![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)
![AI](https://img.shields.io/badge/Artificial%20Intelligence-8A2BE2?style=for-the-badge)

> 📚 **Ujian Akhir Semester (UAS) – Informatika Pariwisata**  
> 👩‍💻 **Siti Nur Aini** | 210411100054  
> Universitas Trunojoyo Madura  

---

## 📘 Deskripsi Singkat  

Penelitian ini mengusulkan penerapan metode **Multi-Column Convolutional Neural Network (MCNN)** untuk **memprediksi tingkat keramaian di tempat wisata**.  
Studi kasus dilakukan pada **Gacoan**, dengan tujuan membantu manajemen dalam mengatur operasional seperti pengendalian kerumunan, pengaturan tenaga kerja, dan persediaan.  

Metode **MCNN** menghasilkan **peta kepadatan (Density Map)** yang menggambarkan distribusi orang di dalam citra, dengan hasil prediksi akurat dan efisien.  

---

## 🧩 Tujuan Penelitian  
- Mengembangkan model **prediksi kepadatan kerumunan** berbasis citra menggunakan MCNN.  
- Mengukur performa model menggunakan **dataset ShanghaiTech** dan **data primer** dari lokasi penelitian.  
- Mengevaluasi efektivitas MCNN dalam mendeteksi kerumunan dengan **Mean Average Precision (mAP)**.

---

## ⚙️ Arsitektur Sistem  

Proses penelitian melibatkan beberapa tahapan utama:  

1. **Dataset Preparation**  
   - Dataset: *ShanghaiTech Part A & B* dan data primer dari Gacoan.  
   - Splitting: 70% training, 30% testing, dan 15% validation.  

2. **Preprocessing**  
   - Resize gambar menjadi `610x610 px`.  
   - Pembuatan **Density Map** dari data *ground truth*.  

3. **Training & Validation**  
   - Model dilatih menggunakan 5 epoch.  
   - Validasi dilakukan untuk mencegah overfitting.  

4. **Modeling (MCNN)**  
   - Arsitektur terdiri dari 3 kolom CNN dengan ukuran kernel berbeda (`9x9`, `7x7`, `5x5`).  
   - Setiap kolom mengekstraksi fitur global dan lokal untuk menghasilkan peta kepadatan.  

5. **Evaluation**  
   - Model terbaik dipilih berdasarkan performa mAP.  
   - Evaluasi dilakukan pada dataset ShanghaiTech dan data primer Gacoan.  

---

## 🧠 Metodologi MCNN  

Model **MCNN** menggunakan tiga kolom CNN paralel:  
| Kolom | Kernel | Fokus |  
|--------|---------|-------|  
| Kolom 1 | 9×9 | Fitur global (kepadatan tinggi) |  
| Kolom 2 | 7×7 | Fitur menengah |  
| Kolom 3 | 5×5 | Fitur detail & halus |  

Ketiga keluaran kolom digabung (fusion) menjadi **density map** yang menunjukkan jumlah dan distribusi orang dalam gambar.

---

## 🧪 Dataset  
- **Sumber:** [ShanghaiTech Dataset](https://www.kaggle.com/datasets/tthien/shanghaitech)  
- **Total Data:** 1.198 gambar (RGB, 330.165 individu)  
- **Part A:** Kepadatan tinggi, 482 gambar  
- **Part B:** Kepadatan rendah, 716 gambar  
- **Data Primer:** 10 gambar dari lokasi Gacoan  

---

## 📊 Hasil Eksperimen  

| Dataset | Mean Average Precision (mAP) | Keterangan |
|----------|------------------------------|-------------|
| ShanghaiTech Part A | 0.61 | Kepadatan tinggi |
| ShanghaiTech Part B | **0.85** | Kepadatan rendah, hasil terbaik |
| Data Primer Gacoan | 0.50 | Akurasi baik untuk variasi crowd |

🧠 **Kesimpulan:**  
MCNN berhasil memprediksi kepadatan kerumunan dengan **akurasi tinggi dan efisiensi waktu**.  
Part B menunjukkan performa terbaik dengan mAP 0.85.

---

## 🧰 Tools & Library  

- **Python 3.10**  
- **PyTorch** (`torch`, `torchvision`)  
- **OpenCV (cv2)**  
- **Pandas**, **NumPy**  
- **Matplotlib**, **Seaborn**  
- **Scikit-learn** (evaluasi model)  

---


## 🧾 Kesimpulan  

Model **MCNN** terbukti:  
- Efektif dalam memprediksi kepadatan kerumunan.  
- Memiliki **akurasi tinggi (mAP 0.85)** pada dataset ShanghaiTech Part B.  
- Dapat diimplementasikan untuk membantu **pengelolaan keramaian di tempat wisata seperti Gacoan**.  

---

## 🧠 Referensi  
Penelitian ini didukung oleh berbagai studi sebelumnya, termasuk:  
- Chen et al., *Scale Pyramid Network for Crowd Counting*, WACV 2019  
- Jiang et al., *Crowd Counting via Multi-Column Deconvolution Networks*, 2020  
- Hu et al., *Speech Emotion Recognition Based on Attention MCNN*, IEEE Access 2023  

---

## 🧑‍💻 Penulis  
**Siti Nur Aini**  
Program Studi Teknik Informatika – Universitas Trunojoyo Madura  
📧 *stnuraini082@gmail.com*   

---

### 🏷️ Tags  
`#MCNN` `#DeepLearning` `#CrowdCounting` `#Python` `#InformatikaPariwisata`  
