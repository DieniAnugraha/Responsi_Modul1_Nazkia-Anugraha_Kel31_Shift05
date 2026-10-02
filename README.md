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

Contoh Request and Response :
1. Menampilkan Seluruh Data / Filter Status (GET)
Endpoint: GET /loans atau dengan filter GET /loans?status=Terlambat

{
  "success": true,
  "message": "Berhasil mengambil data peminjaman buku",
  "count": 1,
  "data": [
    {
      "id": "c0a80112-8941-11ee-b9d1-0242ac120002",
      "member_name": "Nazkia Anugraha",
      "book_title": "Pemrograman Node.js",
      "borrow_date": "2026-03-01",
      "return_date": "2026-03-08",
      "status": "Dipinjam"
    }
  ]
}

2. Menambah Data Peminjaman (POST) : 
Endpoint: POST /loans

{
  "member_name": "Budi Santoso",
  "book_title": "Belajar Express & Supabase",
  "borrow_date": "2026-03-02",
  "return_date": "2026-03-09",
  "status": "Dipinjam"
}

 Response
{
  "success": true,
  "message": "Data peminjaman berhasil ditambahkan",
  "data": {
    "id": "8f332c11-92b1-4e22-8110-3b8591f4ae22",
    "member_name": "Budi Santoso",
    "book_title": "Belajar Express & Supabase",
    "borrow_date": "2026-03-02",
    "return_date": "2026-03-09",
    "status": "Dipinjam"
  }
}

3. Memperbarui Data (PUT)
Endpoint: PUT /loans/:id

{
  "status": "Dikembalikan"
}

Response:
{
  "success": true,
  "message": "Data peminjaman berhasil diperbarui"
}

4. Menghapus Data (DELETE)
Endpoint: DELETE /loans/:id

Response :
{
  "success": true,
  "message": "Data peminjaman berhasil dihapus"
}




#Panduan Instalasi dan Menjalankan Lokal
Clone repo ini:
   ```bash
   git clone [https://github.com/DieniAnugraha/Responsi_Modul1_Nazkia-Anugraha_Kel31_Shift05.git](https://github.com/DieniAnugraha/Responsi_Modul1_Nazkia-Anugraha_Kel31_Shift05.git)
1. Install dependency:
npm install
2. Buat file .env di folder utama proyek dan isi dengan kredensial Supabase:
SUPABASE_URL=[https://your-project-id.supabase.co](https://your-project-id.supabase.co)
SUPABASE_KEY=your-supabase-anon-key
PORT=3000
3. Jalankan isi database/schema.sql melalui SQL Editor di Supabase.
4. Jalankan server:
npm run dev
5. API lokal tersedia di http://localhost:3000.

Link Hasil Deployment Vercel
Base URL API: https://responsi-modul1-nazkia-anugraha.vercel.app
