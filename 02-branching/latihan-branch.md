# 🌿 Latihan 2: Branching dan Merge

## 🎯 Tujuan
- Belajar membuat branch baru
- Melakukan perubahan di branch tersebut
- Merge ke `main`
- (Bonus) Mengatasi konflik merge

---

## 🪜 Langkah-langkah

### 1. Buat Branch Baru

```bash
git checkout -b fitur-hello
```

> Ini otomatis membuat branch `fitur-hello` dan langsung pindah ke sana.

---

### 2. Buat File Baru di Branch

```bash
echo "Halo dari branch fitur-hello!" > 02-branching/hello-branch.md
git add .
git commit -m "Menambahkan hello-branch.md di fitur-hello"
```

---

### 3. Kembali ke `main` dan Merge

```bash
git checkout main
git merge fitur-hello
```

Kalau tidak ada konflik, akan otomatis merge.

---

### 4. Push ke GitHub

```bash
git push
```

---

## 🔥 Bonus: Simulasi Konflik Merge (Opsional)

1. Ubah file `README.md` di `main`
2. Ubah juga `README.md` di `fitur-hello`
3. Lalu coba merge — akan terjadi **konflik**
4. Edit file, selesaikan konflik, lalu commit:
```bash
git add README.md
git commit
```

---

## ✅ Checklist

- [ ] Branch baru dibuat
- [ ] Perubahan dicommit di branch
- [ ] Branch sudah di-merge ke `main`
- [ ] Konflik merge (jika dicoba) berhasil diatasi
