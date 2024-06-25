# Memberikan izin toko snap di linux mint

Sejak versi 21.1 ke atas snap store sudah tidak tersedia di APT karena telas diblokir oleh pengembang linux mint, sehingga pengguna dialihkan ke flathub. Tetapi kabar baiknya kita diizinkan untuk membuat snap store tersedia dengan cara menghapus atau memindahkan berkas nosnap.pref

## Perbahrui sistem

```bash
sudo apt update
sudo apt upgrade
```

## Memindahkan atau menghapus berkas

* Menghapus berkas
  
  * ```bash
    sudo rm /etc/apt/preferences.d/nosnap.pref
    ```

* Memindahkan berkas
  
  Isi direktori_berkas sesuai dengan direktori berkas yang ingin dipindahkan
  
  * ```bash
    sudo mv /etc/apt/preferences.d/nosnap.pref ~/direktori_berkas/nosnap.backup
    ```

## Perbahrui APT Cache

```bash
sudo apt update
```

## Mengunduh layanan latar belakang atau toko snap

* Layanan latar belakang
  
  * ```bash
    sudo apt install snapd  
    ```
  
  * Atur Izin
    
    * Manual
    
    * ```bash
      sudo systemctl start snapd.service
      ```
    
    * Otomatis
    
    * ```bash
      sudo systemctl enable snapd.service
      ```
      
      * alias
      
      * ```bash
        sudo systemctl enable snapd
        ```

* Toko snap
  
  * ```bash
    sudo snap install snap-store
    ```

## Ucapan keberhasilan

Selamat 🎉 sekarang toko snap telah tersedia di sistem anda 👏.
