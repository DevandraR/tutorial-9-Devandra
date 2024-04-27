# Tutorial Modul 9

Nama    : Devandra Reswara Arkananta 

1. What are the key differences between unary, server streaming, and bi-directional streaming RPC (Remote Procedure Call) methods, and in what scenarios would each be most suitable?

Jawab : Perbedaan utama antara metode RPC unary, server streaming, dan bi-directional streaming terletak pada cara komunikasi antara klien dan server. Unary RPC digunakan untuk panggilan satu kali, server streaming untuk mengirimkan banyak respons dari server ke klien, sementara bi-directional streaming memungkinkan pertukaran data dalam dua arah secara simultan. Untuk skenario yang memerlukan respons tunggal, gunakan unary RPC. Untuk mengirimkan data dalam jumlah besar dari server ke klien, gunakan server streaming. Sedangkan untuk aplikasi yang memerlukan komunikasi real-time dua arah, seperti aplikasi chatting, bi-directional streaming lebih cocok.

2. What are the potential security considerations involved in implementing a gRPC service in Rust, particularly regarding authentication, authorization, and data encryption?

Jawab : Dalam mengimplementasikan layanan gRPC di Rust, penting untuk memperhatikan keamanan. Ini termasuk autentikasi, otorisasi, dan enkripsi data. Perlu memastikan bahwa hanya klien yang berwenang yang dapat mengakses layanan, menggunakan metode autentikasi seperti token JWT atau OAuth. Penggunaan HTTPS untuk enkripsi data juga penting untuk melindungi informasi sensitif dari hacking.

3. What are the potential challenges or issues that may arise when handling bidirectional streaming in Rust gRPC, especially in scenarios like chat applications?

Jawab : Tantangan yang mungkin muncul saat menangani streaming dua arah dalam gRPC Rust adalah sinkronisasi pesan antara klien dan server serta manajemen koneksi yang efisien, terutama dalam aplikasi obrolan di mana banyak pengguna dapat terlibat dalam percakapan yang berbeda secara bersamaan.

4. What are the advantages and disadvantages of using the tokio_stream::wrappers::ReceiverStream for streaming responses in Rust gRPC services?

Jawab : Keuntungan menggunakan tokio_stream::wrappers::ReceiverStream untuk streaming respons dalam layanan gRPC Rust adalah kemudahannya dalam mengintegrasikan aliran data dengan framework tokio dan kesesuaian dengan pola pemrograman berbasis asinkronus. Namun, kelemahannya adalah ketergantungan pada ekosistem tokio dan kompleksitas penggunaan yang lebih tinggi dibandingkan dengan solusi lainnya.

5. In what ways could the Rust gRPC code be structured to facilitate code reuse and modularity, promoting maintainability and extensibility over time?

Jawab : Untuk meningkatkan kode yang dapat digunakan kembali dan modularitas dalam layanan gRPC Rust, strukturkan kode menjadi modul yang terpisah berdasarkan fungsionalitas, gunakan traits untuk menentukan kontrak antarmuka, dan gunakan dependensi eksternal dengan bijak untuk membagi fungsionalitas yang dapat digunakan kembali.

6. In the MyPaymentService implementation, what additional steps might be necessary to handle more complex payment processing logic?

Jawab : Dalam implementasi MyPaymentService, langkah tambahan yang mungkin diperlukan untuk menangani logika pemrosesan pembayaran yang lebih kompleks termasuk validasi transaksi, manajemen kegagalan transaksi, pelacakan riwayat pembayaran, dan integrasi dengan sistem third party seperti gateway pembayaran.

7. What impact does the adoption of gRPC as a communication protocol have on the overall architecture and design of distributed systems, particularly in terms of interoperability with other technologies and platforms?

Jawab : Adopsi gRPC sebagai protokol komunikasi dapat mempengaruhi arsitektur dan desain sistem terdistribusi dengan memperkenalkan pola komunikasi yang efisien, struktur pesan yang jelas, dan penggunaan aliran data dua arah. Ini dapat meningkatkan interoperability dengan teknologi dan platform lain yang mendukung gRPC.

8. What are the advantages and disadvantages of using HTTP/2, the underlying protocol for gRPC, compared to HTTP/1.1 or HTTP/1.1 with WebSocket for REST APIs?

Jawab : Keuntungan menggunakan HTTP/2, protokol yang mendasari gRPC, dibandingkan dengan HTTP/1.1 atau HTTP/1.1 dengan WebSocket untuk REST API termasuk multiplexing, kompresi header, dan server push, yang dapat meningkatkan kinerja dan efisiensi komunikasi. Namun, kelemahannya adalah kompleksitas implementasi dan dukungan yang mungkin terbatas di beberapa lingkungan.

9. How does the request-response model of REST APIs contrast with the bidirectional streaming capabilities of gRPC in terms of real-time communication and responsiveness?

Jawab : Model requeset-response dari REST API berbeda dengan kemampuan streaming dua arah gRPC dalam hal komunikasi real-time dan responsivitas. REST API cenderung lebih cocok untuk kasus penggunaan di mana respons tunggal sudah cukup, sementara gRPC lebih sesuai untuk aplikasi yang memerlukan komunikasi real-time atau transfer data besar dalam dua arah.

10. What are the implications of the schema-based approach of gRPC, using Protocol Buffers, compared to the more flexible, schema-less nature of JSON in REST API payloads?

Jawab : Implikasi dari pendekatan berbasis skema gRPC menggunakan Protocol Buffers dibandingkan dengan sifat yang lebih fleksibel dan tanpa skema JSON dalam muatan REST API termasuk validasi data yang ketat, kinerja yang lebih baik, dan pembacaan pesan yang lebih efisien. Namun, JSON lebih mudah dipahami oleh manusia dan lebih fleksibel dalam hal evolusi skema.