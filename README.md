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

|Summary|Insiden keamanan terjadi pada jaringan internal sebuah perusahaan multimedia yang bergerak di bidang desain dan pemasaran digital. Layanan sempat terganggu selama kurang lebih dua jam akibat serangan Denial of Service (DoS) yang memanfaatkan lonjakan lalu lintas ICMP. Selama serangan berlangsung, jaringan tidak bisa diakses oleh pengguna internal karena banjir paket ICMP yang membebani sistem. Karyawan kesulitan mengakses sumber daya penting dan aktivitas operasional pun terhenti sementara. Hasil investigasi menunjukkan bahwa akar masalah berasal dari konfigurasi firewall yang kurang optimal. Tidak adanya pembatasan trafik ICMP dan proses verifikasi alamat IP membuka celah bagi pihak tidak bertanggung jawab untuk membanjiri jaringan. Tim manajemen insiden segera mengambil langkah dengan memblokir lalu lintas ICMP, menonaktifkan layanan yang tidak kritis, dan memulihkan layanan utama agar bisnis tetap berjalan. Setelah kondisi stabil, tim keamanan menerapkan aturan firewall baru, pengecekan IP sumber, pemantauan trafik jaringan, serta sistem IDS/IPS untuk mencegah insiden serupa terulang. Laporan ini disusun menggunakan pendekatan NIST Cybersecurity Framework (CSF) sebagai dasar dalam menganalisis insiden dan merancang peningkatan keamanan jaringan di masa depan.|
|Identify||
