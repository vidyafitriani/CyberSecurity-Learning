# Day 04 - Authentication & Authorization

## Introduction

Authentication dan Authorization adalah dua konsep dasar yang digunakan hampir di semua sistem keamanan modern.

Banyak orang menganggap keduanya sama, padahal memiliki fungsi yang berbeda.

---

## Authentication

Authentication adalah proses untuk memverifikasi identitas seseorang atau sistem.

Pertanyaan yang dijawab:

"Siapa kamu?"

Contoh:

- Login menggunakan username dan password
- Login menggunakan fingerprint
- Login menggunakan OTP
- Login menggunakan MFA

Jika identitas berhasil diverifikasi, maka proses authentication berhasil.

---

## Authorization

Authorization adalah proses menentukan hak akses yang dimiliki setelah berhasil login.

Pertanyaan yang dijawab:

"Apa yang boleh kamu lakukan?"

Contoh:

- User biasa hanya bisa melihat data
- Manager bisa menyetujui pengajuan
- Administrator bisa membuat user baru

Authorization dilakukan setelah authentication berhasil.

---

## Authentication vs Authorization

Contoh sederhana:

Saat masuk ke kantor:

1. Satpam memeriksa kartu identitas
   → Authentication

2. Setelah masuk, kamu hanya boleh mengakses ruangan tertentu
   → Authorization

---

## Factors of Authentication

### Something You Know

Contoh:

- Password
- PIN

---

### Something You Have

Contoh:

- Smartphone
- Security Token
- OTP Application

---

### Something You Are

Contoh:

- Fingerprint
- Face Recognition
- Retina Scan

---

## Multi-Factor Authentication (MFA)

MFA adalah metode keamanan yang menggunakan lebih dari satu faktor authentication.

Contoh:

Password + OTP

Keuntungan:

- Mengurangi risiko pencurian akun
- Melindungi akun meskipun password bocor

---

## Principle of Least Privilege

Prinsip keamanan yang memberikan hak akses minimum yang diperlukan untuk melakukan pekerjaan.

Contoh:

Staff HR tidak perlu memiliki akses Administrator Server.

Semakin sedikit hak akses, semakin kecil risiko keamanan.

---

## Real World Example

Microsoft 365

Authentication:

- Username
- Password
- MFA

Authorization:

- User
- Global Administrator
- Exchange Administrator
- Security Administrator

---

## Why It Matters for Cyber Security

Hampir semua sistem keamanan modern bergantung pada Authentication dan Authorization.

Contoh:

- Active Directory
- Azure Entra ID
- Okta
- VPN
- Cloud Security 
- Zero Trust Architecture

Memahami konsep ini merupakan fondasi sebelum mempelajari Identity and Access Management (IAM).