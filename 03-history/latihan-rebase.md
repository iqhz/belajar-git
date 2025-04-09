# ♻️ Latihan 3: Rebase, Reset, dan Clean History

## 🎯 Tujuan
- Mengerti perbedaan `merge` vs `rebase`
- Menggunakan `rebase` untuk merapikan history
- Memperbaiki commit dengan `amend` dan `reset`
- Menggunakan `stash` untuk simpan sementara perubahan

---

## 🪜 Langkah-langkah

### 1. Buat branch `fitur-rebase`

```bash
git checkout -b fitur-rebase
```

---

### 2. Buat commit bertahap

```bash
echo "Langkah 1" > 03-history/langkah.txt
git add .
git commit -m "Langkah pertama"

echo "Langkah 2" >> 03-history/langkah.txt
git add .
git commit -m "Langkah kedua"

echo "Langkah 3" >> 03-history/langkah.txt
git add .
git commit -m "Langkah ketiga"
```

---

### 3. Rebase ke main

```bash
git checkout main
git pull
git checkout fitur-rebase
git rebase main
```

Kalau konflik, selesaikan dan lanjutkan:

```bash
git add .
git rebase --continue
```

---

### 4. Gabungkan ke main (dengan fast-forward)

```bash
git checkout main
git merge fitur-rebase --ff-only
```

---

### 5. (Bonus) Edit commit terakhir

```bash
git commit --amend
```

---

### 6. (Bonus) Hapus perubahan sementara
git stash menyimpan perubahan yang belum di-commit ke tempat tersembunyi, lalu mengembalikan working directory kamu ke kondisi bersih.

Cocok buat situasi kayak:
Mau pindah branch tapi belum siap commit
Lagi eksperimen tapi belum yakin
Mau tarik update (git pull) tapi ada uncommitted changes

```bash
echo "sementara" > sementara.txt
git stash
git stash list
git stash pop
```

---
---

### 7. (Bonus) Menggunakan `git reset`

#### 🔁 Soft Reset: Balik commit tapi simpan perubahan di staging

```bash
git reset --soft HEAD~1
```

➡️ Commit terakhir dibatalkan, tapi perubahan masih dalam tahap "siap commit".

#### 🧽 Mixed Reset (default): Balik commit dan staging, simpan perubahan di file

```bash
git reset HEAD~1
```

➡️ Commit terakhir dibatalkan, perubahan pindah ke working directory (belum di-*add*).

#### ❌ Hard Reset: Hapus commit dan perubahan **(hati-hati!)**

```bash
git reset --hard HEAD~1
```

➡️ Commit dan perubahan dihapus total. Tidak bisa dibalikin kecuali dengan reflog.

> ⚠️ Gunakan `--hard` hanya jika kamu benar-benar yakin!

---



## ✅ Checklist

- [ ] Paham perbedaan merge vs rebase
- [ ] Sudah mencoba `rebase`
- [ ] Sudah mencoba `amend`, `reset`, atau `stash`
- [ ] History repo terlihat bersih
