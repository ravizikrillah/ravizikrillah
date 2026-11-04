# Panduan Aktivasi GitHub Profile README (`Ravizikrillah/Ravizikrillah`)

Semua file untuk tampilan halaman depan GitHub kamu sudah siap di folder ini.

## 1. Opsional: Tambahkan Link Sosial Media
Buka `README.md` di bagian `Let's Connect and Grow Together!`, lalu hapus tanda komentar `<!-- ... -->` pada ikon LinkedIn / YouTube / Instagram dan ganti `USERNAME_..._KAMU` dengan username aslimu.

## 2. Buat Special Repository & Push ke GitHub
Karena kamu sudah login di `gh` CLI sebagai `Ravizikrillah`, kamu cukup menjalankan perintah berikut dari terminal di dalam folder ini:

```bash
cd /Users/ravi/Project/personal/Ravizikrillah
git init -b main
git add .
git commit -m "feat: initialize GitHub profile README"
gh repo create Ravizikrillah/Ravizikrillah --public --source=. --remote=origin --push
```

> **Penting:** Repository **wajib berstatus `Public`** agar GitHub menampilkannya di halaman profil `https://github.com/Ravizikrillah`.

## 3. Cara Kerja Otomatis Animasi Ular (`snake.yaml`)
- Begitu kamu push ke branch `main`, GitHub Actions **Generate GitHub Contributions Snake** otomatis berjalan (~15 detik) dan membuat branch `output` berisi `github-snake.svg` dan `github-snake-dark.svg`.
- Tidak perlu setting token apa pun untuk animasi ular (otomatis memakai `GITHUB_TOKEN` bawaan).

## 4. Opsional: Aktifkan Live Auto-Update `lowlighter/metrics` (`metrics.yaml`)
Saat pertama kali push, kartu `github-metrics.svg` bawaan yang berisi statistik asli kamu sudah langsung tampil rapi (tidak *broken image*). Jika kamu ingin memakai kartu detail otomatis dari `lowlighter/metrics` persis seperti `OfficialCodeVoyage`:

1. Buka GitHub **Settings → Developer settings → Personal access tokens → Tokens (classic)**.
2. Klik **Generate new token (classic)**, beri nama `METRICS_TOKEN`, centang scope **`read:user`** (dan `public_repo` jika ingin analisis mendalam), lalu copy tokennya.
3. Buka repo `https://github.com/Ravizikrillah/Ravizikrillah/settings/secrets/actions` → klik **New repository secret**:
   - **Name:** `METRICS_TOKEN`
   - **Secret:** *(paste token tadi)*
4. Buka tab **Actions** → pilih **Generate GitHub Metrics** → klik **Run workflow**.
