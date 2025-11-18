```text
Bahasa yang digunakan adalah Bahasa Indonesia.
```

```markdown
# Praktikum-Struktur-data-Asdos

Tentu, ini dia konten README.md yang sudah digabungkan menjadi satu blok, siap untuk disalin dan ditempel langsung ke GitHub:

```markdown
# Implementasi Stack dan Queue dengan Python

Dokumen ini menjelaskan implementasi dasar dari struktur data Stack (Tumpukan) dan Queue (Antrian) menggunakan bahasa pemrograman Python.

## Struktur Data: Stack (Tumpukan)

*   **Tujuan:** Mengilustrasikan implementasi dan operasi dasar pada struktur data stack menggunakan Python.
*   **Proses:**
    1.  **Inisialisasi:** Membuat sebuah stack kosong.
        ```python
        stack = []
        ```
    2.  **Penambahan (Push):** Menambahkan elemen 'A', 'B', dan 'C' ke dalam stack. Elemen terakhir yang ditambahkan akan berada di "puncak" stack.
        ```python
        stack.append('A')
        stack.append('B')
        stack.append('C')
        ```
    3.  **Tampilan Awal:** Menampilkan isi stack setelah penambahan elemen.
        ```python
        print("Stack:", stack) # Output: Stack: ['A', 'B', 'C']
        ```
    4.  **Penghapusan (Pop):** Menghapus elemen yang berada di puncak stack (elemen terakhir yang ditambahkan) dan menampilkannya.
        ```python
        element = stack.pop()
        print("Pop:", element) # Output: Pop: C
        ```
    5.  **Intip (Peek):** Melihat elemen yang berada di puncak stack tanpa menghapusnya, lalu menampilkannya.
        ```python
        topElement = stack[-1]
        print("Peek:", topElement) # Output: Peek: B
        ```
    6.  **Pemeriksaan Kosong:** Memeriksa apakah stack dalam keadaan kosong atau tidak, lalu menampilkan hasilnya (True jika kosong, False jika tidak).
        ```python
        isEmpty = not bool(stack)
        print("isEmpty:", isEmpty) # Output: isEmpty: False
        ```
    7.  **Ukuran:** Menampilkan jumlah elemen yang terdapat di dalam stack.
        ```python
        print("Size:", len(stack)) # Output: Size: 2
        ```
*   **Konsep Utama:** Stack beroperasi berdasarkan prinsip **LIFO (Last-In, First-Out)**, yang berarti elemen terakhir yang dimasukkan akan menjadi elemen pertama yang dikeluarkan.

## Struktur Data: Queue (Antrian)

*   **Tujuan:** Mengilustrasikan implementasi dan operasi dasar pada struktur data queue menggunakan Python.
*   **Proses:**
    1.  **Inisialisasi:** Membuat sebuah queue kosong.
        ```python
        queue = []
        ```
    2.  **Penambahan (Enqueue):** Menambahkan elemen 'A', 'B', dan 'C' ke dalam queue. Elemen akan ditambahkan di akhir antrian.
        ```python
        queue.append('A')
        queue.append('B')
        queue.append('C')
        ```
    3.  **Tampilan Awal:** Menampilkan isi queue setelah penambahan elemen.
        ```python
        print("Queue:", queue) # Output: Queue: ['A', 'B', 'C']
        ```
    4.  **Penghapusan (Dequeue):** Menghapus elemen yang berada di depan antrian (elemen pertama yang ditambahkan) dan menampilkannya.
        ```python
        element = queue.pop(0)
        print("Dequeue:", element) # Output: Dequeue: A
        ```
    5.  **Intip (Peek):** Melihat elemen yang berada di depan antrian tanpa menghapusnya, lalu menampilkannya.
        ```python
        frontElement = queue[0]
        print("Peek:", frontElement) # Output: Peek: B
        ```
    6.  **Pemeriksaan Kosong:** Memeriksa apakah queue dalam keadaan kosong atau tidak, lalu menampilkan hasilnya (True jika kosong, False jika tidak).
        ```python
        isEmpty = not bool(queue)
        print("isEmpty:", isEmpty) # Output: isEmpty: False
        ```
    7.  **Ukuran:** Menampilkan jumlah elemen yang terdapat di dalam queue.
        ```python
        print("Size:", len(queue)) # Output: Size: 2
        ```
*   **Konsep Utama:** Queue beroperasi berdasarkan prinsip **FIFO (First-In, First-Out)**, yang berarti elemen pertama yang dimasukkan akan menjadi elemen pertama yang dikeluarkan.

## Perbandingan Singkat

| Fitur         | Stack (Tumpukan)                               | Queue (Antrian)                               |
|---------------|------------------------------------------------|-----------------------------------------------|
| Prinsip Kerja | LIFO (Last-In, First-Out)                      | FIFO (First-In, First-Out)                     |
| Penghapusan   | Menghapus elemen teratas (terakhir dimasukkan) | Menghapus elemen depan (pertama dimasukkan) |
| Analogi       | Tumpukan piring                                | Antrian di loket                              |
```

