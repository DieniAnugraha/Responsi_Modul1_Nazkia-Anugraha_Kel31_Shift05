REST API Peminjaman Buku Perpustakaan

Backend REST API sederhana untuk pencatatan peminjaman buku perpustakaan menggunakan Node.js, Express, dan Supabase

Identitas  : 
- Nama: Nazkia Qolbie Dieni Anugraha
- NIM: 21120124140123
- Kelompok: 31
- Shift: 05

Tech Stack : 
- Node.js
- Express.js
- Supabase (PostgreSQL)
- Vercel

Struktur Tabel (`loans`)
| Kolom | Tipe | Keterangan |
| --- | --- | --- |
| `id` | UUID | Primary key, dibuat otomatis |
| `member_name` | Text | Nama anggota, wajib |
| `member_email` | Text | Email anggota, wajib |
| `book_title` | Text | Judul buku, wajib |
| `status` | Text | `Dipinjam`, `Dikembalikan`, atau `Terlambat` |

Endpoints API
| Method | Endpoint | Keterangan |
| --- | --- | --- |
| `GET` | `/loans` | Melihat semua data / filter status (contoh: `/loans?status=Terlambat`) |
| `POST` | `/loans` | Menambah data peminjaman baru |
| `PUT` | `/loans/:id` | Mengubah data peminjaman berdasarkan ID |
| `DELETE` | `/loans/:id` | Menghapus data peminjaman berdasarkan ID |

#Panduan Instalasi dan Menjalankan Lokal
1. Clone repo ini:
   ```bash
   git clone [https://github.com/DieniAnugraha/Responsi_Modul1_Nazkia-Anugraha_Kel31_Shift05.git](https://github.com/DieniAnugraha/Responsi_Modul1_Nazkia-Anugraha_Kel31_Shift05.git)
2. Install dependency:
npm install
3. Buat file .env di folder utama proyek dan isi dengan kredensial Supabase:
SUPABASE_URL=[https://jqhxifnmkkzzcvczfvnn.supabase.co](https://jqhxifnmkkzzcvczfvnn.supabase.co)
SUPABASE_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
PORT=3000
4. Jalankan isi database/schema.sql melalui SQL Editor di Supabase.
Jalankan server:
npm run dev
5. API lokal tersedia di http://localhost:3000.

Link Hasil Deployment Vercel
Base URL API: https://responsi-modul1-nazkia-anugraha.vercel.app
