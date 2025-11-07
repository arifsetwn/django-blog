# Django Blog

Repository ini merupakan proyek untuk **Mata Kuliah Pemrograman Web** - Program Studi Pendidikan Teknologi Informasi, Universitas Muhammadiyah Surakarta (PTI UMS).

## 🌐 Demo Website

Website demo dapat diakses di: **[https://arifsetwn.pythonanywhere.com/](https://arifsetwn.pythonanywhere.com/)**

## Deskripsi Proyek

Django Blog adalah aplikasi web berbasis Django yang memungkinkan pengguna untuk membuat, mengelola, dan membagikan postingan blog. Aplikasi ini dilengkapi dengan fitur rich text editor, upload gambar header, dan sistem komentar.

## Fitur Utama

- ✍️ Membuat, mengedit, dan menghapus postingan blog
- 📝 Rich text editor menggunakan TinyMCE
- 🖼️ Upload gambar header untuk setiap postingan
- 💬 Sistem komentar pada postingan
- 👤 Autentikasi pengguna (login/logout)
- 📅 Timestamp untuk postingan dan komentar


## Teknologi yang Digunakan

- **Framework**: Django 5.1.2
- **Database**: SQLite3
- **Rich Text Editor**: django-tinymce 4.1.0
- **Image Processing**: Pillow 10.4.0
- **Python Version**: 3.10+

## Struktur Proyek

```
django/
├── blog/                   # Aplikasi blog utama
│   ├── models.py          # Model Post dan Comment
│   ├── views.py           # View logic
│   ├── urls.py            # URL routing
│   ├── forms.py           # Forms untuk Post dan Comment
│   ├── templates/         # Template HTML
│   └── static/            # File CSS dan static lainnya
├── mysite/                # Konfigurasi proyek Django
│   ├── settings.py        # Pengaturan proyek
│   ├── urls.py            # URL routing utama
│   └── wsgi.py            # WSGI configuration
├── media/                 # Folder untuk file upload
├── myenv/                 # Virtual environment
├── manage.py              # Django management script
└── requirements.txt       # Dependencies Python
```

## Instalasi dan Setup

### 1. Clone Repository

```bash
git clone https://github.com/arifsetwn/django-blog.git
cd django-blog
```

### 2. Buat Virtual Environment

```bash
python3 -m venv myenv
source myenv/bin/activate  # Untuk macOS/Linux
# atau
myenv\Scripts\activate     # Untuk Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Migrasi Database

```bash
python manage.py migrate
```

### 5. Buat Superuser (Opsional)

```bash
python manage.py createsuperuser
```

### 6. Jalankan Server Development

```bash
python manage.py runserver
```

Aplikasi akan berjalan di `http://127.0.0.1:8000/`

## Penggunaan

### Akses Admin Panel
- URL: `http://127.0.0.1:8000/admin/`
- Login menggunakan kredensial superuser yang telah dibuat

### Akses Blog
- Halaman utama: `http://127.0.0.1:8000/`
- Membuat postingan baru: Harus login terlebih dahulu
- Menambahkan komentar: Tersedia di setiap detail postingan

## Model Database

### Post
- `author`: Foreign key ke User
- `title`: Judul postingan
- `text`: Konten postingan (HTML field)
- `created_date`: Tanggal pembuatan
- `published_date`: Tanggal publikasi
- `header_image`: Gambar header (opsional)

### Comment
- `post`: Foreign key ke Post
- `author`: Nama penulis komentar
- `text`: Isi komentar
- `created_date`: Tanggal pembuatan
- `approved_comment`: Status approval komentar

## Kontribusi

Proyek ini dibuat untuk keperluan pembelajaran. Silakan fork dan modifikasi sesuai kebutuhan Anda.

## Informasi Akademik

- **Mata Kuliah**: Pemrograman Web
- **Program Studi**: Pendidikan Teknik Informatika
- **Universitas**: Universitas Muhammadiyah Surakarta (UMS)

## Referensi

Proyek ini dikembangkan dengan mengacu pada tutorial:
- [Django Girls Tutorial](https://tutorial.djangogirls.org/en/) - Tutorial lengkap untuk membangun aplikasi web dengan Django

## Lisensi

Proyek ini dibuat untuk tujuan pembelajaran dan edukasi.

## Kontak

Untuk pertanyaan lebih lanjut, silakan hubungi melalui GitHub repository.

---

**Catatan**: Pastikan untuk tidak menggunakan `DEBUG = True` dan secret key yang sama saat deploy ke production.
