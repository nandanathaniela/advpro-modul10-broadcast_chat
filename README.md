# Module 10 - Asynchronous Programming - Broadcast Chat

> ##### Nanda Nathaniela Meizari - 2206824136

## Experiment 2.1: Original code, and how it run
![Experiment 2.1: Original code, and how it run](assets/images/Experiment%202.1.jpg)

Untuk memulai server, saya menggunakan satu terminal dan memasukkan perintah `cargo run --bin server`. Kemudian, untuk menjalankan tiga klien, saya membuka tiga terminal terpisah dan di setiap terminal tersebut saya menjalankan perintah `cargo run --bin client`. Ketiga klien tersebut terhubung ke satu server yang sama, dan ketika saya mengetikkan sesuatu pada salah satu klien, pesan tersebut dikirim ke server. Setelah itu, server mengirimkan pesan tersebut ke semua klien, sehingga klien lain juga dapat melihat apa yang telah diketik

## Experiment 2.2: Modifying port
![Experiment 2.2: Modifying port](assets/images/Experiment%202.2.jpg)

Untuk menggunakan port 8080, perubahan harus dilakukan pada file `client.rs` dan `server.rs`. Pada file `client.rs`, modifikasi dilakukan pada pembuatan WebSocket client seperti berikut:

```rust
let (mut ws_stream, _) =
        ClientBuilder::from_uri(Uri::from_static("ws://127.0.0.1:8080"))
            .connect()
            .await?;
```

Sedangkan di file `server.rs`, penyesuaian dilakukan pada pembuatan TCP listener:

```rust
let listener = TcpListener::bind("127.0.0.1:8080").await?;
println!("listening on port 8080");
```

Penting untuk memastikan bahwa port yang digunakan oleh klien dan server adalah sama. Jika port yang digunakan berbeda, akan terjadi kesalahan di mana klien tidak dapat terhubung ke server yang mengakibatkan terminate program