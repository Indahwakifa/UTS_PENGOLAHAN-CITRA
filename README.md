# UTS_PENGOLAHAN-CITRA
NAMA:INDAH WAFIKAH
KELAS:1241E


### **LAPORAN UTS PENGOLAHAN CITRA DIGITAL**
**Implementasi Berbagai Metode Segmentasi pada Citra Sintetis**

#### **1. Pembuatan Citra (Input)**
Dalam proyek ini, aku nggak pakai foto dari luar, tapi bikin sendiri lewat kodingan Python agar hasilnya lebih terkontrol. Gambarnya berupa 5 lingkaran dengan tingkat terang-gelap yang beda-beda, terus aku tambahin efek bintik-bintik (*noise*) biar kayak foto asli[cite: 1].

*(Sisipkan file: **Screenshot 2026-05-04 111258.jpg** sebelah kiri bagian "Asli")*

---

#### **2. Metode 1: Thresholding (Pengambangan)**
Ini cara paling dasar buat misahin objek. Intinya, kita nentuin batas warna: yang terang jadi putih, yang gelap jadi hitam[cite: 1].
*   **Global**: Pakai satu angka batas untuk semua bagian[cite: 1].
*   **Otsu**: Paling pintar, karena dia otomatis nyari angka batas yang paling pas[cite: 1].
*   **Adaptif**: Bagus kalau gambarnya punya pencahayaan yang nggak rata[cite: 1].

**Hasil Visualisasi:**
*(Sisipkan file: **Screenshot 2026-05-04 110655.jpg**)*
*Di sini kelihatan kalau metode Otsu paling bersih hasilnya dibanding yang lain.*

---

#### **3. Metode 2: Edge Detection (Deteksi Tepi)**
Kalau ini tujuannya cuma buat nyari garis pinggir dari setiap bulatan[cite: 1].
*   **Sobel**: Garis tepinya kelihatan lebih tebal dan agak kasar[cite: 1].
*   **Canny**: Hasilnya jauh lebih rapi, tipis, dan presisi mengikuti bentuk bulatan[cite: 1].

**Hasil Visualisasi:**
*(Sisipkan file: **Screenshot 2026-05-04 111214.jpg**)*

---

#### **4. Metode 3: Region Growing & KMeans**
Dua metode ini cara kerjanya beda lagi:
*   **Region Growing**: Kita pilih satu titik, nanti dia bakal "nularin" warna ke tetangganya yang warnanya mirip[cite: 1]. Di foto, aku kasih warna hijau buat area yang terpilih[cite: 1].
*   **KMeans**: Ini pakai logika pengelompokan warna (clustering). Dia bakal ngelompokkin piksel-piksel yang warnanya mirip jadi satu grup[cite: 1].

**Hasil Visualisasi:**
*(Sisipkan file: **Screenshot 2026-05-04 111258.jpg** dan **Screenshot 2026-05-04 111227.jpg**)*

---

#### **5. Metode 4: Watershed (Paling Canggih)**
Metode ini keren banget karena bisa misahin dua objek yang nempel[cite: 1]. Logikanya kayak air yang ngalir. Kita cari dulu pusat setiap bulatan (pakai *Distance Transform*), terus kita kasih garis pembatas merah di antara mereka[cite: 1].

**Hasil Visualisasi:**
*(Sisipkan file: **Screenshot 2026-05-04 111656.jpg**)*
*Perhatikan bagian "Distance" yang menyala terang, itu adalah pusat setiap objek.*

---

#### **6. Evaluasi Hasil (Cek Akurasi)**
Terakhir, aku ngecek seberapa sukses segmentasi ini dengan ngebandingin hasil kodingan (**Prediksi**) sama kunci jawaban aslinya (**Ground Truth**)[cite: 1]. Aku pakai hitungan **IoU** dan **Dice** buat dapet angka persentase kemiripannya[cite: 1].

**Hasil Visualisasi:**
*(Sisipkan file: **Screenshot 2026-05-04 112158.jpg**)*

---

**Kesimpulan:**
Dari semua percobaan di file `main.py` ini, metode **Otsu** dan **Watershed** adalah yang paling efektif buat misahin objek bulatan di gambar ini dengan rapi dan akurat[cite: 1].
