# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

## Jawaban

1. DevOps adalah Sebuah budaya dalam perusahaan untuk mengautomasikan setiap tugas-tugas yang ada dan juga menghubungkan antara tim pengembang dan tim operasion agar pekerjaan lebih efesien.

2. Sebuah element-element yang terhubung satu sama lain yang memiliki tujuan yang sama.

3. Server adalah sebuah penyedia layanan di internet. Ketika sebuah client ingin mengkases halaman web atau mengirim email , mereka menggunakan penyedia layanan server tersebut. Contohnya ketika seorang user ingin mengakses layanan search engine seperti Google maka user tersebut akan melakukan pencarian di URL dengan mengetik Google.com .

4. Sebagai pengujian sebelum di deploy ke public.
   
5. Virtualisasi adalah sebuah cara untuk mengakses komputer lain  tanpa harus mengaksesnya secara langsung
   Container adalah Sesuatu cara untuk membungkus aplikasi agar bisa berjalan di berbagai platform.

6. Karena dengan container aplikasi dapat berjalan di berbagai platform , efesien dalam penggunaan sumber daya , dan mendukung microservice dengan menerapkan setiap service di container yang terpisah.

7. Sebuah alat untuk mengelola container.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy

(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

