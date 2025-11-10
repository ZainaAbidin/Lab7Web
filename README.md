# PHP DASAR
<img width="1920" height="1080" alt="Screenshot (106)" src="https://github.com/user-attachments/assets/33eded7f-f5c3-4297-84ca-a8a46abb8837" />

Buat file `php_dasar.php` berisi HTML dasar dan skrip PHP yang mencetak Hello World. Buka `http://localhost/lab7_php_dasar/php_dasar.php` untuk melihat hasilnya. Tujuan langkah ini: memastikan PHP berjalan dan dapat menyisip ke halaman HTML. 

# Variable PHP
<img width="1920" height="1080" alt="Screenshot (107)" src="https://github.com/user-attachments/assets/032c2d2f-cb7b-4e67-9f28-53559a71ed5a" />

Tambahkan variabel `$nim dan $nama`, lalu tampilkan nilainya. Ini mengenalkan deklarasi variabel, penggabungan string `(.)`, serta interpolasi string dengan tanda kutip ganda.


`Predefine Variable $_GET`
<img width="1920" height="1080" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/67d713c5-721c-48de-9b35-267515a9faba" />

Baca nilai dari URL menggunakan `$_GET['nama']` lalu cetak: Selamat Datang `{nama}`. Uji dengan membuka:
`http://localhost/lab7_php_dasar/latihan2.php?nama=Agung`. Ini memperlihatkan cara menerima data dari query string

# Membuat Form Input
<img width="1920" height="1080" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/78a44b0b-fd2f-4b40-93db-ba7ab82df6e7" />

Buat form sederhana dengan input teks `name="nama"` dan tombol submit. Saat disubmit, PHP membaca `$_POST['nama']` lalu menampilkan Selamat Datang `{nama}`. Ini memperkenalkan alur form → kirim data → proses server. (Catatan: di modul, akses langsung `$_POST['nama']`; jika ingin menghindari peringatan saat halaman pertama kali dibuka, gunakan operator null-coalescing seperti yang sudah kita bahas.)

# Operator
<img width="1920" height="1080" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/8ea6c0c2-f05c-492c-ad58-2e006da572de" />

Hitung gaji bersih setelah pajak: set `$gaji` dan `$pajak`, lalu kurangi untuk mendapatkan `$thp`. Ini memperkenalkan operasi aritmatika dan prioritas operator dalam PHP

# Kondisi IF
<img width="1920" height="1080" alt="Screenshot (111)" src="https://github.com/user-attachments/assets/5f8af030-ae32-4271-99de-c911e394267b" />

Ambil nama hari dengan date`("l")`, lalu cetak terjemahannya `(Minggu/Senin/Selasa)` tergantung kondisi. Tujuannya: memahami percabangan dasar untuk mengambil keputusan

# Kondisi Switch
<img width="1920" height="1080" alt="Screenshot (112)" src="https://github.com/user-attachments/assets/ce9bee39-73c4-4091-9b29-4dee687bcbe3" />

Gunakan `switch` pada nilai hari yang sama untuk menulis logika yang setara tetapi lebih rapi ketika banyak cabang. Ada case untuk Sunday, Monday, Tuesday, dan default (Sabtu).

# Perulangan for
<img width="1920" height="1080" alt="Screenshot (113)" src="https://github.com/user-attachments/assets/65dd2ae7-b82a-43db-83b9-058816c3dbe4" />

Cetak angka 1–10 dengan for `($i=1; $i<=10; $i++)` lalu cetak mundur 10–1. Tujuannya: mengenalkan perulangan dengan penghitung (counter).

# Perulangan while
<img width="1920" height="1080" alt="Screenshot (114)" src="https://github.com/user-attachments/assets/b57634e8-f974-49cb-a4cf-e4c28bab52ca" />

Mulai dari `$i=1`, selama kondisi `($i<=10)` bernilai benar, cetak nilai dan tingkatkan `$i`. Ini menekankan perbedaan while (cek kondisi sebelum blok dieksekusi)

# Perulangan dowhile
<img width="1920" height="1080" alt="Screenshot (115)" src="https://github.com/user-attachments/assets/2c166b54-e47a-4b37-8b43-61a683529cbd" />

Mirip `while`, tetapi blok dijalankan minimal sekali sebelum kondisi dicek. Cetak 1–10 dengan pola `do { ...; $i++; } while ($i<=10);`.




# Pertanyaan dan Tugas
```
    <h2>Form Input</h2>
    <form method="post" action="">
        <label>Nama: </label>
        <input type="text" name="nama">
        <input type="submit" value="Kirim">
    </form>
    <?php
    $nama = $_POST['nama'] ?? '';
    echo 'Selamat Datang' . ($nama !== '' ? ' ' . htmlspecialchars($nama) : '');
    ?>

    <hr>

    
    <h2>Operator</h2>
    <?php
    $gaji = 1000000;
    $pajak = 0.1;
    $thp = $gaji - ($gaji * $pajak);
    echo "Gaji sebelum pajak = Rp. $gaji <br>";
    echo "Gaji yang dibawa pulang = Rp. $thp";
    ?>

    <hr>

    
    <h2>Kondisi IF</h2>
    <?php
    $nama_hari = date("l");
    if ($nama_hari == "Sunday") {
        echo "Minggu";
    } elseif ($nama_hari == "Monday") {
        echo "Senin";
    } else {
        echo "Selasa";
    }
    ?>

    <hr>

    <h2>Kondisi Switch</h2>
    <?php
    $nama_hari = date("l");
    switch ($nama_hari) {
        case "Sunday":
            echo "Minggu";
            break;
        case "Monday":
            echo "Senin";
            break;
        case "Tuesday":
            echo "Selasa";
            break;
        default:
            echo "Sabtu";
    }
    ?>

    <hr>

    <h2>Perulangan for</h2>
    <?php
    echo "Perulangan 1 sampai 10 <br />";
    for ($i = 1; $i <= 10; $i++) {
        echo "Perulangan ke: " . $i . "<br />";
    }
    echo "Perulangan Menurun dari 10 ke 1 <br />";
    for ($i = 10; $i >= 1; $i--) {
        echo "Perulangan ke: " . $i . "<br />";
    }
    ?>

    <hr>

    <h2>Perulangan while</h2>
    <?php
    echo "Perulangan 1 sampai 10 <br />";
    $i = 1;
    while ($i <= 10) {
        echo "Perulangan ke: " . $i . "<br />";
        $i++;
    }
    ?>

    <hr>

    <h2>Perulangan dowhile</h2>
    <?php
    echo "Perulangan 1 sampai 10 <br />";
    $i = 1;
    do {
        echo "Perulangan ke: " . $i . "<br />";
        $i++;
    } while ($i <= 10);
    ?>

</body>
</html>
```

# Output
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f92d9747-dc05-493f-8cc8-8de2fb5775b8" />

## Penjelasan
Program ini menerima input nama, tanggal lahir, dan pekerjaan melalui formulir PHP.
Arsitektur menerapkan separation of concerns antara logika pemrosesan dan presentasi HTML. Eksekusi penuh terjadi saat permintaan berjenis POST; jika belum, halaman hanya merender form.
Input diambil dari `$_POST` dengan null coalescing untuk mencegah kunci yang belum ada. Nama dinormalisasi dengan `trim()`, tanggal lahir mengikuti format Y-m-d dari input date.
Validasi memeriksa nama wajib, mem-parsing tanggal secara ketat, dan memverifikasi pekerjaan pada whitelist.

Jika valid, umur dihitung sebagai tahun penuh menggunakan `DateTime::diff()` terhadap tanggal hari ini. Pemetaan pekerjaan ke label dan gaji dikelola dalam associative array terpusat untuk konsistensi. Gaji kemudian diformat ke Rupiah melalui fungsi utilitas `rupiah()` agar tampil seragam.
Seluruh data yang berasal dari pengguna di-escape dengan `htmlspecialchars()` demi mencegah XSS.
Data hasil disusun ke paket berisi nama, tanggal lahir terformat, umur, pekerjaan, dan gaji numerik. Presentasi menampilkan tabel ringkas hanya ketika paket hasil tersedia setelah validasi sukses.

Form menerapkan sticky value agar isian tetap terisi setelah pengiriman dan koreksi. Aksesibilitas dijaga dengan label terhubung id, serta penggunaan fieldset dan legend yang semantik.
Alur tampilan bersifat kondisional: daftar galat muncul bila validasi gagal dievaluasi. Saat validasi berhasil, yang ditampilkan hanyalah ringkasan hasil yang relevan bagi pengguna.
Struktur data yang terpisah memudahkan penambahan profesi baru atau perubahan skema gaji. Desain ini menyederhanakan pemeliharaan dan perluasan aturan tanpa mengganggu antarmuka.

