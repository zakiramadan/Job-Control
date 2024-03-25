# Job Control

Tugas ini bertujuan untuk memperkenalkan konsep dasar dalam sistem operasi dan penggunaan kontrol pekerjaan (job control) dalam lingkungan Linux. Berikut adalah langkah-langkah dan penjelasan untuk setiap bagian tugas.

## 1. Eksekusi Seluruh Profile

### a. Edit File /etc/profile

Edit file `/etc/profile` dan tambahkan pesan:

```bash
echo "Profile dari /etc/profile"
```

![App Screenshot](/Images/1.png)

![App Screenshot](/Images/2.png)

![App Screenshot](/Images/3.png)

### b. Edit Profil Pengguna

Edit semua profil pengguna:

```bash
/home/stD02001/.bash_profile
/home/. stD02001/.bash_login
/home/mahasiswa/.profile
/home/mahasiswa/.bashrc
```

![App Screenshot](/Images/4.png)

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

![App Screenshot](/Images/5.png)

Perbedaan kedua utilitas tersebut...

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

![App Screenshot](/Images/6.png)

## 3. Logout

Edit file .bash_logout dan tambahkan pesan:

```bash
echo "Terima kasih atas sesi yang diberikan"
sleep 5
clear
```

![App Screenshot](/Images/9.png)

![App Screenshot](/Images/10.png)

## 4. Bash Script

### a. Buat 3 Buah Script

Buat 3 buah script dengan isi masing-masing:

```bash
p1.sh
p2.sh
p3.sh
```

![App Screenshot](/Images/nano%203%20buah%20script.png)

![App Screenshot](/Images/11.png)

![App Screenshot](/Images/12.png)

![App Screenshot](/Images/12.png)

![App Screenshot](/Images/14.png)

### b. Jalankan Script

Jalankan script sebagai berikut:

```bash
$ ./p1.sh ; ./p3.sh ; ./p2.sh
$ ./p1.sh &
$ ./p1.sh $ ./p2.sh & ./p3.sh &
$ ( ./p1.sh ; ./p3.sh ) &
```

![App Screenshot](/Images/15.png)

![App Screenshot](/Images/16.png)

![App Screenshot](/Images/17.png)

![App Screenshot](/Images/18.png)

## 5. Jobs

### a. Buat Shell-Script Loop

Buat shell-script yang melakukan loop dengan nama pwaktu.sh:

```bash
#!/bin/bash
while [ true ]
do
date >> hasil
echo "my name is zaki"
sleep 10
done
```

![App Screenshot](/Images/pwaktu.png)

### b. Jalankan Sebagai Background

Jalankan sebagai background dan jalankan utilitas find di background:

```bash
$ jobs
$ find / -print > files 2>/dev/null &
$ jobs
```

![App Screenshot](/Images/19.png)

### c. Ubah Program ke 1 Menjadi Foreground

Ubah program ke 1 menjadi foreground:

```bash
$ fg %1
$ bg
```

![App Screenshot](/Images/20.png)

### d. Stop Program Background

Hentikan program background dengan utilitas kill:

```bash
$ ps x
$ kill [Nomor PID]
```

![App Screenshot](/Images/21.png)

![App Screenshot](/Images/22.png)

## 6. History

### a. Ganti Nilai HISTSIZE

Ganti nilai HISTSIZE dan gunakan fasilitas history:

```bash
$ HISTSIZE=20
$ h
```

![App Screenshot](/Images/23.png)

### b. Gunakan Fasilitas History

Gunakan fasilitas history untuk mengedit instruksi dan ulangi instruksi pada history buffer:

```bash
$ !-5
```

![App Screenshot](/Images/24.png)

### c. Ulangi Instruksi yang Terakhir

Gunakan perintah untuk mengulangi instruksi terakhir:

```bash
$ !!
```

![App Screenshot](/Images/25.png)

### d. Ulangi Instruksi pada History Buffer Nomor (sebagai contoh: 101)

Jalankan instruksi yang ada di history buffer dengan nomor 101:

```bash
$ !101
```

![App Screenshot](/Images/26.png)

### e. Ulangi Instruksi dengan Prefix "ls"

Ulangi instruksi yang memiliki prefix "ls":

```bash
$ ls
```

![App Screenshot](/Images/27.png)

Dengan langkah-langkah di atas, Anda akan dapat memahami dan menguasai penggunaan job control serta konsep dasar sistem operasi dalam lingkungan Linux. Semoga berhasil!
