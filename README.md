# GIT & GITHUB | WPU

Kode ini merupakan materi Git & GitHub yang dibawakan oleh Pak **Sandhika Galih** dari channel YouTube _Web Programming UNPAS_.

Link Playlist Tutorial: [GIT & GITHUB](https://www.youtube.com/playlist?list=PLFIM0718LjIVknj6sgsSceMqlq242-jNf)

Bahasan Materi Meliputi:

- Apa itu Git & GitHub
- Install GitHub
- Membuat Repository di GitHub
- GitHub: Branch
- GitHub: Fork
- Git Init
- Git Status
- Git Add
- Git Config
- Git Commit
- Git Log
- Git Checkout
- Git Branch
- Git Merge
- Merge Conflict
- Git Remote
- Git Clone
- Git Push
- Git Fetch
- Git Pull
- GitHub Pages
- Multiple Remotes
- Pull Request (PR)
- Merge Pull Request
- Remote Branch
- Git Ignore
- Git Rebase
- Git & Web Hosting

## Technology stack & Tools

**Program ini membutuhkan:**

| Tech Stack & Tools | Version |
| ------------------ | ------- |
| Git                | 2.30+   |
| Visual Studio Code | Latest  |

## Catatan Pribadi

Jika ingin klona di komputer lain. Taruh di direktori berikut:

    .
    ├── Course
    │   ├── WPU
    |   |   ├── git-github
    |   |   └── ...
    |   └── ...
    └── ...

Jika sudah di berada di folder **git-github**, baru clone.

```shell
git clone https://github.com/bagusperdanay7/GIT-GITHUB-Notes.git
```

# Notes

Ini merupakan catatan pribadi mengenai materi dari **Git & GitHub** dengan Pak _Sandhika Galih_.

## Git Help

Komando Bantuan Git:

```shell
git help
```

Git Area:

- Working Directory
- Staging Area
- Repository

## Inisialisasi Git (Membuat Git Project)

```shell
git init
```

## Memeriksa Status Git

```shell
git status
```

## Menambah File

```shell
git add <file(s)>

git add index.html

# untuk menambahkan semua file
git add .
```

## Konfigurasi Profile Git

```shell
git config --global user.email "bagus@gmail.com"
git config --global user.name "Bagus Perdana"
```

## Commit

```shell
git commit -m "Pesan"

git commit -m "Menambah file index"
```

Jika memeriksa `git status` dan hasilnya modified, bisa gunakan perintah di bawah:

```shell
git commit -am "menambahkan feature x"
```

## Git Log

Git Log adalah perintah untuk melihat apa saja yang telah dilakukan, git log melacak riwayat commit yang dilakukan

```shell
git log

# melihat jumlah commit terakhir
git log -<jumlah>

git log -3 # melihat 3 commit terakhir

# melihat perubahan file tertentu
git log -- style.css

# melihat log dengan dekorasi satu baris dan graphnya
git log --all --decorate --oneline --graph
```

## Git Checkout

Untuk pindah ke commit tertentu bisa gunakan git checkout.

```shell
git checkout hash

# pindah commit dengan spesifik file
git checkout hash -- file
git checkout 542b5 -- style.css

# checkout sekaligus membuat branch baru
git checkout -b newbranch
```

## Git Branch

### Melihat semua branch

```shell
git branch
```

### Membuat Branch Baru dan Menangkap Snapshot di commit yang sama

```shell
git branch namabranch
git branch dosen
```

### Pindah Branch

```shell
git checkout namabranch
git checkout dosen
```

### Hapus Branch

```shell
git branch -d namabranch
git branch -d dosen

# paksa hapus (beresiko)
git branch -D namabranch
```

## Git Merge

Jenis-jenis Merge

- Fast Forward
- Three-way Merge

Fast forward terjadi ketika branch yang ingin digabungkan berada di satu jalur.

Three way merge/merge commit terjadi ketika branch yang digabungkan tidak berada di satu jalur.

Merge atau menggabungkan cabang, caranya pergi ke cabang yang mau digabungkan misal `master` dengan `checkout`. Lalu misal kita ingin menggabungkan master dengan cabang `dosen` maka perintahnya:

```shell
git checkout master
git merge dosen
```

Merge bisa dilakukan juga dengan cara berikut:

```shell
git merge namaremote/branch

git merge new/master
```

### Melihat Branch Yang telah di merged

```shell
git branch --merged

```

## Git Merge Conflict

Kadang-Kadang konflik terjadi ketika ingin merge dengan cabang lain, tipsnya jika terjadi conflict dan auto-merge nya tidak berfungsi maka diperlukan manual merge ketika proses merge tidak otomatis maka default code editor akan terbuka secara otomatis dan di situ dibutuhkan peninjauan manual.

## Git Remote

Remote biasanya merupakan sebuah server, contoh remote ada **GitHub, Gitlab, BitBucket, dll**. Jika bekerja di sebuah perusahaan, komputer perusahaan pun bisa dijadikan remote.

### Melihat Semua Remote

```shell
git remote

# melihat lebih detail (verbose)
git remote -v
```

### Menambahkan remote

```shell
git remote add namaremote url
git remote add origin https://github.com/bagusperdanay7/WPU-Test-Repo-1.git
```

Sebenarnya kita bisa menambah banyak remote atau disebut **Multiple Remotes**, caranya tambahkan saja remote baru:

```shell
git remote add new https://sandhikagalih/simple-landing-page.git
```

## Git Clone

Git clone berfungsi untuk mengklona suata repository dari remote, misalnya kita ingin mengklona repository seseorang dari GitHub. Maka perintahnya:

```shell
git clone url-remote-repository

git clone https://github.com/sandhikagalih/simple-landing-page.git
```

## Git Push

Mengirim perubahan commit ke remote:

```shell
git push

git push origin main

git push -u origin master

# push sekaligus hapus branch
git push origin --delete features
```

`-u` artinya upstream, `origin` nama remote dan `master` nama branchnya. Jadi kirim perubahan ke remote origin dan cabang master.

## Git Fetch

Git fetch digunakan untuk membandingkan commit di remote dan di local. Jadi ketika mengetik perintah `git status`, maka akan terdeteksi perbandingannya, misal jika remote dan local berbeda 1 commit.

```shell
git fetch

# jika remote lebih dari satu
git fetch namaremote
```

## Git Pull

Pull biasanya dilakukan ketika adanya perubahan di remote yang dilakukan oleh rekan kita, commitnya berbeda dengan di local kita, sehingga mengharuskan `pull` lebih dahulu kemudian baru bisa push. Hati-hati biasanya pull ini menghasilkan merge conflict. Ketika merge conflict telah di selesaikan baru kita bisa `push` ke remote.

```shell
git pull
```

## Git Ignore

Jika ingin mengabaikan (ignore) file file atau folder mana saja daftarkan saja ke file `.gitignore`. Jadi ketika disimpan ke remote file file yang terdaftar di `.gitignore` tidak terbawa. GitHub menyediakan templates berbagai project <https://github.com/github/gitignore> atau bisa kunjungi <https://www.toptal.com/developers/gitignore/>.

## Git Rebase

Git rebase merupakan salah satu strategi merge, Rebase akan maju ke commit terakhir master, sehingga ketika kita merging, nanti tipenya **fast-forward**, tidak akan menambah commit baru ketika merging. Misalnya branch saat ini adalah `fitur_keren` dan ingin di rebase ke master, maka perintahnya:

```shell
git rebase master
```

## Reference

- YouTube GIT & GITHUB - Web Programming UNPAS
