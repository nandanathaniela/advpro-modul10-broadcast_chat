# Module 10 - Asynchronous Programming - Broadcast Chat

> ##### Nanda Nathaniela Meizari - 2206824136

## 2.1 Experiment 2.1: Original code, and how it run
![2.1 Experiment 2.1: Original code, and how it run](assets/images/Experiment%202.1.jpg)

Untuk memulai server, saya menggunakan satu terminal dan memasukkan perintah `cargo run --bin server`. Kemudian, untuk menjalankan tiga klien, saya membuka tiga terminal terpisah dan di setiap terminal tersebut saya menjalankan perintah `cargo run --bin client`. Ketiga klien tersebut terhubung ke satu server yang sama, dan ketika saya mengetikkan sesuatu pada salah satu klien, pesan tersebut dikirim ke server. Setelah itu, server mengirimkan pesan tersebut ke semua klien, sehingga klien lain juga dapat melihat apa yang telah diketik