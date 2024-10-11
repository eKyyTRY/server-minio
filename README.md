Berikut langkah-langkah untuk menjalankan MinIO setelah meng-clone repository `https://github.com/ekyyy08/server-minio.git`:

## Langkah-langkah Menjalankan MinIO

1. **Clone Repository:**
   Pertama, clone repository tersebut ke komputer Anda.
   ```bash
   git clone https://github.com/ekyyy08/server-minio.git
   cd server-minio
   ```

2. **Setup Environment File (.env):**
   Buat file `.env` di dalam direktori project dengan memasukkan akses key dan secret key untuk MinIO. Berikut contoh isinya:
   ```bash
   MINIO_ROOT_USER=your-access-key
   MINIO_ROOT_PASSWORD=your-secret-key
   ```

   Gantilah `your-access-key` dan `your-secret-key` dengan kredensial yang ingin Anda gunakan.

3. **Jalankan Docker Compose (Jika Menggunakan Docker Compose):**
   Jika repository ini sudah memiliki file `docker-compose.yml`, Anda bisa menjalankan MinIO dengan Docker Compose. Pastikan Docker dan Docker Compose sudah terinstall.

   Untuk memulai MinIO, jalankan perintah berikut:
   ```bash
   docker-compose up -d
   ```

4. **Jalankan MinIO dengan Docker (Jika Tanpa Docker Compose):**
   Jika tidak menggunakan Docker Compose, Anda bisa langsung menjalankan MinIO dengan perintah Docker berikut:
   ```bash
   docker run -p 9000:9000 -p 9090:9090 \
       --name minio \
       -e "MINIO_ROOT_USER=your-access-key" \
       -e "MINIO_ROOT_PASSWORD=your-secret-key" \
       minio/minio server /data --console-address ":9090"
   ```

5. **Akses MinIO Console:**
   Setelah menjalankan perintah di atas, Anda bisa mengakses konsol MinIO melalui browser dengan membuka alamat:
   ```
   http://localhost:9090
   ```
   Masukkan akses key dan secret key yang Anda buat di langkah kedua.

6. **Buat Bucket:**
   Setelah login, Anda dapat membuat bucket untuk penyimpanan data di tab "Buckets". Sesuaikan konfigurasi bucket sesuai dengan kebutuhan Anda.

---

Jika ada file tambahan di dalam repository yang perlu dijalankan atau dikonfigurasi, pastikan untuk mengikuti dokumentasi yang tersedia di repository tersebut.
