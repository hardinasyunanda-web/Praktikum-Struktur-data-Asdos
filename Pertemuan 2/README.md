# **PENJELASAN SEDERHANA PER BAGIAN**

## **🔷 1. Class Node**

```
class Node:
```

→ Membuat tipe data Node (simpul).

```
def __init__(self, data=None, pointer=None):
```

→ Ketika Node dibuat, dia bisa punya *data* dan *next*.

```
self.data = data
```

→ Simpan nilai datanya.

```
self.next = pointer
```

→ Simpan alamat node berikutnya.

---

## **🔷 2. Class LinkedList**

```
class LinkedList:
```

→ Membuat struktur Linked List.

```
def __init__(self):
```

→ Saat pertama kali dibuat…

```
self.head = None
```

→ List masih kosong (belum ada head).

---

# **INSERT OPERATIONS**

## **🔹 insert_at_first() — Tambah di depan**

```
node = Node(data, self.head)
```

→ Buat node baru, next-nya menunjuk head lama.

```
self.head = node
```

→ Jadikan node baru sebagai head.

---

## **🔹 insert_at_last() — Tambah di belakang**

```
if self.head is None:
```

→ Kalau list kosong…

```
self.head = Node(data)
```

→ Node baru jadi head.

```
else:
    node_sekarang = self.head
```

→ Kalau tidak kosong, mulai dari head.

```
while node_sekarang.next:
    node_sekarang = node_sekarang.next
```

→ Maju sampai nodenya terakhir.

```
node_sekarang.next = Node(data)
```

→ Sambungkan node baru di ujung.

---

## **🔹 insert_at(index) — Tambah pada posisi tertentu**

```
if index < 0 or index > self.length() - 1:
```

→ Cek index valid atau tidak.

```
elif index == 0:
```

→ Kalau index 0 → sama seperti tambah depan.

```
else:
    urutan = 0
    node_sekarang = self.head
```

→ Mulai hitung dari awal.

```
while urutan < index - 1:
    urutan += 1
    node_sekarang = node_sekarang.next
```

→ Berhenti di node sebelum posisi yang diinginkan.

```
node = Node(data, node_sekarang.next)
node_sekarang.next = node
```

→ Simpan node baru di posisi tersebut.

---

# **REMOVE OPERATIONS**

## **🔹 remove_first() — Hapus depan**

```
if self.head is None:
```

→ Kalau kosong → tidak ada yg dihapus.

```
self.head = self.head.next
```

→ Pindah head ke node berikutnya.

---

## **🔹 remove_last() — Hapus belakang**

```
if self.head is None:
```

→ List kosong.

```
elif self.head.next is None:
```

→ Kalau isinya cuma 1…

```
self.head = None
```

→ Hilangkan.

```
else:
    node_sekarang = self.head
```

→ Mulai dari depan.

```
while node_sekarang.next:
    node_sebelumnya = node_sekarang
    node_sekarang = node_sekarang.next
```

→ Cari sampai node terakhir.

```
node_sebelumnya.next = None
```

→ Putuskan node terakhir.

---

## **🔹 remove_at(index) — Hapus posisi tertentu**

```
if index < 0 or index >= self.length():
```

→ Kalau index salah → error.

```
elif index == 0:
```

→ Hapus depan.

```
else:
    urutan = 0
    node_sekarang = self.head
```

→ Mulai dari awal.

```
while urutan < index - 1:
    node_sekarang = node_sekarang.next
    urutan += 1
```

→ Cari node sebelum posisi yang ingin dihapus.

```
node_sekarang.next = node_sekarang.next.next
```

→ Loncatkan node yang ingin dihapus.

---

# **UTILITY FUNCTIONS**

## **🔹 print()**

```
if self.head is None:
```

→ Kalau kosong → tampilkan "data kosong".

```
text_print = ''
node_sekarang = self.head
```

→ Siapkan string dan mulai dari head.

```
while node_sekarang:
    text_print += str(node_sekarang.data) + " → "
    node_sekarang = node_sekarang.next
```

→ Tambahkan semua data ke string.

```
print(text_print)
```

→ Cetak isi list.

---

## **🔹 length()**

```
urutan = 0
data_sekarang = self.head
```

→ Mulai hitung dari head.

```
while data_sekarang:
    data_sekarang = data_sekarang.next
    urutan += 1
```

→ Selama masih ada node → tambahkan hitungan.

```
return urutan
```

→ Kembalikan jumlah node.

---

# **PROGRAM UTAMA**

```
ll = LinkedList()
```

→ Buat list baru.

```
ll.insert_at_first(...)
```

→ Tambah beberapa data di depan.

```
ll.insert_at_last("apel")
```

→ Tambah "apel" di belakang.

```
ll.insert_at(2, "anggur")
```

→ Tambah "anggur" di index 2.

```
ll.remove_first()
ll.remove_last()
ll.remove_at(1)
```

→ Hapus data sesuai urutan operasi.

```
ll.print()
print(ll.length())
```

→ Tampilkan isi list dan jumlah elemennya.

---
