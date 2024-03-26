# Packet Tracer - Konfigurasi VLAN

## Tabel Pengalamatan

## Tujuan
### Bagian 1: Verifikasi Konfigurasi VLAN Default
### Bagian 2: Konfigurasikan VLAN
### Bagian 3: Tetapkan VLAN ke Port

## Latar belakang
### VLAN berguna dalam administrasi grup logis, memungkinkan anggota grup dengan mudah dipindahkan, diubah, atau ditambahkan. Kegiatan ini berfokus pada pembuatan dan penamaan VLAN, serta penetapan port akses ke VLAN tertentu.

## Bagian 1: Lihat Konfigurasi VLAN Default
### Langkah 1: Tampilkan VLAN saat ini.
#### Di S1, keluarkan perintah yang menampilkan semua VLAN yang dikonfigurasi. Secara default, semua antarmuka ditetapkan ke VLAN 1.

### Langkah 2: Verifikasi konektivitas antar PC di jaringan yang sama.
#### Perhatikan bahwa setiap PC dapat melakukan ping ke PC lain yang berbagi subnet yang sama.
#### · PC1 dapat melakukan ping ke PC4
#### · PC2 dapat melakukan ping ke PC5
#### · PC3 dapat melakukan ping ke PC6
#### Ping ke host di jaringan lain gagal.

## Bagian 2: Konfigurasikan VLAN
### Langkah 1: Buat dan beri nama VLAN di S1.
#### A. Buat VLAN berikut. Nama peka huruf besar-kecil dan harus sama persis dengan persyaratan:
#### · VLAN 10: Fakultas/Staf
#### S1#(konfigurasi)#vlan 10
#### S1#(config-vlan)# nama Faculty/Staff

#### B. Buat VLAN yang tersisa.
#### · VLAN 20: Students
#### · VLAN 30: Guest(Default)
#### · VLAN 99: Management&Native
#### · VLAN 150: VOICE

### Langkah 2: Verifikasi konfigurasi VLAN.
#### Perintah mana yang hanya akan menampilkan nama VLAN, status, dan port terkait pada sebuah switch?

### Langkah 3: Buat VLAN di S2 dan S3.
#### Gunakan perintah yang sama dari Langkah 1 untuk membuat dan memberi nama VLAN yang sama pada S2 dan S3.

### Langkah 4: Verifikasi konfigurasi VLAN.

## Bagian 3: Tetapkan VLAN ke Port
### Langkah 1: Tetapkan VLAN ke port aktif di S2.
#### A. Konfigurasikan antarmuka sebagai port akses dan tetapkan VLAN sebagai berikut:
#### · VLAN 10: FastEthernet 0/11
#### S2(config)# interface f0/11
#### S2(config-if)# switchport mode access
#### S2(config-if)# switchport access vlan 10

#### B. Tetapkan port yang tersisa ke VLAN yang sesuai.
#### · VLAN 20: FastEthernet 0/18
#### · VLAN 30: FastEthernet 0/6

### Langkah 2: Tetapkan VLAN ke port aktif di S3.
#### S3 menggunakan penetapan port akses VLAN yang sama dengan S2. Konfigurasikan antarmuka sebagai port akses dan tetapkan VLAN sebagai berikut:
#### · VLAN 10: FastEthernet 0/11
#### · VLAN 20: FastEthernet 0/18
#### · VLAN 30: FastEthernet 0/6

### Langkah 3: Tetapkan VOICE VLAN ke FastEthernet 0/11 di S3.
#### Seperti yang ditunjukkan pada topologi, antarmuka S3 FastEthernet 0/11 terhubung ke Cisco IP Phone dan PC4. Telepon IP berisi saklar tiga port 10/100 terintegrasi. Satu port di ponsel diberi label Switch dan terhubung ke F0/4. Port lain di ponsel diberi label PC dan terhubung ke PC4. Telepon IP juga memiliki port internal yang menghubungkan ke fungsi telepon IP.

#### Antarmuka S3 F0/11 harus dikonfigurasi untuk mendukung lalu lintas pengguna ke PC4 menggunakan VLAN 10 dan lalu lintas suara ke telepon IP menggunakan VLAN 150. Antarmuka juga harus mengaktifkan QoS dan mempercayai nilai Class of Service (CoS) yang ditetapkan oleh telepon IP . Lalu lintas suara IP memerlukan jumlah throughput minimum untuk mendukung kualitas komunikasi suara yang dapat diterima. Perintah ini membantu switchport untuk menyediakan jumlah throughput minimum ini.
#### S3(config)# interface f0/11
#### S3(config-if)# mls qos trust cos
#### S3(config-if)# switchport voice vlan 150

### Langkah 4: Verifikasi hilangnya konektivitas.
#### Sebelumnya, PC yang berbagi jaringan yang sama dapat berhasil melakukan ping satu sama lain.

#### Pelajari output dari perintah berikut di S2 dan jawab pertanyaan berikut berdasarkan pengetahuan Anda tentang komunikasi antar VLAN. Perhatikan baik-baik penugasan port Gig0/1.
#### Coba ping antara PC1 dan PC4.
