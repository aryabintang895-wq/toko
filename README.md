# DATABASE TOKO
Project ini adalah contoh penggunaan **JOIN pada MariaDB/MySQL** untuk menggabungkan data dari dua tabel:

pelanggan
-
pesanan
-
Relasi yang digunakan adalah 1 pelanggan dapat memiliki beberapa pesanan.

1. **Membuat Database**
 <img width="597" height="145" alt="Screenshot 2026-03-05 134946" src="https://github.com/user-attachments/assets/807b12b3-8995-4315-8762-f798b9638c55" />
 
 Database Toko dibuat untuk menyimpan data pelanggan dan pesanan.
 
2. **Membuat Tabel dan Data Tabel**
**Tabel dan Data Pelanggan**
<img width="785" height="310" alt="Screenshot 2026-03-05 140114" src="https://github.com/user-attachments/assets/17e88961-376d-4bd5-8dc0-30c9592397c2" />

Tabel pelanggan digunakan untuk menyimpan data pelanggan.

Struktur tabel:

| Kolom        | Tipe Data | Keterangan     |
| ------------ | --------- | -------------- |
| id_pelanggan | INT       | Primary key    |
| nama         | VARCHAR   | Nama pelanggan |

Contoh Data:

| id_pelanggan | nama |
| ------------ | ---- |
| 1            | andi |
| 2            | budi |
| 3            | sari |



**Tabel dan Data Pesanan**
<img width="870" height="355" alt="Screenshot 2026-03-05 140303" src="https://github.com/user-attachments/assets/3be655a4-17e6-4b2a-b2f2-844772d0e6db" />

Tabel Pesanan digunakan untuk menyimpan data produk yang dipesan pelanggan

Struktur Tabel:

| Kolom        | Tipe Data | Keterangan   |
| ------------ | --------- | ------------ |
| id_pesanan   | INT       | Primary key  |
| id_pelanggan | INT       | ID pelanggan |
| produk       | VARCHAR   | Nama produk  |

3. **Inner Join**
<img width="939" height="254" alt="Screenshot 2026-03-05 144134" src="https://github.com/user-attachments/assets/47b09e7a-0e38-4cac-9621-9bb359369b70" />

Query:

SELECT pelanggan.nama,   pesanan.produk

FROM pelanggan

INNER JOIN pesanan

ON pelanggan.id_pelanggan = pesanan.id_pelanggan;

Hasil:

| nama | produk     |
| ---- | ---------- |
| andi | laptop     |
| budi | smartphone |
| andi | headset    |

INNER JOIN hanya menampilkan data yang cocok di kedua tabel.

4. **LEFT JOIN**
<img width="948" height="287" alt="Screenshot 2026-03-05 142056" src="https://github.com/user-attachments/assets/ab83ffdb-939b-48dd-ab0d-97ed4bda1e0b" />

Query:
SELECT pelanggan.nama,  pesanan.produk

FROM pelanggan

LEFT JOIN pesanan

ON pelanggan.id_pelanggan = pesanan.id_pelanggan;

Hasil:

| nama | produk     |
| ---- | ---------- |
| andi | laptop     |
| budi | smartphone |
| andi | headset    |
| sari | NULL       |

LEFT JOIN menampilkan semua data dari tabel kiri (pelanggan).

Jika pelanggan tidak memiliki pesanan, maka produk akan bernilai NULL.

5. **Right Join**
<img width="954" height="259" alt="Screenshot 2026-03-05 142112" src="https://github.com/user-attachments/assets/b4f8d588-7d62-4752-868e-a90231faed75" />

Query:

SELECT pelanggan.nama,  pesanan.produk

FROM pelanggan

RIGHT JOIN pesanan

ON pelanggan.id_pelanggan = pesanan.id_pelanggan;

Hasil:

| nama | produk     |
| ---- | ---------- |
| andi | laptop     |
| budi | smartphone |
| andi | headset    |

RIGHT JOIN menampilkan semua data dari tabel kanan (pesanan).




