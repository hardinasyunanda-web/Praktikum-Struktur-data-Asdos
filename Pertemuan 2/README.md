# **PARAFRASE KODE PER BARIS**

### **Class Node**

```
1  class Node:
```

→ Mendefinisikan sebuah kelas bernama *Node*.

```
2      def __init__(self, data=None, pointer=None):
```

→ Membuat fungsi konstruktor yang menerima nilai data dan pointer ke node berikutnya.

```
3          self.data = data
```

→ Menyimpan nilai data pada properti `data`.

```
4          self.next = pointer
```

→ Menyimpan referensi node berikutnya pada properti `next`.

---

### **Class LinkedList**

```
6  class LinkedList:
```

→ Mendeklarasikan kelas untuk struktur data linked list.

```
7      def __init__(self):
```

→ Konstruktor linked list.

```
8          self.head = None
```

→ Awalnya, list tidak punya elemen sehingga head bernilai *None*.

---

### **insert_at_first**

```
10     def insert_at_first(self, data):
```

→ Metode untuk menambahkan elemen baru di posisi paling depan.

```
11         node = Node(data, self.head)
```

→ Membuat node baru dengan next menunjuk ke head saat ini.

```
12         self.head = node
```

→ Set node baru sebagai head.

---

### **insert_at_last**

```
14     def insert_at_last(self, data):
```

→ Metode menambah elemen di posisi paling akhir.

```
15         if self.head is None:
```

→ Jika list kosong…

```
16             self.head = Node(data)
```

→ …langsung jadikan node baru sebagai head.

```
17         else:
```

→ Jika list tidak kosong…

```
18             node_sekarang = self.head
```

→ Mulai traversal dari head.

```
19             while node_sekarang.next:
```

→ Selama node berikutnya masih ada…

```
20                 node_sekarang = node_sekarang.next
```

→ Maju ke node berikutnya.

```
22             node = Node(data)
```

→ Buat node baru.

```
23             node_sekarang.next = node
```

→ Letakkan node baru sebagai elemen paling akhir.

---

### **insert_at (insert di index tertentu)**

```
26     def insert_at(self, index, data):
```

→ Fungsi memasukkan data ke posisi indeks tertentu.

```
27         if index < 0 or index > self.length() - 1:
```

→ Jika index kurang dari 0 atau lebih dari batas…

```
28             print("index tidak valid")
```

→ …tampilkan pesan error.

```
29         elif index == 0:
```

→ Jika posisi yang dituju adalah 0…

```
30             self.insert_at_first(data)
```

→ …gunakan fungsi insert di awal.

```
31         else:
```

→ Untuk posisi selain 0…

```
32             urutan = 0
```

→ Inisialisasi penghitung posisi.

```
33             node_sekarang = self.head
```

→ Mulai dari head.

```
34             while urutan < index - 1:
```

→ Bergerak sampai satu langkah sebelum index.

```
35                 urutan += 1
```

→ Tambahkan penghitung.

```
36                 node_sekarang = node_sekarang.next
```

→ Maju ke node berikutnya.

```
38             node = Node(data, node_sekarang.next)
```

→ Buat node baru yang next-nya menunjuk ke node setelah posisi itu.

```
39             node_sekarang.next = node
```

→ Sambungkan node baru ke list.

---

### **remove_first (hapus elemen pertama)**

```
41     def remove_first(self):
```

→ Fungsi untuk menghapus elemen paling awal.

```
42         if self.head is None:
```

→ Jika list kosong…

```
43             print("tidak ada data yang bisa dihapus")
```

→ …tampilkan pesan bahwa tidak ada yang bisa dihapus.

```
44         else:
```

→ Jika ada elemen…

```
45             self.head = self.head.next
```

→ Geser head ke elemen berikutnya.

---

### **remove_last (hapus elemen terakhir)**

```
47     def remove_last(self):
```

→ Menghapus node paling akhir.

```
48         if self.head is None:
```

→ Jika list kosong…

```
49             print("tidak ada data yang bisa dihapus")
```

→ Tampilkan pesan.

```
50         elif self.head.next is None:
```

→ Jika hanya ada satu elemen…

```
51             self.head = None
```

→ Hapus elemen tersebut.

```
52         else:
```

→ Jika ada lebih dari satu elemen…

```
53             node_sebelumnya = None
```

→ Variabel penanda node sebelum terakhir.

```
54             node_sekarang = self.head
```

→ Mulai traversal dari head.

```
55             while node_sekarang.next:
```

→ Selama masih ada elemen setelahnya…

```
56                 node_sebelumnya = node_sekarang
```

→ Update node sebelumnya.

```
57                 node_sekarang = node_sekarang.next
```

→ Pindah ke node berikutnya.

```
59             node_sebelumnya.next = None
```

→ Putuskan node terakhir.

---

### **remove_at (hapus berdasarkan index)**

```
61     def remove_at(self, index):
```

→ Menghapus node pada index tertentu.

```
62         if index < 0 or index >= self.length():
```

→ Jika index tidak valid…

```
63             print("index invalid")
```

→ …beri pesan.

```
64         elif index == 0:
```

→ Kalau index = 0…

```
65             self.remove_first()
```

→ …hapus elemen pertama.

```
67         else:
```

→ Jika index di tengah list…

```
68             urutan = 0
```

→ Set penghitung posisi.

```
69             node_sekarang = self.head
```

→ Mulai di head.

```
70             while urutan < index - 1:
```

→ Loop sampai node sebelum target.

```
71                 node_sekarang = node_sekarang.next
```

→ Bergerak ke depan.

```
72                 urutan += 1
```

→ Tambahkan penghitung.

```
74             node_sekarang.next = node_sekarang.next.next
```

→ Lewati node yang ingin dihapus.

---

### **print()**

```
76     def print(self):
```

→ Menampilkan seluruh isi list.

```
77         if self.head is None:
```

→ Jika kosong…

```
78             print("data kosong")
```

→ …tampilkan pesan.

```
79         else:
```

→ Bila tidak kosong…

```
80             text_print = ''
```

→ Siapkan string kosong.

```
81             node_sekarang = self.head
```

→ Mulai dari head.

```
83             while node_sekarang:
```

→ Selama node masih ada…

```
84                 text_print += str(node_sekarang.data) + " → "
```

→ Tambahkan data ke string beserta panah.

```
85                 node_sekarang = node_sekarang.next
```

→ Pindah ke node berikutnya.

```
87             print(text_print)
```

→ Cetak isi list.

---

### **length()**

```
89     def length(self):
```

→ Menghitung jumlah node.

```
90         urutan = 0
```

→ Inisialisasi hitungan.

```
91         data_sekarang = self.head
```

→ Mulai dari head.

```
93         while data_sekarang:
```

→ Selama masih ada node…

```
94             data_sekarang = data_sekarang.next
```

→ Maju satu node.

```
95             urutan += 1
```

→ Tambah hitungan.

```
97         return urutan
```

→ Kembalikan jumlah node.

---

### **Program Utama**

```
100 ll = LinkedList()
```

→ Buat objek linked list baru.

```
103 ll.insert_at_first("jeruk")
104 ll.insert_at_first("mangga")
105 ll.insert_at_first("manggis")
```

→ Tambahkan 3 data di depan list.

```
106 ll.insert_at_last("apel")
```

→ Tambah “apel” di akhir.

```
107 ll.insert_at(2, "anggur")
```

→ Menyisipkan “anggur” pada index ke-2.

```
110 ll.remove_first()
```

→ Hapus elemen pertama.

```
111 ll.remove_last()
```

→ Hapus elemen terakhir.

```
112 ll.remove_at(1)
113 ll.remove_at(1)
```

→ Hapus elemen di index 1 sebanyak dua kali.

```
117 ll.print()
```

→ Cetak seluruh isi list.

```
118 print(ll.length())
```

→ Cetak jumlah elemen.

---
