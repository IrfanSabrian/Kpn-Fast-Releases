# KPN FAST Releases

Repository ini adalah channel release resmi untuk aplikasi desktop KPN FAST. File installer Windows, metadata update, dan artifact dari `electron-builder` dipublish ke halaman GitHub Releases repository ini.

Source code utama aplikasi berada di repository `Kpn-Fast-Future-Accurate-Smart-Tender`. Repository ini dipisahkan agar branch source code tetap ringan dan file besar seperti `.exe`, `.blockmap`, dan `latest.yml` dikelola lewat mekanisme GitHub Releases.

## Untuk Pengguna

1. Buka tab `Releases`.
2. Pilih versi terbaru.
3. Download installer Windows KPN FAST.
4. Jalankan installer di komputer yang akan memakai aplikasi.

Jika auto-update aktif di aplikasi desktop, KPN FAST akan membaca metadata release dari repository ini dan menawarkan update saat versi baru tersedia.

## Untuk Maintainer

Release dibuat dari repository source code utama melalui workflow `Publish Desktop Release`.

Alur umum:

1. Update versi aplikasi di repository source.
2. Commit perubahan versi.
3. Buat dan push tag versi, misalnya `v1.0.1`.
4. GitHub Actions menjalankan build Windows.
5. Artifact hasil build dipublish ke GitHub Releases repository ini.

Publish lokal juga bisa dilakukan dari repository source dengan token GitHub:

```powershell
$env:GH_TOKEN="TOKEN_GITHUB"
npm run build:release
```

## Isi Release

Artifact release biasanya berisi:

- installer Windows KPN FAST (`.exe`)
- file metadata update (`latest.yml`)
- file delta/update pendukung dari `electron-builder`

Jangan commit artifact build langsung ke branch `main`. Simpan file release melalui tab `Releases` agar auto-update Electron tetap memakai format yang benar.

## Repository Terkait

- Source code: `Kpn-Fast-Future-Accurate-Smart-Tender`
- Release channel: `Kpn-Fast-Releases`
