### Experiment 1.2: Understanding how it works
![alt text](<Screenshot 2024-05-06 194338.png>)

- `Gabriella's computer: hey hey` di print terlebih dahulu. Hal ini terjadi karena print `Gabriella's computer: hey hey` berada di luar fungsi async sehingga dieksekusi tanpa perlu menunggu fungsi async selesai dieksekusi. Oleh karena itu dalam kasus ini `Gabriella's computer: hey hey` di print terlebih dahulu karena fungsi async masih menunggu hasil dari future.