Crudu Denis I2301

Prima aplicație Docker

# Scop

Aceasta lucrare de laborator familiarizează cu elementele de bază ale containerizării și pregătește spațiul de lucru pentru următoarele lucrări de laborator.

# Sarcina

Instalarea Docker Desktop și verificarea funcționării acestuia.

Descărcam și instalam Docker Desktop.

![image](https://github.com/user-attachments/assets/e5f388a4-5a82-47a0-82b7-f5ff04c79407)

# Executare

Creaam un repozitoriu containers02 și il clonam pe computerul nostru.

![image](https://github.com/user-attachments/assets/bf39f21a-5565-4ddb-9800-9c1bffdfee83)

Creaam în directorul containers02 fișierul Dockerfile cu următorul conținut:

FROM debian:latest

COPY ./site/ /var/www/html/

CMD ["sh", "-c", "echo hello from $HOSTNAME"]

![image](https://github.com/user-attachments/assets/8ea84619-5166-4944-9737-5d8f0b3c4e1d)

În aceeași director de proiect creaam directorul site. În noul director creaan fișierul index.html cu conținut arbitrar.

![image](https://github.com/user-attachments/assets/05c65dc9-2d45-4aa5-bb15-5bc6ac2e9924)

# Pornire și testare

Deschidem terminalul în directorul containers02 și executam comanda:

docker build -t containers02 .

![image](https://github.com/user-attachments/assets/238f3167-54e6-4fb6-98a4-0f186fb09675)

Cât timp a durat crearea imaginii?

Crearea imaginii a durat 4.9 secunde.

Executam comanda pentru a porni containerul:

docker run --name containers03 containers02

![image](https://github.com/user-attachments/assets/e1cfa963-59a9-4cf0-a8d5-ec437a979d59)

Ce a fost afișat în consolă?

In consola a fost afisat mesajul: hello from 2F3566403ec4

Ștergem containerul și il pornim din nou, executând comenzile:

docker rm containers02

docker run -ti --name containers02 containers02 bash

![image](https://github.com/user-attachments/assets/b878ea9c-eab5-458a-9d01-da51a50d66e3)

În fereastra deschisă, executam comenzile:

cd /var/www/html/

ls -l

![image](https://github.com/user-attachments/assets/f05f4650-7727-4dcb-a947-77aff47b7357)

Ce este afișat pe ecran?

Pe ecran este afisat fisierul index.html cat si permisinulie acestuia si dimensiunea totală a fișierelor din director

Închidem fereastra cu comanda exit.

# Concluzii

Am învățat cum să instalăm și să configurăm Docker Desktop.

Am creat și rulat un container simplu bazat pe Debian.

Am folosit un Dockerfile pentru a copia fișiere într-un container.

Am verificat conținutul containerului și am confirmat că fișierele au fost copiate corect.

Această experiență ne oferă o bază solidă pentru lucrări ulterioare legate de containerizare.

# Bibliografie

[Docker Documentation](https://docs.docker.com/)


 
