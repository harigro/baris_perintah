# Bahasa Java

Java sepertinya akan mendominasi seiring banyaknya pengguna android dan tentu saja  permintaan akan aplikasi berbasis android akan meningkat, oleh sebab itu kita harus tau bagaimana caranya menginstalasi bahasa java di sistem operasi terutama dalam contoh ini adalah sistem operasai linux.

## Mengunduh SDK Java

Buka browser dan ketik `adoptium` atau `https://adoptium.net/` dan pastikan mengunduh versi java sesuai kebutuhan anda.

## Ekstrak Arsip

Ekstrak arsip yang telah diunduh dengan perintah `tar`

```bash
tar -xvf nama_arsip.tar.gz
```

## Memindahkan Direktori

Pindahkan direktori JDK yang diekstrak ke `/opt`

```bash
sudo mv nama_berkas /opt/
```

## Konfigurasi Variabel Lingkungan

* Tambahkan JDK ke `PATH` dan atur `JAVA_HOME` dengan membuka berkas `.bashrc` atau `.zshrc` dengan editor teks (misalnya, `nano`, `vim`, atau `vscode` )
  
  * ```bash
    code ~/.bashrc
    ```



* Tambahkan baris berikut di bagian paling bawah berkas
  
  * ```bash
    export JAVA_HOME=/opt/nama_berkas
    export PATH=$JAVA_HOME/bin:$PATH
    ```

* Simpan perubahan dan muat ulang berkas konfigurasi
  
  * ```bash
    source ~/.bashrc
    ```

## Verifikasi Instalasi

Periksa instalasi dengan menjalankan

```bash
java --version
```

Dengan langkah-langkah di atas, Anda telah berhasil memindahkan instalasi JDK Java ke direktori `/opt` di Linux dan mengatur variabel lingkungan dengan benar. Pastikan untuk menyesuaikan nama direktori JDK sesuai dengan versi yang Anda unduh.




