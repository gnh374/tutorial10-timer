### Experiment 1.2: Understanding how it works
![alt text](<Screenshot 2024-05-06 194338.png>)

- `Gabriella's computer: hey hey` di print terlebih dahulu. Hal ini terjadi karena print `Gabriella's computer: hey hey` berada di luar fungsi async sehingga dieksekusi tanpa perlu menunggu fungsi async selesai dieksekusi. Oleh karena itu dalam kasus ini `Gabriella's computer: hey hey` di print terlebih dahulu karena fungsi async masih menunggu hasil dari future.

### 1.3. Multiple Spawn and removing drop
![alt text](<Screenshot 2024-05-06 200740.png>)
- Dari hasil output yang dihasilkan, terlihat bahwa jumlah spawner yang banyak menyebabkan lebih banyak task dilakukan, karena setiap spawner menambahkan task baru ke dalam antrian (task sender) untuk dieksekusi. Tidak melakuka drop spawner mengakibatkan program tidak pernah berakhir karena program menganggap bahwa masih akan ada pengiriman data oleh spawner. Penggunaan drop(spawner) menandakan bahwa interaksi sudah selesai dan spawner akan ditutup.

Ketika suatu spawner memanggil fungsi spawn, task baru akan dibuat dan dimasukkan ke dalam antrian task sender. Executor kemudian akan mengambil satu task dari antrian tersebut, mengeksekusinya, dan mengulang proses tersebut hingga tidak ada task lagi dalam antrian. Penggunaan drop(spawner) menandakan bahwa interaksi telah selesai dan spawner dapat ditutup.