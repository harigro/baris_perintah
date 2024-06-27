# Kompilasi kode python dengan pyinstaller

Kompilasi kode menjadi penting jika ingin mendistribusikan aplikasi ke sistem operasi tertentu dan dalam contoh ini saya memberikan caranya mengkompilasi kode program python di sistem operasi linux

## Memasang pyinstaller

ketik perintah berikut

```bash
pip install pyinstaller
```

## Terminal

Buka teminal dan arahkan ke direktori proyek anda lalu ketik perintah berikut  

```bash
pyinstaller --onefile --name nama_aplikasi --clean nama_program.py
```

selamat aplikasi anda siap untuk didistribusikan




















