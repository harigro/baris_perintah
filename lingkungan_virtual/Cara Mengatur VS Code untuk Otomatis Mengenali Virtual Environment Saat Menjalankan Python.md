# Cara Mengatur VS Code untuk Otomatis Mengenali Virtual Environment Saat Menjalankan Python

Untuk mengatur VS Code agar mengenali virtual environment secara otomatis ketika menekan tombol "Run" untuk menjalankan Python, kamu bisa mengikuti langkah-langkah berikut:

### 1. **Buat Virtual Environment di Folder Proyek**:

Sebenarnya sama saja tutuorialnya antara menggunakan `virualenv` atau `venv`. Jalankan perintah ini di terminal (pada folder proyek kamu) untuk membuat virtual environment:

```bash
python -m venv venv
```

   Ini akan membuat folder `venv` di dalam proyek kamu.

### 2. **Aktifkan Virtual Environment**:

   Untuk mengaktifkan virtual environment, jalankan perintah ini di terminal:

- **Windows**:
  
  ```bash
  .\venv\Scripts\activate
  ```
- **macOS/Linux**:
  
  ```bash
  source venv/bin/activate
  ```

### 3. **Atur VS Code untuk Menggunakan Virtual Environment**:

   Setelah virtual environment diaktifkan, buka proyek di VS Code dan pastikan interpreter Python sudah diarahkan ke virtual environment yang telah dibuat.

- Tekan `Ctrl + Shift + P` atau `Cmd + Shift + P` (untuk macOS) untuk membuka Command Palette.
- Ketik `Python: Select Interpreter` dan pilih interpreter Python yang berada di virtual environment (biasanya ada di `./venv/bin/python` atau `.\venv\Scripts\python.exe` untuk Windows).

### 4. **Buat atau Edit File `settings.json` (Opsional)**:

   Agar setiap kali membuka proyek, VS Code langsung menggunakan interpreter dari virtual environment, kamu bisa menambahkan pengaturan di file `settings.json` proyek kamu.

- Buat atau buka folder `.vscode` di direktori proyek, lalu buat atau edit file `settings.json` dengan menambahkan konfigurasi berikut:
  
  ```json
  {
    "python.pythonPath": "${workspaceFolder}/venv/bin/python"  // Linux/macOS
    // atau
    "python.pythonPath": "${workspaceFolder}\\venv\\Scripts\\python.exe"  // Windows
  }
  ```

### 5. **Jalankan Python dengan Tombol "Run"**:

   Sekarang, setiap kali menekan tombol "Run" di VS Code, interpreter akan menggunakan virtual environment dari folder proyek kamu.

Dengan langkah-langkah ini, virtual environment akan secara otomatis digunakan setiap kali kamu menjalankan Python di VS Code.
