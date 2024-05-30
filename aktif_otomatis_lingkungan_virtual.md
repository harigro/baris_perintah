# Mengaktifkan otomatis lingkungan virtual python

Sering terjadi kesulitan ketika harus mengaktifkan lingkungan virtual python karena dilakukan secara manual, oleh karena itu skrip ini diciptakan untuk memberikan kemudahan bagi para pengembang python terutama yang membutuhkan efisiensi dalam pengeerjaan proyek.

## Langkah - langkah

Dalam contoh ini saya menggunkan sistem operasi linux.  

1. Buka terminal dan ketik nama teks editor + ~/.bashrc lalu tekan ENTER. 

2. Diakhir baris tambahkan skrip berikut  
   
   ```bash
   # Aktifkan virtualenv otomatis saat berada di direktori proyek tertentu
   function activate_virtualenv() {
       if [[ $PWD == ~/Dokumen/python/proyek_pyside2/kalkulator* ]]; then
           source ~/Dokumen/python/proyek_pyside2/side2/bin/activate
           echo "Lingkungan virtual sedang diaktifkan"
           echo "Lingkungan virtual aktif"
       elif [[ -n "$VIRTUAL_ENV" ]]; then
           echo "Lingkungan virtual non aktif"
           deactivate
       fi
   }
   
   export PROMPT_COMMAND="activate_virtualenv;$PROMPT_COMMAND"
   ```

3. Simpan perintah dengan mengetik diterminal  
   
   ```bash
   source ~/.bashrc
   ```

4. keluar dari terminal dan buka lagi terminal dan arahkan ke direktori folder tempat proyek anda berada untuk menguji program.
