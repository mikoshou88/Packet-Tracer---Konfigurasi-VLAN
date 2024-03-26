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
#### S1#(config-vlan)# nama Fakultas/Staf

#### B. Buat VLAN yang tersisa.
#### · VLAN 20: Siswa
#### · VLAN 30: Gues(Default)
#### · VLAN 99: Management&Native
#### · VLAN 150: VOICE
