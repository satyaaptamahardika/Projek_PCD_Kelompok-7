Identifikasi Penyakit Daun dengan SVM

Jurnal RAPIDS — Universitas Negeri Surabaya, 2026
Identifikasi Penyakit Daun Menggunakan Ekstraksi Fitur Warna dan Tekstur dengan Klasifikasi Support Vector Machine

Deskripsi
Proyek ini membangun sistem otomatis untuk mengidentifikasi penyakit daun berbasis pengolahan citra digital tanpa deep learning. Sistem menggunakan kombinasi ekstraksi fitur warna dan tekstur (handcrafted features) yang kemudian diklasifikasikan menggunakan Support Vector Machine (SVM) kernel RBF.
Pipeline end-to-end yang dibangun meliputi:

1. Preprocessing — Resize, konversi RGB→HSV, CLAHE, Gaussian Blur
2. Segmentasi — Otsu thresholding, HSV masking, morphological operations
3. Ekstraksi Fitur — Color Moments, HSV Histogram, GLCM, LBP (93 fitur/citra)
4. Klasifikasi — SVM kernel RBF dengan strategi One-vs-Rest (OvR)
5. Evaluasi — Accuracy, F1-Score, Confusion Matrix, 5-Fold Cross Validation

Dataset

1. Sumber: Roboflow Universe — roboflow-100/leaf-disease-nsdsr
2. Total citra: 2.501 gambar (.jpg)
3. Anotasi: Format YOLOv8 segmentation polygon (.txt)
4. Kelas:

    1. mildew — Powdery mildew (embun tepung)
    2. rose_P01 — Penyakit mawar tipe P01
    3. rose_R02 — Penyakit mawar tipe R02


5. Split akhir: 56% train : 14% validasi : 30% test (stratified)


Dataset orisinal memiliki ketidakseimbangan kelas yang signifikan (rose_R02 tidak muncul di split validasi dan test). Dilakukan re-split stratified sebelum training.
