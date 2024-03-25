# Job Control

Tugas ini bertujuan untuk memperkenalkan konsep dasar dalam sistem operasi dan penggunaan kontrol pekerjaan (job control) dalam lingkungan Linux. Berikut adalah langkah-langkah dan penjelasan untuk setiap bagian tugas.

## 1. Eksekusi Seluruh Profile

### a. Edit File /etc/profile

Edit file `/etc/profile` dan tambahkan pesan:

```bash
echo "Profile dari /etc/profile"
```

### b. Edit Profil Pengguna

Edit semua profil pengguna:

```bash
/home/stD02001/.bash_profile
/home/. stD02001/.bash_login
/home/mahasiswa/.profile
/home/mahasiswa/.bashrc
```

Ganti /home/mahasiswa dengan nama Anda sendiri dan tambahkan pesan pada setiap file.

### c. Jalankan Instruksi Substitute User

Jalankan instruksi sebagai berikut:

```bash
$ su mahasiswa
$ exit
```

Kemudian jalankan opsi -:

```bash
$ su - mahasiswa
$ exit
```

Perbedaan kedua utilitas tersebut adalah...

## 2. Prompt String (PS)

### a. Edit File .bash_profile

Ganti prompt PS1 dengan > dan gunakan export agar perubahan dikenal oleh semua shell:

```bash
PS1=">"
export PS1
```

### b. Eksperimen Hasil PS1

Lakukan eksperimen dengan mengubah nilai PS1:

```bash
$ PS1=“\! > “
69 > PS1=”\d > “
Mon Sep 23 > PS1=”\t > “
10:10:20 > PS1=”Saya=\u > “
Saya=mahasiswa > PS1=”\w >”
~ > PS1=\h >”
```

## 3. Logout

Edit file .bash_logout dan tambahkan pesan:

```bash
echo "Terima kasih atas sesi yang diberikan"
sleep 5
clear
```

## 4. Bash Script

### a. Buat 3 Buah Script

Buat 3 buah script dengan isi masing-masing:

```bash
p1.sh
p2.sh
p3.sh
```

### b. Jalankan Script

Jalankan script sebagai berikut:

```bash
$ ./p1.sh ; ./p3.sh ; ./p2.sh
$ ./p1.sh &
$ ./p1.sh $ ./p2.sh & ./p3.sh &
$ ( ./p1.sh ; ./p3.sh ) &
```

## 5. Jobs

### a. Buat Shell-Script Loop

Buat shell-script yang melakukan loop dengan nama pwaktu.sh:

```bash
#!/bin/bash
while [ true ]
do
date >> hasil
sleep 10
done
```

### b. Jalankan Sebagai Background

Jalankan sebagai background dan jalankan utilitas find di background:

```bash
$ jobs
$ find / -print > files 2>/dev/null &
$ jobs
```

### c. Ubah Program ke 1 Menjadi Foreground

Ubah program ke 1 menjadi foreground:

```bash
$ fg %1
$ bg
```

### d. Stop Program Background

Hentikan program background dengan utilitas kill:

```bash
$ ps x
$ kill [Nomor PID]
```

## 6. History

### a. Ganti Nilai HISTSIZE

Ganti nilai HISTSIZE dan gunakan fasilitas history:

```bash
$ HISTSIZE=20
$ h
```

### b. Gunakan Fasilitas History

Gunakan fasilitas history untuk mengedit instruksi dan ulangi instruksi pada history buffer:

```bash
$ !-5
```

### c. Ulangi Instruksi yang Terakhir

Gunakan perintah untuk mengulangi instruksi terakhir:

```bash
$ !!
```
