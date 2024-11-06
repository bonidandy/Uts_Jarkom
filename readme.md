Bonifasius Dandy Krisnanda
20210801002
Teknik Informatika

#Essay
1. Jelaskan menurut anda apa itu Routing Static?
jawab: 
Menurut saya, Routing static adalah metode pengaturan jalur data di jaringan yang diatur manual oleh admin. Jalurnya tetap dan tidak otomatis berubah walaupun ada perubahan di jaringan. Routing Static cocok untuk jaringan kecil yang sederhana karena lebih mudah diatur dan tidak membutuhkan banyak sumber daya, tetapi jika ada perubahan, maka admin harus mengatur ulang rutenya secara manual.

2. Jelaskan menurut anda apa itu Routing Dynamic? 
Jawab:
Menurut saya, routing dinamis itu adalah cara mengatur jalur data di jaringan yang bisa berubah otomatis sesuai kondisi jaringan. Jadi, jika ada perubahan seperti perangkat baru atau jalur yang putus, router dengan routing dinamis bisa menyesuaikan sendiri tanpa perlu diatur manual oleh admin. Router ini pakai protokol khusus yang otomatis menghitung rute terbaik untuk mengirim data, jadi lebih fleksibel untuk jaringan besar yang sering berubah.

3. Jelaskan menurut anda apa itu Firewall?
Jawab:
Menurut saya, firewall itu seperti pengaman jaringan yang memfilter data yang keluar masuk. Jadi, fungsinya untuk menjaga jaringan dari ancaman atau akses yang nggak diinginkan. Firewall akan memeriksa tiap data yang masuk atau keluar dan menentukan apakah data itu aman atau nggak berdasarkan aturan yang sudah ditentukan. Kalau dianggap berbahaya, firewall akan blokir aksesnya. Dengan kata lain, firewall ini seperti “satpam” yang ngontrol siapa aja yang boleh keluar masuk ke dalam jaringan supaya jaringan tetap aman dari serangan.

4. Jelaskan menurut anda apa itu NAT?
Jawab:
Menurut saya, NAT (Network Address Translation) itu teknologi yang digunakan untuk "menerjemahkan" alamat IP di dalam jaringan lokal ke alamat IP publik yang dipakai di internet. Jadi, misalnya di rumah kita punya beberapa perangkat yang terhubung ke internet lewat satu router, NAT memungkinkan semua perangkat itu bisa pakai satu alamat IP publik yang sama saat akses internet. Tujuannya biar hemat IP dan juga lebih aman, karena perangkat-perangkat di dalam jaringan tidak langsung kelihatan oleh internet, hanya alamat IP publik dari router saja yang terlihat.

#Topologi
![Topologi](uts_jarkom.drawio.svg)

#Konfigurasi

1. Konfigurasi router KJ :
- Interface LAN (connects to KJ local network)
  IP Address: 192.168.1.1/24

- Interface WAN1 (connects to CR)
  IP Address: 10.0.0.1/30
  Network: 10.0.0.0/30

- Interface WAN2 (connects to KHI)
  IP Address: 10.0.0.5/30
  Network: 10.0.0.4/30

Static Routes:
- Route to CR Network (192.168.2.0/24)
  Next hop: 10.0.0.2

- Route to KHI Network (192.168.3.0/24)
  Next hop: 10.0.0.6

2. Konfigurasi router CR:
- Interface LAN (connects to CR local network)
  IP Address: 192.168.2.1/24

- Interface WAN (connects to KJ)
  IP Address: 10.0.0.2/30
  Network: 10.0.0.0/30

Static Routes:
- Route to KJ Network (192.168.1.0/24)
  Next hop: 10.0.0.1

- Route to KHI Network (192.168.3.0/24)
  Next hop: 10.0.0.1

3. Konfigurasi router KHI:
- Interface LAN (connects to KHI local network)
  IP Address: 192.168.3.1/24

- Interface WAN (connects to KJ)
  IP Address: 10.0.0.6/30
  Network: 10.0.0.4/30

Static Routes:
- Route to KJ Network (192.168.1.0/24)
  Next hop: 10.0.0.5

- Route to CR Network (192.168.2.0/24)
  Next hop: 10.0.0.5


