# Genetic Algorithm for Function Optimization

Repositori ini berisi implementasi **Algoritma Genetika (Genetic Algorithm - GA)** untuk mengoptimalkan nilai dari enam bobot ($w_1$ hingga $w_6$) guna memaksimalkan fungsi linear berikut:

$$
y = w_1x_1 + w_2x_2 + w_3x_3 + w_4x_4 + w_5x_5 + w_6x_6
$$

Dengan nilai input konstan:
$$
(x_1, x_2, x_3, x_4, x_5, x_6) = (3, -1, 4.5, 6, -10, -5.7)
$$

Batas nilai untuk setiap bobot ($w$) adalah antara **-4.0 hingga 4.0**. Batas teoretis maksimal yang dapat dicapai dari persamaan ini adalah **120.8**.

## Cara Kerja

Algoritma genetika ini meniru proses evolusi alamiah melalui tahapan-tahapan berikut:

1. **Inisialisasi**: Populasi awal berisi 30 solusi (kromosom) acak dibuat dengan nilai gen antara -4.0 dan 4.0.
2. **Evaluasi**: Setiap solusi dihitung nilai kebugarannya (*fitness value*) menggunakan fungsi kebugaran sum-of-products.
3. **Seleksi**: Solusi-solusi terbaik dipilih secara acak menggunakan metode berbobot berbasis nilai fitness untuk dijadikan induk (*parents*).
4. **Crossover (Penyilangan)**: Menggabungkan gen dari pasangan induk untuk menghasilkan keturunan (*offspring*) baru (menggunakan metode satu titik potong tengah).
5. **Mutasi**: Memberikan variasi acak kecil pada gen anak yang dihasilkan agar tidak terjebak pada solusi optimum lokal.
6. **Substitusi**: Mengganti populasi lama yang kurang fit dengan induk terpilih dan anak hasil mutasi yang baru.
7. **Terminasi**: Algoritma berhenti setelah mencapai jumlah generasi yang ditentukan (default: 100 generasi).

## Struktur Kode

* `cal_pop_fitness`: Fungsi untuk menghitung nilai fitness populasi.
* `select_mating_pool`: Seleksi induk menggunakan metode peluang proporsional terhadap fitness.
* `crossover`: Melakukan persilangan gen dari induk.
* `mutation`: Melakukan mutasi gen dengan batas toleransi.
* `run_ga`: Fungsi pembungkus untuk menjalankan satu siklus penuh algoritma genetika.
* `run_experiment`: Menjalankan eksperimen untuk melihat pengaruh parameter GA terhadap hasil akhir.

## Hasil Eksperimen Parameter

Kami melakukan pengujian dengan 20 kali percobaan acak (*runs*) untuk melihat pengaruh perubahan parameter terhadap tingkat konvergensi:

### 1. Pengaruh Jumlah Mutasi per Anak (`num_mutations`)
* **`num_mutations = 1`**: Fitness akhir rata-rata **116.63** (~96.5% dari batas maks).
* **`num_mutations = 3`**: Fitness akhir rata-rata **117.15** (~97.0% dari batas maks).
* **`num_mutations = 5`**: Fitness akhir rata-rata **113.10** (~93.6% dari batas maks).

### 2. Pengaruh Jumlah Induk Terpilih (`num_parents`)
* **`num_parents = 2`**: Fitness akhir rata-rata **112.02** (~92.7% dari batas maks).
* **`num_parents = 4`**: Fitness akhir rata-rata **117.15** (~97.0% dari batas maks).
* **`num_parents = 8`**: Fitness akhir rata-rata **119.27** (~98.7% dari batas maks).

## Cara Penggunaan

### Prasyarat
Pastikan Anda sudah menginstal pustaka Python yang diperlukan:
```bash
pip install numpy matplotlib
```

### Menjalankan Program
1. Buka berkas notebook (`.ipynb`) ini di Google Colab atau Jupyter Notebook.
2. Jalankan semua cell secara berurutan.
3. Hasil akhir berupa visualisasi grafik perkembangan nilai fitness serta perbandingan parameter akan langsung ditampilkan di bagian bawah notebook.
