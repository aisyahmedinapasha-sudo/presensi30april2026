Bagian Import & Data
Kode ini mengimpor library random untuk proses acak dalam algoritma genetika dan matplotlib.pyplot untuk visualisasi grafik, lalu mendefinisikan data utama seperti daftar mata kuliah (courses), ruang (rooms), waktu (times), serta mapping dosen (lecturers), dan juga parameter penting algoritma seperti ukuran populasi (POP_SIZE), jumlah generasi (GENERATIONS), tingkat mutasi (MUTATION_RATE), dan jumlah elit (ELITE_SIZE) yang akan dipertahankan di setiap generasi.

Fungsi create_schedule dan init_population
Fungsi create_schedule menghasilkan satu solusi jadwal dengan menggabungkan setiap mata kuliah dengan dosen tetap serta ruang dan waktu yang dipilih secara acak, sedangkan init_population membuat populasi awal berupa kumpulan jadwal sebanyak POP_SIZE yang akan menjadi titik awal proses evolusi dalam algoritma genetika.

Fungsi conflict_details
Fungsi ini bertugas mendeteksi konflik dalam jadwal dengan memeriksa apakah ada dua mata kuliah yang menggunakan ruang dan waktu yang sama atau diajar oleh dosen yang sama pada waktu yang sama, lalu menyimpan setiap konflik dalam bentuk deskripsi teks ke dalam list details untuk dianalisis lebih lanjut.

Fungsi fitness
Fungsi fitness digunakan untuk mengevaluasi kualitas suatu jadwal dengan menghitung jumlah konflik yang terjadi, kemudian memberikan skor awal 100 dan menguranginya sebesar 15 poin untuk setiap konflik, serta memastikan nilai akhir tidak negatif sehingga semakin sedikit konflik maka semakin tinggi nilai fitness.

Fungsi repair
Fungsi repair berfungsi memperbaiki jadwal yang memiliki konflik ruang dan waktu dengan cara mengganti kombinasi ruang dan waktu yang bentrok ke slot lain yang masih tersedia, sehingga membantu mengurangi konflik tanpa harus membuat jadwal baru dari awal

Fungsi selection
Fungsi selection menerapkan metode tournament selection dengan memilih tiga individu secara acak dari populasi lalu mengembalikan individu dengan nilai fitness terbaik sebagai parent untuk proses reproduksi.

Fungsi crossover
Fungsi crossover menggabungkan dua parent jadwal dengan memilih titik potong secara acak, lalu mengambil sebagian gen dari parent pertama dan sisanya dari parent kedua untuk menghasilkan satu offspring baru.

Fungsi mutate
Fungsi mutate melakukan perubahan acak pada satu elemen dalam jadwal dengan mengganti ruang dan waktu suatu mata kuliah, yang bertujuan menambah variasi dalam populasi agar tidak terjebak pada solusi lokal

Fungsi GA (Genetic Algorithm utama)
Fungsi GA merupakan inti algoritma yang menjalankan proses evolusi mulai dari inisialisasi populasi, evaluasi fitness, seleksi individu terbaik, crossover, mutasi, hingga pembentukan generasi baru, sambil mencatat perkembangan nilai fitness terbaik dan rata-rata di setiap generasi, serta menghentikan proses jika solusi optimal ditemukan setelah sejumlah iterasi tertentu.

Bagian Hasil Akhir & Visualisasi
Setelah proses evolusi selesai, program menampilkan jadwal terbaik beserta nilai fitness dan detail konflik (jika ada), lalu memvisualisasikan perkembangan fitness terbaik dan rata-rata menggunakan grafik untuk menunjukkan bagaimana kualitas solusi meningkat selama proses generas

Bagian Eksekusi (main)
Bagian ini memastikan bahwa fungsi GA dijalankan hanya ketika file dieksekusi secara langsung, sehingga program akan otomatis memulai proses algoritma genetika saat dijalankan.
