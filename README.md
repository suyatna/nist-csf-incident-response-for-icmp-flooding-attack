# NIST CSF incident response for ICMP flooding attack

## 📌 Table of contents

1. [Background](#background)
2. [Incident overview](#scenario)
3. [Incident response objectives](#objective)
4. [NIST CSF incident response approach](#nist)
5. [Incident analysis summary](#incidentanalysis)
6. [Reflection](#reflection)

---

## 🧠 Background <a name="background">

Studi kasus ini dibuat sebagai bagian portofolio cybersecurity yang fokus pada analisis insiden jaringan dan penulisan laporan keamanan. Skenario yang dipakai menceritakan sebuah organisasi multimedia yang mengalami gangguan layanan karena serangan Denial of Service (DoS). Sistem internal sempat tidak bisa diakses dalam waktu tertentu. Alur kejadian, dampak ke operasional, dan respons awal organisasi dijelaskan secara ringkas dan mudah dipahami.

Pembahasan ini mengacu pada pembelajaran saya di program Google Cybersecurity Professional Certificate, terutama pada course Connect and Protect: Networks and Network Security. Analisis dimulai dengan menggunakan NIST Cybersecurity Framework (CSF) sebagai kerangka kerja. Pendekatan ini membantu mengenali risiko, melindungi aset penting, meningkatkan deteksi, menyusun respons insiden, dan menyiapkan proses pemulihan. Studi kasus ini menunjukkan penerapan NIST CSF secara praktis sekaligus memberi gambaran kesiapan organisasi menghadapi ancaman serupa ke depan.

---

## 🚨 Incident overview <a name="scenario">

Saya berperan sebagai analis keamanan siber di sebuah perusahaan multimedia yang menyediakan layanan desain web, desain grafis, dan pemasaran media sosial untuk bisnis kecil. Aktivitas operasional sangat bergantung pada jaringan internal karena hampir semua layanan klien dikelola secara online.

Suatu hari terjadi gangguan jaringan besar selama kurang lebih dua jam. Jaringan internal berhenti merespons dan karyawan tidak bisa mengakses sistem serta resource penting. Pemantauan awal menunjukkan lonjakan trafik tidak wajar berupa banjir paket ICMP yang masuk terus-menerus.

Tim manajemen insiden langsung bergerak menstabilkan kondisi jaringan. Pemblokiran sementara paket ICMP dilakukan. Layanan nonkritis dimatikan. Proses pemulihan dimulai dengan memprioritaskan sistem yang paling penting supaya aktivitas bisnis bisa kembali berjalan.

Kondisi jaringan yang mulai stabil memberi kesempatan untuk investigasi lanjutan. Analisis menunjukkan konfigurasi firewall yang kurang tepat dimanfaatkan untuk mengirim ping ICMP dalam jumlah besar ke jaringan perusahaan. Celah ini memicu serangan Denial of Service (DoS) yang membuat kapasitas jaringan habis dan tidak mampu melayani trafik normal.

Langkah perbaikan kemudian diterapkan untuk mencegah kejadian serupa, yaitu:
- Aturan firewall diperbarui untuk membatasi laju paket ICMP
- Alamat IP sumber diverifikasi untuk mendeteksi spoofing
- Pemantauan jaringan diperkuat untuk mengenali pola trafik mencurigakan
- IDS/IPS diaktifkan untuk menyaring lalu lintas ICMP berdasarkan karakteristik serangan

Peristiwa ini menjadi dasar penugasan saya untuk menyusun rencana peningkatan keamanan jaringan dengan acuan NIST Cybersecurity Framework (CSF). Kerangka ini digunakan untuk memetakan risiko, melindungi aset penting, meningkatkan kemampuan deteksi, menyiapkan respons insiden, dan merancang proses pemulihan supaya organisasi lebih siap menghadapi ancaman keamanan di masa depan.

---

## 🎯 Incident response objectives <a name="objective">

Studi ini bertujuan untuk memahami insiden keamanan jaringan akibat serangan Denial of Service (DoS) sekaligus menyusun rencana penguatan keamanan jaringan yang lebih terarah dan berkelanjutan. Analisis dilakukan dengan mengacu pada NIST Cybersecurity Framework (CSF) agar pendekatan yang digunakan selaras dengan praktik keamanan yang umum diterapkan di industri.

Tujuan utama dari kegiatan ini meliputi:
- Mengidentifikasi sumber gangguan jaringan melalui pola lalu lintas ICMP yang tidak wajar
- Menentukan jenis serangan yang terjadi serta layanan dan sistem jaringan yang terdampak
- Menilai kelemahan konfigurasi keamanan, terutama pada firewall dan sistem pemantauan trafik
- Mengelompokkan langkah pengamanan berdasarkan fungsi Identify, Protect, Detect, Respond, dan Recover dalam NIST CSF
- Menyusun rekomendasi kontrol keamanan jaringan untuk mencegah serangan Denial of Service (DoS) serupa di kemudian hari
- Meningkatkan kesiapan organisasi dalam mendeteksi, menangani, dan memulihkan diri dari insiden jaringan

Tujuan ini menjadi landasan dalam penyusunan laporan insiden dan rencana peningkatan keamanan jaringan yang tidak hanya fokus pada penanganan sesaat, tetapi juga bersifat pencegahan dan berorientasi jangka panjang.

---

## 🧭 NIST CSF incident response approach <a name="nist">

### a. Identify

Hasil analisis menunjukkan insiden ini termasuk serangan Denial of Service (DoS) berbentuk ICMP flood. Serangan dilakukan dengan mengirim paket ICMP dalam jumlah besar secara berulang ke jaringan perusahaan. Beban jaringan naik drastis sampai tidak mampu menangani trafik normal. Layanan jaringan internal akhirnya berhenti merespons selama insiden berlangsung.

Dampak serangan langsung terasa di bagian penting jaringan. Firewall tidak memiliki aturan pembatasan trafik ICMP sehingga paket berbahaya bisa masuk tanpa hambatan. Infrastruktur jaringan internal ikut terbebani dan layanan utama yang dipakai karyawan tidak bisa diakses. Kondisi ini membuat gangguan ketersediaan layanan semakin parah.

Investigasi lanjutan menunjukkan trafik ICMP berasal dari sumber eksternal yang lolos melewati firewall tanpa verifikasi alamat IP dan tanpa mekanisme rate limiting. Sistem monitoring dan deteksi dini belum berjalan optimal sehingga pola trafik tidak normal terlambat dikenali. Insiden ini menghentikan aktivitas jaringan internal, menurunkan produktivitas karyawan, dan membuka risiko keamanan lebih besar jika celah yang sama tidak segera diperbaiki.

### b. Protect

Mencegah kejadian serupa perlu dilakukan dengan memperkuat perlindungan aset jaringan lewat kontrol keamanan yang lebih disiplin. Fokus utama dimulai pada pembaruan konfigurasi firewall, terutama pembatasan trafik ICMP yang masuk. Aturan ini membantu menahan lonjakan paket ICMP yang bisa mengganggu ketersediaan layanan jaringan.

Penguatan berikutnya dilakukan lewat verifikasi alamat IP sumber di firewall. Langkah ini menekan risiko spoofing yang sering muncul saat serangan berlangsung. Paket ICMP bisa disaring lebih awal sehingga hanya trafik dari sumber yang valid yang boleh masuk. Pengaturan kontrol akses jaringan yang lebih jelas ikut membatasi jenis trafik yang diizinkan ke jaringan internal.

Dokumentasi kebijakan keamanan jaringan menjadi bagian penting dalam pencegahan. Prosedur respons awal insiden perlu ditulis jelas dan mudah dipahami. Pelatihan rutin untuk tim teknis membantu mereka mengenali pola serangan, mengelola trafik jaringan, dan bergerak cepat saat muncul anomali. Kombinasi kontrol teknis dan kebijakan operasional yang konsisten membuat perlindungan jaringan jadi lebih kuat secara menyeluruh.

### c. Detect

Kemampuan deteksi insiden perlu ditingkatkan dengan pemantauan lalu lintas jaringan yang konsisten dan berjalan terus. Penggunaan tools monitoring jaringan jadi langkah awal yang penting untuk mengenali pola trafik tidak wajar, seperti lonjakan paket ICMP besar-besaran dari sumber eksternal. Pendekatan ini membantu tim keamanan menangkap tanda awal serangan sebelum berdampak ke layanan utama.

Penerapan IDS/IPS punya peran besar dalam proses deteksi. Sistem ini bekerja otomatis untuk mengenali dan menyaring trafik yang mencurigakan. Aturan dan signature yang rutin diperbarui membuat IDS/IPS lebih cepat mengenali pola serangan DoS berbasis ICMP dan langsung mengirim peringatan ke tim keamanan. Identifikasi insiden bisa dilakukan lebih cepat tanpa menunggu gangguan makin parah.

Pencatatan log terpusat perlu diterapkan di seluruh perangkat jaringan seperti firewall, router, dan server. Analisis log yang dilakukan secara rutin membantu menemukan anomali, melacak sumber serangan, dan menyediakan data saat investigasi lanjutan. Kombinasi monitoring real-time, IDS/IPS, dan pengelolaan log yang rapi membuat kemampuan deteksi insiden jaringan jauh lebih kuat dan bisa diandalkan.

### d. Respond

Organisasi perlu punya rencana respons insiden yang jelas saat menghadapi kejadian keamanan serupa ke depannya. Fokus awal dimulai dengan mengisolasi sumber serangan secepat mungkin, misalnya membatasi atau memblokir trafik ICMP mencurigakan lewat firewall supaya gangguan tidak menyebar ke sistem lain.

Tim keamanan menghentikan sementara layanan jaringan yang tidak kritis untuk menurunkan beban sistem dan menjaga layanan utama tetap berjalan. Analisis awal dilakukan dengan meninjau log jaringan, data IDS/IPS, dan hasil monitoring trafik untuk memahami pola serangan, sumber trafik berbahaya, serta celah keamanan yang dimanfaatkan.

Proses eskalasi melibatkan tim manajemen insiden dan pihak terkait supaya pengambilan keputusan bisa cepat dan terkoordinasi. Seluruh kejadian dicatat dengan jelas, termasuk waktu insiden, sistem yang terdampak, dan tindakan yang diambil. Dokumentasi ini menjadi bahan evaluasi dan perbaikan strategi keamanan ke depan.

### e. Recover

Ketika serangan Denial of Service (DoS) berhasil dikendalikan, organisasi masuk ke tahap pemulihan untuk mengembalikan sistem dan layanan jaringan ke kondisi normal. Fokus awal dimulai dengan memastikan seluruh aktivitas berbahaya sudah berhenti dan tidak ada lagi trafik ICMP mencurigakan yang masuk ke jaringan.

Layanan jaringan yang sempat dihentikan dinyalakan kembali secara bertahap, dimulai dari layanan yang paling krusial untuk operasional bisnis. Setiap tahap pemulihan disertai pemantauan performa jaringan dan kestabilan sistem supaya gangguan lanjutan atau serangan ulang bisa cepat terdeteksi. Konfigurasi firewall, IDS/IPS, dan sistem monitoring yang sudah diperbarui diuji ulang untuk memastikan proteksi berjalan sesuai kebijakan.

Tim keamanan melanjutkan evaluasi pasca insiden dengan meninjau log, dokumentasi respons, dan efektivitas langkah mitigasi yang diterapkan. Hasil evaluasi ini digunakan untuk menyempurnakan prosedur pemulihan, memperbarui rencana respons insiden, dan meningkatkan kesiapan organisasi menghadapi ancaman serupa.

Proses pemulihan yang dilakukan dengan belajar dari insiden membantu memperkuat ketahanan jaringan, menekan risiko gangguan berulang, dan menjaga layanan tetap berjalan setelah kejadian keamanan siber.

---

## 📊 Incident analysis summary <a name="#incidentanalysis">

Insiden keamanan terjadi pada jaringan internal perusahaan multimedia yang fokus di desain dan pemasaran digital. Layanan sempat lumpuh sekitar dua jam karena serangan Denial of Service (DoS) lewat lonjakan trafik ICMP. Jaringan internal tidak bisa diakses karena sistem kewalahan menerima banjir paket ICMP. Karyawan kesulitan membuka sistem penting dan aktivitas kerja terhenti sementara.

Hasil pengecekan menunjukkan masalah utama ada pada konfigurasi firewall yang belum optimal. Pembatasan trafik ICMP tidak diterapkan dan verifikasi alamat IP belum berjalan, sehingga jaringan mudah dibanjiri trafik berbahaya. Tim manajemen insiden langsung bertindak dengan memblokir trafik ICMP, mematikan layanan nonkritis, lalu memulihkan layanan utama supaya operasional bisa kembali jalan. Kondisi yang sudah stabil dimanfaatkan tim keamanan untuk memperbarui aturan firewall, melakukan validasi IP sumber, memperkuat pemantauan trafik, dan mengaktifkan IDS/IPS untuk mencegah kejadian serupa terulang.

---

## 💡 Reflection <a name="#reflection">

Serangan Denial of Service (DoS) ini nunjukin dampak besar kesalahan konfigurasi firewall ke stabilitas jaringan. Pembatasan dan validasi trafik ICMP tidak diterapkan, jadi jaringan gampang dibanjiri trafik berbahaya sampai layanan internal tidak jalan normal. Kontrol keamanan dasar yang terlewat sering jadi celah awal serangan jaringan.

Analisis pakai NIST Cybersecurity Framework membantu melihat keseimbangan antara pencegahan, deteksi, dan respons. Peran firewall dan IDS/IPS terasa penting, tapi kebutuhan pemantauan terus-menerus dan kesiapan tim juga kelihatan jelas. Respons cepat bisa menekan durasi gangguan, meski deteksi dini dan kesiapan awal masih perlu ditingkatkan.

Pengalaman ini mendorong pendekatan keamanan yang lebih proaktif. Audit rutin, pemantauan trafik yang lebih ketat, serta pembaruan kebijakan dan prosedur keamanan membantu memperkuat ketahanan jaringan. Pengalaman ini jadi dasar membangun strategi keamanan siber yang lebih matang dan berkelanjutan.

Studi kasus ini menegaskan pentingnya langkah proaktif. Aturan firewall yang lebih ketat, pemanfaatan IDS/IPS, dan pemantauan trafik secara konsisten punya peran besar menekan risiko serangan ke depan. Integrasi praktik ini ke strategi keamanan membantu jaringan lebih siap dan tim lebih sigap menghadapi insiden berikutnya.
