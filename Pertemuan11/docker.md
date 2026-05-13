# CI/CD dengan Git -> Github Actions -> Docker hub -> EC2 AWS

1. Start Instance di AWS EC2
2. Patching OS -> sudo apt update && sudo apt upgrade
3. Install Docker di EC2 AWS https://docs.docker.com/
 - Uninstall Docker old version
  (sudo apt remove $(dpkg --get-selections docker.io docker-compose docker-compose-v2 docker-doc podman-docker containerd runc | cut -f1))
  - Set up Apt Docker
  - Install Docker Engine
  - Cek Docker -> systemctl status docker
  ![alt text]({97B8D7AC-8B3F-4123-A568-5BEEC9941BA2}.png)

4. Create Gudang / Repo di Docker Hub https://hub.docker.com/
 - Create akun dan login
 - create repo -> (hub->repo->New)
 - Create Tokens ( Klik Profile->Account Setting ->Security ->Access Tokens -> Generate new token)
 - Simpan token jangan sampai hilang
 ![alt text]({48063AD0-ABCE-4FE6-810D-111BEF2CCFF9}.png)

 5. Create Repo di Github
 - Membuat Repo baru dengan nama himafor_nim
 - BUat projek di Local 
 - Push ke Github
 ![alt text]({DFC69FCB-6D9E-4773-AB6B-A2D1FC4D8921}.png)

 6. Set Up Github Secret Variables
 - Klik Repo -> Settings -> Secrets and variables -> Actions -> New repository secret 
 - buat secret "DOCKERHUB_USERNAME" with your Docker Hub username
 - buat secret "DOCKERHUB_TOKEN" with your Docker Hub token
 - AWS_USERNAME isi username EC2 AWS kamu (ubuntu)
 - AWS_PRIVATE_KEY isi private key 
 - AWS_HOST isi public IP EC2 AWS kamu
 ![alt text]({0EDD3C6E-1D0B-46A8-B978-C34E71B87211}.png)

 7. Membuat Resep lingkungan Pengembangan (Dockerfile)
 - Buat file Dockerfile di root repo kamu 
 - Isi Dockerfile dengan kode berikut:

     <!-- OS -->
     From nginx:alpine
    
     <!-- PORt -->
     Expose 80

     <!-- Copy file Website html -->
     Copy index.html /usr/share/nginx/html
![alt text]({393659ED-7657-4351-A175-44B16E9D5C1B}.png)

8. Membuat CI/CD Workflow (Github Actions) di Repositori Github
 - Buat folder .github/workflows/
 - Buat File deploy.yml di folder .github/workflows/
 - Isi deploy.yml dengan kode berikut:
![alt text]({4164B4C1-E55E-4AA2-A5A7-594A004E6705}.png)

9. Pastikan semua tidak ada konflik termasuk permission
 - Stop dan disable nginx -> sudo systemctl stop nginx 
 - sudo systemctl disable nginx
 - add ubuntu to docker group -> sudo usermod -aG docker ubuntu
 - commit dan push -> dan cek di website

 ![alt text]({7A1E852B-D61F-4128-B017-AA0C3B154615}.png)