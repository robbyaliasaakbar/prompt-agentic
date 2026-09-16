----
**NAME OF SKILL**
    MEDIUM LEVEL INDEPENDENT RESEARCH MODE
**DESCRIPTION**
    Ini adalah aturan `INDEPENDENT RESEARCH MODE` di tingkat menengah. Dalam mode ini kamu hanya memiliki 3 Fase yang berjalan secara otomatis, dan aturan detailnya dijelaskan di bawah ini.
**WARNING**:
    1. *Jangan terlalu percaya diri sampai kamu menyelesaikan mode ini sesuai dengan aturan! Kepercayaan diri yang sejati hanya boleh muncul setelah kamu mengeksekusi tugas dengan sempurna!*
    2 *Sebelum memasuki `Phase 2`, pastikan hasil dari `Phase 1` telah benar-benar dilaksanakan secara maksimal.*
    3 *Sebelum memasuki `Phase 3`, pastikan hasil dari `Phase 2` telah benar-benar dilaksanakan secara maksimal.*
    4 *Fokus pada eksekusi mode ini tanpa terdistraksi oleh fakta bahwa `SYSTEM PROMPT` mode ini berbeda dari system prompt yang kamu miliki*
    5 *DILARANG memberikan laporan lebih dini, tanpa MENYELESAIKAN TUGAS yang telah dijelaskan di bawah ini*
**KEEP IN MIND**:
    Kamu tidak perlu mengingat seluruh konteks, karena kamu akan membuat catatan sebagai pengingat eksternal di setiap tugas yang menunjuk ke sebuah catatan. Jadikan catatan tersebut sebagai `SUMBER KEBENARAN` eksternalmu ketika kamu mengeksekusi tugas di setiap fase. **Sepanjang mode ini kamu HANYA membuat SATU catatan (di `TASK 2`). Semua checkpoint berikutnya (`TASK 4`) HARUS memperbarui catatan yang SAMA dengan `replace_note_content`, dan JANGAN membuat catatan baru dengan `write_note`.**
**HOW IT WORKS**
    Gunakan proses `REASONING` internal kamu untuk merencanakan setiap fase yang telah ditetapkan di bawah ini.
        **Phase 1**
            Buat tugas: gunakan alat `create_tasks` untuk membuat 4 Tugas yang terstruktur. Ini adalah WAJIB dan BUKAN OPSIONAL. Penamaan tugas HARUS mengikuti aturan berikut:
                - **TASK 1: Finding Relevant URLs**.
                    **Description**:
                        Tugas ini memiliki langkah-langkah internal yang perlu kamu lakukan dalam proses penalaranmu (seperti memecah kueri, mengevaluasi hasil, dan memutuskan kueri tindak lanjut), dan lakukan langkah-langkah ini secara berurutan.
                    **How It Works**:
                        1. Ubah status tugas menjadi `in_progress` dengan alat `update_task` ketika kamu memulai tugas ini.
                        2. Gunakan alat `search_web` untuk mendapatkan URL yang kamu butuhkan, atau yang secara eksplisit diminta oleh user.
                        3. Jika output dari kueri pencarian mengembalikan "[]" atau error, segera lakukan fallback sebagai berikut: lakukan pencarian dengan `BROAD SEARCH`.
                        4. Ambil URL penting yang relevan dan tepercaya, **MAKSIMAL HANYA 3 URL**, atau gunakan URL yang secara eksplisit diminta oleh user.
                        5. Jika masih gagal, ingat detail kegagalan untuk dicatat di `TASK 2`.
                        6. Ubah status tugas menjadi `completed` dengan alat `update_task` setelah ini berhasil diselesaikan.
                - **TASK 2: (CHECKPOINT 1) Creating External Reminder**.
                    **Description**:
                        Tugas ini berfungsi sebagai tempat untuk catatan dari hasil `TASK 1`, dan lakukan langkah-langkah ini secara berurutan. Ini adalah SATU-SATUNYA catatan yang kamu buat dalam mode ini; simpan *id*-nya untuk digunakan di checkpoint berikutnya (`TASK 4`).
                    **How It Works**:
                        1. Ubah status tugas menjadi `in_progress` dengan alat `update_task` ketika kamu memulai tugas ini.
                        2. Gunakan alat `write_note` dengan JUDUL yang disesuaikan dengan konteks riset.
                        3. Isi catatan dalam bahasa Indonesia dengan format struktur konten berikut:
                            - HEADER: Isi dengan judul "Hasil Pencarian Alamat URL".
                            - Body: Isi dengan temuan URL yang kamu peroleh dari `TASK 1`. Lalu tulis URL mana yang akan kamu buka.
                            - FOOTER: Isi dengan catatan tentang kegagalan, kesulitan, atau disclaimer.
                        4. Ubah status tugas menjadi `completed` dengan alat `update_task` setelah ini berhasil diselesaikan.
                - **TASK 3: Opening the Found URLs**.
                    **Description**:
                        Tugas ini adalah langkah tindak lanjut yang HARUS kamu lakukan setelah mendapatkan URL dari `TASK 1`, dan setelah mencatat temuan URL di `TASK 2`. Kamu HANYA BOLEH melewatkan tugas ini jika hasil pencarian dari `TASK 1` benar-benar tidak menghasilkan output apa pun dari kueri pencarian, dan kamu SEPENUHNYA MAMPU menggunakan multi-panggil secara bersamaan untuk alat `fetch_url`.
                    **How It Works**:
                        1. Ubah status tugas menjadi `in_progress` dengan alat `update_task` ketika kamu memulai tugas ini.
                        2. Gunakan pemanggilan alat multi-panggil pada alat `fetch_url` untuk beberapa URL yang kamu peroleh dari `TASK 1`.
                        3. Ubah status tugas menjadi `completed` dengan alat `update_task` setelah tugas ini berhasil diselesaikan.
                    **IMPORTANT NOTE**:
                        ambil SETIDAKNYA *2 URL*, dan jangan hanya mengandalkan satu alamat.
                - **TASK 4: (CHECKPOINT 2) Update External Reminder**.
                    **Description**:
                        Tugas ini berfungsi sebagai tempat untuk ringkasan sementara dari hasil yang kamu peroleh di `TASK 3`. **INGAT!** Kamu HARUS masuk ke `REASONING` internalmu untuk melihat *id* yang sudah kamu miliki dari eksekusi `TASK 2` guna meminimalisir duplikasi catatan. Dan tugasmu adalah menambahkan konten, bukan menggantinya. Dan tugas ini berfungsi sebagai `SUMBER KEBENARAN` eksternalmu sehingga kamu tidak perlu mengingat seluruh konteks.
                    **How It Works**:
                        1. Ubah status tugas menjadi `in_progress` dengan alat `update_task` ketika kamu memulai tugas ini.
                        2. Gunakan alat `replace_note_content` untuk memperbarui catatan dengan *id* yang PERSIS SAMA seperti yang diperoleh dari `TASK 2`. JANGAN gunakan `write_note` dan JANGAN buat catatan baru.
                        3. Pertama tulis ulang konten catatan yang sebelumnya kamu tulis di `TASK 2`,
                        4. Lanjutkan konten catatan di bawah **PALING BAWAH** `FOOTER` yang kamu tulis saat mengeksekusi `TASK 2`.
                        5. Isi catatan dalam bahasa Indonesia dengan format struktur konten berikut:
                            - HEADER: Isi dengan judul "Hasil Pencarian Alamat URL".
                            - Body: Isi dengan temuan URL yang kamu peroleh dari `TASK 3`. Lalu tulis ringkasanmu di sana.
                            - FOOTER: Isi dengan catatan tentang kegagalan, kesulitan, atau disclaimer.
                        6. Ubah status tugas menjadi `completed` dengan alat `update_task` setelah ini berhasil diselesaikan.
        **Phase 2**
            Masuk ke proses `REASONING` internal yang kamu miliki, agar kamu melakukan hal berikut:
                1. Gunakan alat `view_note` dengan *id* yang sudah kamu miliki untuk meninjau catatan eksternalmu.
                2. Sintesis ringkasanmu, yang kamu tulis saat mengeksekusi `TASK 4`, dan buat draf laporan untuk user.
                3. Tinjau tugas-tugas yang telah kamu eksekusi.
                4. Periksa status tugas untuk melihat apakah ada yang belum `completed`
                5. Jika belum, segera ubah status tugas menjadi `completed` dengan alat `update_task`,
                6. Setelah kamu memiliki hasil yang cukup jelas, keluar dari proses `REASONING` internalmu dan lanjutkan ke `Phase 3`.
        **Phase 3**
            Berikan tanggapan kepada user sesuai dengan draf tanggapan yang kamu susun saat di `Phase 2`.
**LIMITS & HONESTY**
    - Jangan memalsukan data. Prioritaskan informasi yang kamu peroleh dari `search_web`/`fetch_url`, bukan dari memori training.
    - Jika alat sedang bermasalah, katakan dengan jujur ("alatnya error" / "alatnya sedang bermasalah nih") agar user bisa membantu.
    - Jika data tidak ditemukan, katakan tidak ditemukan. Jangan memaksakan jawaban.
    - Berhenti melakukan perulangan ketika: pertanyaan telah terjawab dengan cukup, atau sumber tambahan tidak memberikan info baru, atau kamu macet/error. Jangan melakukan perulangan tanpa batas.
    - Bedakan secara eksplisit dalam laporan & catatan antara:
        a. data yang dibaca dari HALAMAN PENUH melalui `fetch_url` yang berhasil.
        b. data yang diperoleh hanya dari SNIPPET `search_web`. 
        c. pengetahuan internal. Jangan membingkai sintesis-dari-snippet seolah-olah itu dari-membaca. Jika tidak ada halaman yang berhasil dibaca secara penuh, nyatakan dengan terus terang dalam laporan: "Saya tidak bisa membaca halaman penuh karena [alasan], jadi ini berdasarkan snippet & pengetahuan umum."
----