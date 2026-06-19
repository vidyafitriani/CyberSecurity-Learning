# Day 05 - Introduction to Active Directory

## Workgroup vs Domain

| Workgroup | Domain |
|------------|------------|
| Tidak ada pusat kontrol | Dikelola Domain Controller |
| User lokal | User tersentralisasi |
| Cocok untuk rumah | Cocok untuk perusahaan |


## Apa Itu Active Directory?

Active Directory (AD) adalah layanan identitas (Identity Service) milik Microsoft yang digunakan untuk:

Mengelola user
Mengelola komputer
Mengelola group
Mengatur hak akses
Mengontrol autentikasi dalam jaringan perusahaan

Sederhananya:

Active Directory adalah "database identitas perusahaan".

Kenapa Perusahaan Membutuhkan AD?

Bayangkan perusahaan punya:

500 User
300 Laptop
50 Server
20 Printer

Kalau tidak ada Active Directory:

User A login satu per satu ke setiap komputer
Password beda-beda
Hak akses diatur manual

😵‍💫 Ribet.

Dengan Active Directory:

1 Username
1 Password
1 Identitas

Bisa dipakai di seluruh domain.

Workgroup vs Domain
Workgroup

Contoh:

Rumah.

Laptop A
Laptop B
Laptop C

Masing-masing berdiri sendiri.

User dibuat lokal.

Tidak ada pusat kontrol.

Domain

Contoh:

Perusahaan.

DC01
 │
 ├── Laptop User 1
 ├── Laptop User 2
 ├── Laptop User 3
 └── Server

Semua identitas tersimpan di Domain Controller.


## Domain Controller (DC)

Domain Controller adalah server yang menjalankan Active Directory.

Fungsi:
- Authentication
- Authorization
- Group Policy
- User Management
- Computer Management

Tugasnya:

Menyimpan user
Menyimpan password
Melakukan authentication
Menyimpan group
Menyimpan policy

Contoh:

DC01

Nanti ini yang akan kita bangun di lab.

## Organizational Unit (OU)

OU digunakan untuk mengelompokkan Objek / user dan komputer berdasarkan kebutuhan organisasi.

Contoh:

LAB.LOCAL
├── HR
├── Finance
├── IT
└── Warehouse


Tujuannya:

Memudahkan manajemen
Memudahkan penerapan policy
User

User adalah identitas yang digunakan untuk login.

Contoh:

vidya

atau

vidya.fitriani
Group

Group digunakan untuk mengelompokkan user.

Contoh:

HR-Team
Finance-Team
IT-Administrator

Daripada memberi akses satu per satu, cukup ke group.

Authentication Flow

Misalnya:

User Login
↓
Username + Password
↓
DC01
↓
Verifikasi
↓
Berhasil Login

Inilah yang disebut:

Authentication
Group Policy (GPO)

Group Policy digunakan untuk mengatur komputer dan user secara terpusat.

Contoh:

Disable USB
Set Wallpaper
Password Policy
Lock Screen

Semua bisa dari Domain Controller.

Hubungan Dengan Cyber Security

Security Engineer sering mengelola:

Identity
User
Group
Role
Access Control
Siapa boleh akses apa
Authentication
Password
MFA
Smart Card
Authorization
Permission
Privilege
Active Directory = Fondasi IAM

Kalau nanti belajar:

Microsoft Entra ID
Okta
SailPoint
Saviynt

Maka konsepnya berasal dari Active Directory.

Diagram Sederhana
                 LAB.LOCAL

                     │

             ┌─────────────┐
             │    DC01     │
             │ Active Dir  │
             └─────────────┘

                   │

      ┌────────────┼────────────┐
      │            │            │

   HR-PC01     FIN-PC01     IT-PC01

      │            │            │

      └──────── Login ────────┘

## My Understanding

### 1. Perbedaan Workgroup dan Domain

Workgroup → tiap komputer berdiri sendiri, nggak ada pusat kontrol. User dan password disimpan lokal di masing-masing PC.

Domain → semua komputer terhubung ke server pusat (Domain Controller). User, password, dan aturan diatur dari satu tempat.

### 2. Kenapa perusahaan lebih pilih Domain?
Karena lebih rapi dan aman:

Admin bisa kontrol semua user dari satu titik.

Kalau ada karyawan baru, tinggal bikin akun di server, langsung bisa login di semua PC.

Security lebih kuat, gampang bikin aturan (policy) yang sama untuk semua.

### 3. Fungsi Domain Controller
Jadi otak pusat buat autentikasi (login user).

Simpan database akun, password, dan aturan (Active Directory).

Ngatur policy, misalnya password harus kuat, atau user Finance nggak boleh akses folder IT.

### 4. Kenapa OU (Organizational Unit) diperlukan?
Bayangin perusahaan punya HR, Finance, IT, Warehouse.
Kalau semua user dicampur jadi satu, ribet banget.
Dengan OU:

Bisa pisahin user sesuai departemen.

Bisa kasih policy berbeda (misalnya HR boleh akses data karyawan, tapi Warehouse nggak).

Lebih gampang di-manage, kayak bikin folder-folder biar nggak berantakan.

### 5. Challenge: Kalau DC01 mati total
Minimal 3 dampak besar:

User nggak bisa login ke domain → karyawan stuck di login screen.

Policy & akses shared folder nggak jalan → file server, printer, aplikasi internal bisa kacau.

Single point of failure → semua kontrol domain lumpuh, bikin operasional perusahaan berhenti.

Kalau perusahaan cuma punya 1 DC (nggak ada backup/replica), dampaknya bisa parah banget sampai bikin downtime total.

## Reflection

Hari ini saya belajar bahwa Active Directory merupakan fondasi utama manajemen identitas pada lingkungan perusahaan.

Saya juga memahami bahwa Domain Controller menjadi komponen kritikal karena berperan sebagai pusat autentikasi, otorisasi, dan pengelolaan policy.

Konsep ini menjadi dasar sebelum mempelajari Microsoft Entra ID, IAM, dan teknologi Zero Trust.