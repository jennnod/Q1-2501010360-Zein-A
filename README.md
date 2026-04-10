# Q1-2501010360-Zein-A

1. Pada array, elemen-elemen disimpan bersebelahan (kontinu) di memori.
- Setiap elemen memiliki indeks.
- Alamat memori elemen ke-i bisa langsung dihitung dengan rumus:
alamat = alamat_awal + (i × ukuran_elemen)
Tidak perlu mencari satu per satu.
Kita bisa langsung “lompat” ke posisi yang diinginkan.
Akses elemen selalu membutuhkan waktu yang sama, tidak peduli posisi → O(1) (konstan).

Pada singly linked list, setiap node disimpan di lokasi memori yang tersebar (non-kontinu)
Harus mulai dari head (awal).  
Lalu mengikuti pointer satu per satu sampai ke elemen yang dituju.
Akses elemen ke-5 → harus melewati elemen ke-1, ke-2, ke-3, ke-4 dulu.
Semakin jauh posisi elemen, semakin lama waktu akses → O(n) (linear).

| Struktur Data      | Penyimpanan Memori | Cara Akses              | Kompleksitas |
| ------------------ | ------------------ | ----------------------- | ------------ |
| Array              | Kontinu            | Langsung via indeks     | O(1)         |
| Singly Linked List | Non-kontinu        | Traversal node per node | O(n)         |

Kesimpulan: 
Array cepat (O(1)) karena alamat elemen bisa dihitung langsung berkat memori yang kontinu.
Linked list lambat (O(n)) karena harus menelusuri pointer satu per satu akibat memori yang tidak berurutan.

2. Pada Array, elemen disimpan secara berurutan di memori. Jika ingin menyisipkan atau menghapus elemen di tengah:
Harus menggeser elemen lain (shift)
Kompleksitas waktu: O(n)

Sedangkan pada Linked List:
Cukup mengubah pointer (referensi node)
Tidak perlu menggeser elemen lain
Kompleksitas waktu: O(1) (jika posisi sudah diketahui)
    
Array insertion Alasan Teoritis:
  Linked List tidak bergantung pada penyimpanan memori yang kontigu, sehingga manipulasi struktur hanya melibatkan perubahan pointer, bukan relokasi data

3. Pada Doubly Linked List, setiap node memiliki struktur anatomi yang terdiri dari tiga bagian utama:
- Data (nilai) → menyimpan informasi atau elemen yang ingin disimpan.
- Pointer ke node berikutnya (next) → menunjuk ke node setelahnya.
- Pointer ke node sebelumnya (prev) → menunjuk ke node sebelumnya.

4. 1.Struktur Keterhubungan
  - Singly Linked List: Node terakhir menunjuk ke NULL (akhir dari list).
  - Circular Linked List: Node terakhir tidak menunjuk ke NULL, tetapi kembali menunjuk ke node pertama (head), sehingga membentuk lingkaran.
   2. Traversal (Penelusuran)
  - Singly Linked List: Traversal dimulai dari head dan berhenti saat NULL.
  - Circular Linked List: Traversal bisa dimulai dari node mana saja dan akan terus berputar sampai kembali ke titik awal.
   3.Efisiensi Operasi Tertentu
  - Pada Circular Linked List, tidak perlu penanganan khusus untuk kondisi akhir list karena tidak ada NULL, sehingga beberapa operasi (seperti iterasi berulang) bisa lebih efisien.

5. Jika array masih memiliki slot kosong, operasi append:

  Elemen langsung ditambahkan di indeks berikutnya
  Waktu eksekusi: O(1) (sangat cepat)
  Saat Kapasitas Habis

Ketika array sudah penuh, Python tidak bisa langsung menambahkan elemen. Maka terjadi proses berikut:
  - Alokasi Memori Baru
    Python membuat array baru dengan kapasitas lebih besar dari sebelumnya
    Biasanya tidak hanya +1, tapi diperbesar (over-allocation), misalnya ~1.125x atau lebih (strategi ini untuk efisiensi)
  - Copy Data Lama
    Semua elemen dari array lama disalin ke array baru
    Ini butuh waktu O(n)
  - Tambahkan Elemen Baru
    Setelah penyalinan selesai, elemen baru dimasukkan
  - Dealokasi Array Lama
    Memori array lama dilepaskan (garbage collection)
