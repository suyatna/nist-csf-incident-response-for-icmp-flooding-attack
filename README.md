# NIST CSF incident response

## 📑 Table of contents

1. [Introduction](#introduction)
2. [Incident scenario](#scenario)
3. [Objective](#objective)
4. [Incident report analysis](#report)
5. [Conclusion](#conclusion)

---

## 👋 Introduction <a name="introduction">

Studi ini disusun sebagai bagian dari latihan cybersecurity yang berfokus pada analisis insiden jaringan dan penulisan laporan keamanan siber. Skenario yang digunakan menggambarkan sebuah organisasi multimedia yang mengalami gangguan layanan akibat serangan denial of service, sehingga sistem internal tidak dapat diakses dalam waktu tertentu. Alur kejadian, dampak terhadap operasional, dan respons awal organisasi dijabarkan secara runtut agar mudah dipahami.

Pembahasan mengacu pada materi dari program Google Cybersecurity Professional Certificate dengan pendekatan NIST Cybersecurity Framework (CSF). Kerangka ini digunakan untuk membantu mengenali risiko, melindungi aset penting, mendeteksi insiden lebih cepat, menyusun respons yang tepat, dan merencanakan proses pemulihan. Studi ini bertujuan menunjukkan bagaimana NIST CSF dapat diterapkan secara praktis untuk mengelola insiden jaringan dan meningkatkan kesiapan organisasi menghadapi ancaman serupa di masa depan.

---

## 💭 Incident scenario <a name="scenario">

Saya berperan sebagai analis keamanan siber di sebuah perusahaan multimedia yang menyediakan layanan desain web, desain grafis, dan pemasaran media sosial untuk bisnis kecil. Seluruh aktivitas operasional sangat bergantung pada jaringan internal karena hampir semua layanan klien dikelola secara online.

Suatu hari terjadi gangguan jaringan besar yang berlangsung sekitar dua jam. Selama periode ini, jaringan internal berhenti merespons dan karyawan tidak bisa mengakses sistem serta sumber daya penting. Pemantauan awal menunjukkan adanya lonjakan trafik tidak wajar berupa banjir paket ICMP yang masuk tanpa henti.

Tim manajemen insiden segera bergerak untuk menstabilkan jaringan. Paket ICMP diblokir sementara, layanan nonkritis dimatikan, dan pemulihan difokuskan pada sistem yang paling penting agar aktivitas bisnis bisa berjalan kembali.

Kondisi jaringan yang mulai membaik memberi ruang bagi tim keamanan untuk melakukan investigasi lanjutan. Analisis menunjukkan bahwa firewall yang kurang tepat konfigurasi dimanfaatkan untuk mengirim ping ICMP dalam jumlah besar ke jaringan perusahaan. Celah ini memicu serangan Denial of Service (DoS) yang membuat jaringan kehabisan kapasitas dan tidak mampu melayani trafik normal.

Langkah perbaikan kemudian diterapkan untuk mencegah kejadian serupa,yaitu berupa:
- Aturan firewall diperbarui untuk membatasi laju paket ICMP
- Alamat IP sumber diverifikasi untuk mendeteksi spoofing
- Pemantauan jaringan diperkuat untuk mengenali pola trafik mencurigakan
- IDS/IPS diaktifkan untuk menyaring lalu lintas ICMP berdasarkan ciri serangan.

Peristiwa ini menjadi dasar penugasan saya untuk menyusun rencana peningkatan keamanan jaringan dengan mengacu pada NIST Cybersecurity Framework (CSF). Kerangka ini digunakan untuk memetakan risiko, melindungi aset penting, meningkatkan deteksi, menyiapkan respons insiden, dan merancang proses pemulihan agar organisasi lebih siap menghadapi ancaman keamanan di masa depan.

---

## 🎯 Objective <a name="objective">

Studi ini bertujuan untuk memahami insiden keamanan jaringan akibat serangan Denial of Service (DoS) sekaligus menyusun rencana penguatan keamanan jaringan yang lebih terarah dan berkelanjutan. Analisis dilakukan dengan mengacu pada NIST Cybersecurity Framework (CSF) agar pendekatan yang digunakan selaras dengan praktik keamanan yang umum diterapkan di industri.

Tujuan utama dari kegiatan ini meliputi:
- Mengidentifikasi sumber gangguan jaringan melalui pola lalu lintas ICMP yang tidak wajar
- Menentukan jenis serangan yang terjadi serta layanan dan sistem jaringan yang terdampak
- Menilai kelemahan konfigurasi keamanan, terutama pada firewall dan sistem pemantauan trafik
- Mengelompokkan langkah pengamanan berdasarkan fungsi Identify, Protect, Detect, Respond, dan Recover dalam NIST CSF
- Menyusun rekomendasi kontrol keamanan jaringan untuk mencegah serangan DoS serupa di kemudian hari
- Meningkatkan kesiapan organisasi dalam mendeteksi, menangani, dan memulihkan diri dari insiden jaringan

Tujuan ini menjadi landasan dalam penyusunan laporan insiden dan rencana peningkatan keamanan jaringan yang tidak hanya fokus pada penanganan sesaat, tetapi juga bersifat pencegahan dan berorientasi jangka panjang.

---

## 📋 Incident report analysis <a name="report">

### Summary

Insiden keamanan terjadi pada jaringan internal sebuah perusahaan multimedia yang bergerak di bidang desain dan pemasaran digital. Layanan sempat terganggu selama kurang lebih dua jam akibat serangan Denial of Service (DoS) yang memanfaatkan lonjakan lalu lintas ICMP. Selama serangan berlangsung, jaringan tidak bisa diakses oleh pengguna internal karena banjir paket ICMP yang membebani sistem. Karyawan kesulitan mengakses sumber daya penting dan aktivitas operasional pun terhenti sementara.

Hasil investigasi menunjukkan bahwa akar masalah berasal dari konfigurasi firewall yang kurang optimal. Tidak adanya pembatasan trafik ICMP dan proses verifikasi alamat IP membuka celah bagi pihak tidak bertanggung jawab untuk membanjiri jaringan. Tim manajemen insiden segera mengambil langkah dengan memblokir lalu lintas ICMP, menonaktifkan layanan yang tidak kritis, dan memulihkan layanan utama agar bisnis tetap berjalan. Setelah kondisi stabil, tim keamanan menerapkan aturan firewall baru, pengecekan IP sumber, pemantauan trafik jaringan, serta sistem IDS/IPS untuk mencegah insiden serupa terulang.

Laporan ini disusun menggunakan pendekatan NIST Cybersecurity Framework (CSF) sebagai dasar dalam menganalisis insiden dan merancang peningkatan keamanan jaringan di masa depan.

### Identify

Hasil analisis menunjukkan bahwa insiden ini merupakan serangan Denial of Service (DoS) dalam bentuk ICMP flood. Serangan dilakukan dengan mengirim paket ICMP secara masif dan berulang ke jaringan perusahaan. Beban jaringan meningkat drastis hingga tidak mampu memproses trafik normal. Layanan jaringan internal pun berhenti merespons dan tidak bisa digunakan selama insiden berlangsung.

Dampak serangan terasa langsung pada beberapa bagian penting jaringan. Firewall tidak memiliki aturan pembatasan lalu lintas ICMP sehingga trafik berbahaya dapat masuk tanpa hambatan. Infrastruktur jaringan internal ikut terbebani dan layanan penting yang digunakan karyawan menjadi tidak tersedia. Kondisi ini memperparah gangguan terhadap ketersediaan layanan.

Hasil investigasi lanjutan menunjukkan bahwa trafik ICMP berasal dari sumber eksternal yang melewati firewall tanpa proses verifikasi alamat IP atau pengaturan rate limiting. Tidak adanya sistem pemantauan dan deteksi dini membuat pola trafik tidak normal terlambat teridentifikasi. Insiden ini menyebabkan terhentinya aktivitas jaringan internal, menurunnya produktivitas karyawan, serta meningkatkan risiko keamanan jika celah yang sama tidak segera diperbaiki.

### Protect

Mencegah kejadian serupa, organisasi perlu memperkuat perlindungan aset jaringan dengan kontrol keamanan yang lebih disiplin. Fokus utama dimulai dari pembaruan konfigurasi firewall, khususnya dengan menerapkan pembatasan lalu lintas ICMP yang masuk. Aturan ini membantu menahan lonjakan paket ICMP yang berpotensi mengganggu ketersediaan layanan jaringan.

Penguatan juga perlu dilakukan melalui verifikasi alamat IP sumber pada firewall. Langkah ini mengurangi risiko pemalsuan alamat IP yang sering dimanfaatkan saat serangan berlangsung. Paket ICMP yang masuk dapat disaring lebih awal sehingga hanya trafik dari sumber yang valid yang diizinkan. Pengaturan kontrol akses jaringan yang lebih jelas turut membantu membatasi jenis lalu lintas yang boleh masuk ke jaringan internal.

Dokumentasi kebijakan keamanan jaringan menjadi bagian penting dari upaya pencegahan. Prosedur respons awal terhadap insiden perlu ditulis dengan jelas dan mudah diikuti. Pelatihan rutin bagi tim teknis membantu memastikan mereka mampu mengenali pola serangan, mengelola trafik jaringan, dan bertindak cepat saat muncul anomali. Kombinasi antara kontrol teknis dan kebijakan operasional yang konsisten akan memperkuat perlindungan jaringan secara menyeluruh.

### Detect

Memperbaiki kemampuan deteksi insiden di masa yang akan datang, organisasi perlu memantau lalu lintas jaringan secara konsisten dan berkelanjutan. Penggunaan perangkat lunak pemantauan jaringan menjadi langkah awal yang penting, terutama untuk mengenali pola trafik yang tidak wajar, seperti lonjakan paket ICMP dari sumber eksternal dalam jumlah besar. Pendekatan ini membantu tim keamanan menangkap tanda awal serangan sebelum gangguan meluas ke layanan utama.

Penerapan sistem IDS/IPS juga berperan besar dalam proses deteksi. Sistem ini bekerja secara otomatis untuk mengenali dan menyaring lalu lintas yang mencurigakan. Aturan dan signature yang diperbarui secara rutin memungkinkan IDS/IPS mengenali pola serangan DoS berbasis ICMP dan mengirimkan peringatan lebih cepat kepada tim keamanan. Proses identifikasi insiden pun dapat dilakukan tanpa menunggu gangguan menjadi lebih parah.

Pencatatan log secara terpusat perlu diterapkan pada seluruh perangkat jaringan, termasuk firewall, router, dan server. Analisis log yang dilakukan secara rutin membantu menemukan anomali, menelusuri sumber serangan, dan menyediakan data yang dibutuhkan saat investigasi lanjutan. Kombinasi pemantauan real-time, IDS/IPS, dan pengelolaan log yang rapi akan membuat kemampuan deteksi insiden jaringan menjadi jauh lebih kuat dan andal.

### Respond

Menghadapi insiden keamanan siber serupa di masa mendatang, organisasi perlu memiliki rencana respons insiden yang jelas dan terstruktur agar dampak serangan dapat ditekan. Fokus awal diarahkan pada isolasi sumber serangan secepat mungkin, seperti membatasi atau memblokir lalu lintas ICMP yang mencurigakan melalui firewall agar gangguan tidak menyebar ke sistem lain.

Tim keamanan menghentikan sementara layanan jaringan yang tidak bersifat kritis untuk mengurangi beban sistem dan menjaga layanan utama tetap tersedia. Analisis awal dilakukan dengan meninjau log jaringan, data dari IDS/IPS, serta hasil pemantauan trafik guna memahami pola serangan, sumber trafik berbahaya, dan celah keamanan yang dimanfaatkan.

Proses eskalasi dijalankan dengan melibatkan tim manajemen insiden dan pemangku kepentingan terkait agar pengambilan keputusan berjalan cepat dan terkoordinasi. Seluruh kejadian didokumentasikan secara menyeluruh, mencakup waktu insiden, sistem terdampak, serta tindakan yang diambil. Dokumentasi ini menjadi dasar evaluasi dan perbaikan strategi keamanan di masa mendatang.

### Recover

Ketika serangan DoS berhasil dikendalikan, organisasi menjalankan proses pemulihan untuk mengembalikan sistem dan layanan jaringan ke kondisi normal secara aman dan terukur. Fokus awal diarahkan pada memastikan seluruh aktivitas berbahaya sudah benar-benar berhenti dan tidak ada lagi lalu lintas ICMP mencurigakan yang masuk ke jaringan.

Layanan jaringan yang sebelumnya dihentikan dipulihkan secara bertahap, dimulai dari layanan yang paling penting bagi operasional bisnis. Setiap tahap pemulihan disertai pemantauan performa jaringan dan stabilitas sistem agar potensi gangguan lanjutan atau serangan ulang dapat segera terdeteksi. Konfigurasi firewall, IDS/IPS, dan sistem monitoring yang telah diperbarui diuji kembali untuk memastikan perlindungan berjalan sesuai kebijakan keamanan.

Tim keamanan melanjutkan dengan evaluasi pasca-insiden melalui peninjauan log, dokumentasi respons, serta efektivitas langkah mitigasi yang diterapkan. Temuan dari evaluasi ini dimanfaatkan untuk menyempurnakan prosedur pemulihan, memperbarui rencana respons insiden, dan meningkatkan kesiapan organisasi menghadapi ancaman serupa.

Proses pemulihan yang terstruktur dan berbasis pembelajaran membantu organisasi memperkuat ketahanan jaringan, menekan risiko gangguan berulang, dan menjaga kontinuitas layanan setelah insiden keamanan siber terjadi.

### Reflection

Serangan DoS yang terjadi memperlihatkan bahwa kesalahan konfigurasi firewall bisa berdampak besar pada stabilitas jaringan organisasi. Ketiadaan pembatasan dan validasi lalu lintas ICMP memberi celah bagi aktor jahat untuk membanjiri jaringan hingga layanan internal tidak lagi berjalan normal. Kondisi ini menunjukkan bahwa kontrol keamanan dasar yang diabaikan sering kali menjadi pintu masuk utama serangan jaringan.

Analisis menggunakan NIST Cybersecurity Framework membantu organisasi melihat kebutuhan keseimbangan antara pencegahan, deteksi, dan respons. Insiden ini menegaskan peran penting perlindungan teknis seperti firewall dan IDS/IPS, sekaligus menyoroti perlunya pemantauan berkelanjutan dan kesiapan tim saat menghadapi insiden. Respons yang cepat mampu menekan durasi gangguan, meski kesiapan awal dan deteksi dini masih perlu diperkuat.

Pembelajaran dari insiden ini mendorong organisasi untuk beralih ke pendekatan keamanan yang lebih proaktif. Praktik audit rutin, pemantauan lalu lintas yang lebih ketat, serta pembaruan kebijakan dan prosedur keamanan membantu meningkatkan ketahanan jaringan. Pengalaman ini menjadi dasar penting dalam membangun strategi keamanan siber yang lebih matang dan berkelanjutan.

---

## 🏁 Conclusion <a name="conclusion">

Insiden Denial of Service (DoS) yang dibahas pada studi kasus ini memperlihatkan dampak besar dari celah konfigurasi jaringan terhadap ketersediaan layanan organisasi. Lonjakan paket ICMP yang tidak terkendali membuat jaringan internal berhenti merespons dan mengganggu aktivitas bisnis selama beberapa jam. Situasi ini menunjukkan bahwa lemahnya kontrol keamanan jaringan, khususnya pada firewall dan sistem pemantauan, sering menjadi titik masuk serangan.

Penerapan NIST Cybersecurity Framework membantu proses analisis berjalan lebih terstruktur, mulai dari mengenali risiko, melindungi aset, mendeteksi ancaman, merespons insiden, hingga memulihkan sistem. Pendekatan ini memudahkan organisasi memahami penyebab utama insiden, menilai efektivitas kontrol keamanan yang sudah ada, serta menyusun langkah perbaikan yang lebih fokus dan berkelanjutan.

Studi kasus ini menegaskan pentingnya pendekatan keamanan yang bersifat proaktif. Aturan firewall yang lebih ketat, pemanfaatan IDS/IPS, serta pemantauan lalu lintas jaringan secara terus-menerus berperan besar dalam mencegah dan mengurangi dampak serangan di masa depan. Integrasi praktik tersebut ke dalam strategi keamanan organisasi membantu meningkatkan ketahanan jaringan dan kesiapan tim menghadapi insiden keamanan siber berikutnya.
