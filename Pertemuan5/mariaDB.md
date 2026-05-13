# Setting-up Database di AWS Ec2 menggunakan MariaDb

1. Aktifkan Instance AWs Ec2
2. Remote Instance Via Open SSH Powershell / putty 
3. Patching OS  (sudo apt-get update && sudo apt-get upgrade)
4. Install MariaDb (sudo apt install mariadb-server -y)
5. Cek Status MariaDb (systemctl status mariadb)
![alt text]({23863258-51D6-41F4-BFB1-4B543130DB26}.png)
6. Test Default Setting database server login
   sudo mysql -u root -p
![alt text]({99697896-273B-4892-AC8C-88ADFC9BEEC2}.png)
7. Hardening Database Server sudo mysql_secure_installation
    - Change the password for the root user = Y
    - Remove anonymous users = Y
    - Disallow root login remotely = Y
    - Remove test database and access to it = Y
    - Reload privilege tables = Y
![alt text]({6D432A20-43FB-4445-B276-3F6ED13B6763}.png)
8. Create DB untuk Website Company Profile
 - Login sebagai root
 - Create DB nama dbcompro_NIM => CREATE DATABASE dbcompro_nim_NIM;
 ![alt text]({25EAA1EA-FA54-4F49-A0D0-B765C1C294AF}.png)
  - Create User dengan nama = usrcompro_NIM dan password = [PASSWORD] => CREATE USER 'usrcompro_NIM'@'localhost' IDENTIFIED BY '[PASSWORD]';
  ![alt text]({9F22B54B-C44B-4E25-9247-93679BE3F295}.png)
  - Grant user akses ke DB yang baru dibuat => GRANT ALL PRIVILEGES ON dbcompro_nim_NIM.* TO 'usrcompro_NIM'@'localhost';

  - Flush privileges => FLUSH PRIVILEGES;
  - exit;
  - login sebagai usrcompro_NIM dan cek apakah bisa akses ke DB yang baru dibuat
![alt text]({D3316A3A-7E14-4DB8-A29D-CDF660C0DD4E}.png)