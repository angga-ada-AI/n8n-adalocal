# n8n — adaLOCAL

Resep pemasangan **n8n** untuk [adaLOCAL](https://adacode.ai) di adaCODE App: dipasang dan dijalankan
di komputer pengguna dengan satu klik, langsung tersambung ke model AI adaCODE.

Otomasi alur kerja — hubungkan ratusan layanan tanpa menulis kode.

- App asli: https://github.com/n8n-io/n8n
- Lisensi app asli: Sustainable Use License (repo ini hanya berisi resep pemasangan, bukan kode app-nya)

## Isi repo

| Berkas | Fungsi |
|---|---|
| `adacode.json` | Manifes: prasyarat, langkah `pasang`, cara `jalan`, `perbarui`. Data JSON, bukan skrip. |
| ikon & `gambar.jpg` | Ikon dan gambar kartu di katalog adaLOCAL. |

## Cara app ini masuk ke katalog adaLOCAL

Admin adaCODE mendaftarkan repo ini di `/admin/app-katalog` beserta **commit SHA lengkap**. Server mengambil
`adacode.json` pada commit itu, memeriksanya, lalu menyalinnya. Karena yang dipakai selalu commit tertentu
(bukan cabang), perubahan di repo ini **tidak** sampai ke pengguna sampai admin meninjau dan menyimpan SHA baru.

Aturan manifes:
- Aksi yang dikenal pemasang: `log`, `tulis`, `folder`, `venv`, `shell`.
- Jangan menulis rahasia di sini. Kunci API adaCODE dan alamat gateway diisi server lewat pengisi tempat
  `{{kunci_api_pelanggan}}` dan `{{gateway_adacode}}`; jalur lokal lewat `{{folder_app}}`.
- Semua berkas app wajib berada di foldernya sendiri (supaya bisa dipindah ke VPS).
