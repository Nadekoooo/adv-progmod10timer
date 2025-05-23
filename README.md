### 1.2. Understanding how it works
![alt text](image.png)

Program di gambar menunjukkan alur eksekusi async di Rust dengan hasil:

"ChristianYudistira's computer: howdy!" muncul terlebih dahulu
"ChristianYudistira's computer: hey hey" muncul selanjutnya
Setelah jeda 2 detik, "ChristianYudistira's computer: done!" muncul terakhir
Ini terjadi karena:

Penggunaan .await pada TimerFuture menyebabkan tugas tersebut "ditunda" sementara
Saat tugas ditunda, program tidak memblokir seluruh thread
Program dapat melanjutkan eksekusi kode lainnya (mencetak "hey hey")
Setelah waktu tunggu 2 detik selesai, eksekusi tugas yang ditunda dilanjutkan secara asingkron.