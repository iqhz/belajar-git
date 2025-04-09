
# 🧪 Latihan 1: Dasar-Dasar Git

## 🎯 Tujuan
- Memahami proses `init`, `add`, `commit`, dan `log`
- Mengenal `.gitignore`

---

## 🪜 Langkah-langkah

### 1. Inisialisasi Repo Git (kalau belum)
```bash
git init
```

### 2. Buat File README
```bash
echo "# Latihan Git Dasar" > 01-dasar/hello.md
```

### 3. Cek status perubahan
```bash
git status
```

### 4. Tambahkan ke staging
```bash
git add 01-dasar/hello.md
```

### 5. Commit perubahan
```bash
git commit -m "Menambahkan hello.md di latihan dasar"
```

### 6. Lihat histori commit
```bash
git log --oneline --graph --all
```

---

## ⚠️ Bonus: `.gitignore`

1. Buat file sampah simulasi:
```bash
echo "ini file log" > debug.log
```

2. Tambahkan `.gitignore`:
```bash
echo "*.log" > .gitignore
```

3. Cek status:
```bash
git status
```

4. Commit `.gitignore`:
```bash
git add .gitignore
git commit -m "Menambahkan .gitignore untuk file log"
```

---

## ✅ Checklist

- [ ] `git init` dijalankan
- [ ] File `hello.md` dibuat dan di-commit
- [ ] `.gitignore` diatur untuk `.log`
- [ ] Histori commit bisa dilihat
