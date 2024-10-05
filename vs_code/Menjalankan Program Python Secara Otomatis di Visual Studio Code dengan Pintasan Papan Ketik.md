# Menjalankan Program Python Secara Otomatis di Visual Studio Code dengan Pintasan Papan Ketik

Untuk menjalankan program Python secara otomatis di Visual Studio Code (VS Code) dengan perintah keyboard seperti `CTRL+T`, kamu bisa menggunakan **ikatan kunci** di VS Code dan memanfaatkan fitur **Task** atau **Launch Configurations**. Berikut ini langkah-langkah yang bisa kamu ikuti:

### Opsi 1: Menggunakan kostum ikatan kunci untuk Jalankan Python File

1. **Buka File Pengaturan Ikatan Kunci:**
   
   - Buka Command Palette dengan menekan `CTRL+SHIFT+P`.
   - Cari dan pilih `Preferences: Open Keyboard Shortcuts (JSON)`.

2. **Tambahkan Kostum Ikatan Kunci:**
   Tambahkan kode berikut di file `keybindings.json` untuk mengikat kombinasi `CTRL+T` ke perintah `python.execInTerminal`.
   
   ```json
   [
       {
           "key": "ctrl+t",
           "command": "python.execInTerminal",
           "when": "editorTextFocus && editorLangId == 'python'"
       }
   ]
   ```
   
   Untuk kombinasi satu atau lebih pintasan
   
   ```json
   [
       {
           "key": "ctrl+t ctrl+p ctrl+q",
           "command": "python.execInTerminal",
           "when": "editorTextFocus && editorLangId == 'python'"
       }
   ]
   ```
   
   Keterangan:
   
   - **`"key"`**: Kombinasi tombol yang kamu inginkan (misalnya `CTRL+T`).
   - **`"command"`**: Perintah yang akan dijalankan (di sini perintah Python `execInTerminal` untuk menjalankan script Python di terminal).
   - **`"when"`**: Kondisi kapan shortcut ini akan aktif (misalnya hanya saat file Python terbuka).

3. **Save** dan sekarang kamu bisa menjalankan script Python dengan menekan `CTRL+T`.

### Opsi 2: Menggunakan VS Code Task

Jika kamu ingin lebih fleksibel, kamu bisa membuat **Task** di VS Code yang menjalankan Python dan mengaitkan shortcut keyboard ke task tersebut.

1. **Buat Task Baru:**
   
   - Tekan `CTRL+SHIFT+P` dan pilih `Tasks: Configure Task`.
   - Pilih `Create tasks.json file from template` → `Others`.

2. **Tambahkan Konfigurasi Task untuk Python:**
   
   Setelah file `tasks.json` terbuka, tambahkan konfigurasi berikut untuk menjalankan file Python:
   
   ```json
   {
       "version": "2.0.0",
       "tasks": [
           {
               "label": "Run Python File",
               "type": "shell",
               "command": "python ${file}",
               "group": {
                   "kind": "build",
                   "isDefault": true
               },
               "problemMatcher": [],
               "detail": "Jalankan file Python saat ini."
           }
       ]
   }
   ```
   
   Ini akan membuat task untuk menjalankan file Python yang sedang dibuka.

3. **Tambahkan Ikatan Kunci untuk Task:**
   
   - Buka Command Palette dengan `CTRL+SHIFT+P` dan cari `Preferences: Open Keyboard Shortcuts (JSON)` lagi.
   - Tambahkan keybinding berikut untuk task tersebut:
   
   ```json
   [
       {
           "key": "ctrl+t",
           "command": "workbench.action.tasks.runTask",
           "args": "Run Python File"
       }
   ]
   ```

4. **Simpan**, dan sekarang kamu bisa menekan `CTRL+T` untuk menjalankan script Python melalui task.

### Ekstensi Tambahan

Kamu juga bisa menggunakan ekstensi seperti **Code Runner** yang memungkinkan kamu untuk menjalankan script Python (atau bahasa lainnya) dengan shortcut keyboard khusus. Ekstensi ini menyediakan shortcut default (`CTRL+ALT+N`) untuk menjalankan file Python tanpa konfigurasi tambahan.
