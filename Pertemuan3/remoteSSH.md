# Remote SSH dari AWS EC2 Server

1. unduh dan Install Putty di https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html

![alt text]({7EF1210D-C4CF-43AF-A1F9-EB0FEEE01C6A}.png)

2. Konversi ekstensi Private Key dari .pem menjadi .ppk
    - Buka Putty Gen
    - Load Private Key .pem 
    - Klik Save Private Key menjadi ekstensi File .ppk
![alt text]({607502C3-33D9-4E12-A7BB-45FC303C79B5}.png)

3. Setting-Up Remote SSH dengan Putty
    - isi Ipv4 addres Public data berasal dari instance masing2
    - port SSH (22)
    - load private key .ppk di menu Connection->SSH->Auth->Credential
    - user dari instance masing-masing (ubuntu)

![alt text]({C998595E-BBEE-4151-9065-81CFE155A287}.png)

4. Setiap awal Remote kita lakukan Patching OS
 - sudo apt-get update && sudo apt-get upgrade 

5. coba lakukan instalasi Web Server 
 dalam keadaan Kosong
 ![alt text]({3E14BBFA-CFC3-44DF-91E4-5A7BC339C166}.png)
 instal salah satu web server 
 sudo apt install nginx 
 ![alt text]({B4A8D1D0-789D-47C3-9C2D-6CD0F65FFC4A}.png)