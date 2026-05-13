# Laporan UTS Administrasi Server

Krisna Adilla Fernada | 2388010044 | Informatika 6A

1. Tahap Provisioning & Security
- Membuat instance EC2 di region Singapore (ap-southeast-1) dengan nama uts_2388010026, tipe t2.micro/t3.micro, dan OS Ubuntu 22.04/24.04.
- Mengatur Key Pair, B. SPESIFIKASI INFRASTRUKTUR YANG DIMINTA
Region: Wajib menggunakan region Singapore (ap-southeast-1).
Compute: * Amazon EC2 Instance dengan OS Ubuntu 22.04 LTS atau 24.04 LTS.
Tipe Instance wajib t2.micro atau t3.micro (Free Tier Eligible).
Storage: 8 GB General Purpose SSD (gp2/gp3).
Security & Access:
Wajib menggunakan Key Pair (Tidak boleh menggunakan password/EIC).
Security Group: Hanya buka Port 80 (HTTP) dari Anywhere (0.0.0.0/0) dan Port 22 (SSH) hanya dari IP Publik Anda sendiri (My IP).
Web Server: Menggunakan Nginx (Bukan Apache).
Monitoring: Wajib mengaktifkan Detailed CloudWatch Monitoring dan membuat 1 buah Alarm jika penggunaan CPU menyentuh >80%.

C. INSTRUKSI PENGERJAAN (STEP-BY-STEP)
Tahap 1: Provisioning & Security (30 Poin)
- Buat instance EC2 sesuai spesifikasi di atas.
![alt text]({FCEB1B10-7460-46A1-9026-EFE64613072C}.png)
- Buat Elastic IP (EIP) dan Attach (hubungkan) EIP tersebut ke instance EC2 Anda secara permanen.
![alt text]({0076325B-2E3F-4207-BBED-6C98E376C4A7}.png)
- Konfigurasi Security Group dengan ketat sesuai aturan di atas.
![alt text]({2E1AE8C1-C73D-44EF-A9C8-D2DE0F7AA932}.png)

Tahap 2: Konfigurasi Web Server (30 Poin)
- Lakukan remote login (SSH) ke dalam server Anda menggunakan PuTTY atau Terminal.
![alt text]({516DB2B1-B3BC-43C0-ABB1-57F46D7FB19D}.png)
- Lakukan instalasi web server Nginx.
![alt text]({EFA0F1DA-214D-47EC-8659-2C64D85FE2D9}.png)
- Pastikan service Nginx berstatus running dan enabled.
![alt text]({FF614373-78AE-40B7-97C8-6F1AB77D7422}.png)
![alt text]({3AF10CA4-F493-4239-BE8E-646BFE421915}.png)

Tahap 3: Deployment Aplikasi Web CV (40 Poin)
- Siapkan source code Web CV / Portofolio Pribadi Anda (berbasis HTML/CSS/JS). Anda diizinkan menggunakan template gratis dari internet, namun wajib dimodifikasi dengan Data Diri Asli Anda (Foto, Riwayat Pendidikan, Skill, dll).
- Gunakan aplikasi SFTP (seperti FileZilla atau WinSCP) untuk memindahkan source code Web CV tersebut dari laptop Anda ke dalam server.
![alt text]({6ACFA6C0-0BAC-4849-AC0F-5C9535194D87}.png)
- Pindahkan source code tersebut ke Document Root Nginx/Apache (biasanya di /var/www/html).
![alt text]({2B40DD8D-ADB1-4CB9-B6B3-545A35EBFA21}.png)

PENTING: Atur Ownership dan Permissions (chown & chmod) pada folder website tersebut secara benar agar Nginx (www-data) bisa membacanya tanpa terkena Error 403 Forbidden.
Validasi Ujian: Pastikan di bagian paling bawah website CV Anda (footer) terdapat tulisan tebal: "Dideploy oleh: [Nama Lengkap Anda] - [NIM Anda]".storage 8 GB, serta Security Group (SSH: My IP, HTTP: 0.0.0.0/0).
1. Menjalankan instance hingga running, lalu membuat dan menghubungkan Elastic IP agar IP tetap.
![alt text]({FCEB1B10-7460-46A1-9026-EFE64613072C}.png)
![alt text]({0076325B-2E3F-4207-BBED-6C98E376C4A7}.png)
![alt text]({0076325B-2E3F-4207-BBED-6C98E376C4A7}.png)

3. Security Group Inbound Rules (menunjukkan Port 22 hanya diakses oleh My IP).
![alt text]({2E1AE8C1-C73D-44EF-A9C8-D2DE0F7AA932}.png)

4. Mengaktifkan dan menjalankan nginx
![alt text]({516DB2B1-B3BC-43C0-ABB1-57F46D7FB19D}.png)
![alt text]({EFA0F1DA-214D-47EC-8659-2C64D85FE2D9}.png)
![alt text]({FF614373-78AE-40B7-97C8-6F1AB77D7422}.png)
![alt text]({3AF10CA4-F493-4239-BE8E-646BFE421915}.png)

5. Deployment Aplikasi Web
- Setelah layanan Nginx berhasil dijalankan, dilakukan pengujian dengan mengakses alamat IP publik (Elastic IP) melalui browser.
- Website CV yang telah diunggah kemudian berhasil ditampilkan, menandakan bahwa proses deployment berjalan dengan baik dan server dapat diakses secara online.
- Dengan demikian, konfigurasi web server dan proses upload file website telah berhasil dilakukan tanpa kendala.
![alt text]({6ACFA6C0-0BAC-4849-AC0F-5C9535194D87}.png)
![alt text]({2B40DD8D-ADB1-4CB9-B6B3-545A35EBFA21}.png)