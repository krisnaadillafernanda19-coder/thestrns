# Deploy Web Apps Framework Next.js ke AWS 

1. Pastikan Web Apps berjalan di Local
 - install dependensi -> npm install
 - create db dan import sql
 - create file .env dan isi sesuaikan dengan db local
 - jalankan web apps -> npm run dev
 - akses web apps di browser `http://localhost:3000`
 - Testing Front Pastikan tampilan muncul dan tanpa Error
 - testing Back end http://localhost:3000/admin
    username: admin
    password: admin123
   ![alt text]({C44EBAE5-5608-41CC-9E9C-75509AC457ED}.png)
   ![alt text]({A56F6614-36F7-4270-A572-3CE1237EAA4C}.png)
   ![alt text]({34E45758-58BB-4DF9-A045-DADE8010C3A9}.png)
   ![alt text]({3AD699AD-F6FC-4C7B-A548-71C1C48EBD61}.png)
 - Create static File -> npm run build
 - Archive folder standalone -> zip -> klik kanan folder standalone -> send to -> compressed (zipped) folder