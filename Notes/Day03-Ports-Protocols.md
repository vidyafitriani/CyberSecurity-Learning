# Day 03 - Ports and Protocols

## What is a Port?

Port adalah jalur komunikasi yang digunakan oleh aplikasi atau layanan untuk mengirim dan menerima data melalui jaringan.

---

## Common Ports

### Port 80

Protocol: HTTP

Function:
Digunakan untuk akses website tanpa enkripsi.

Example:
http://example.com

---

### Port 443

Protocol: HTTPS

Function:
Digunakan untuk akses website yang menggunakan SSL/TLS encryption.

Example:
https://example.com

---

### Port 22

Protocol: SSH

Function:
Digunakan untuk remote access ke server Linux secara aman.

Example:
ssh user@server

---

### Port 25

Protocol: SMTP

Function:
Digunakan untuk pengiriman email.

Example:
Mail server mengirim email ke mail server lain.

---

### Port 53

Protocol: DNS

Function:
Digunakan untuk menerjemahkan nama domain menjadi alamat IP.

Example:
google.com → 142.250.x.x

---

### Port 3389

Protocol: RDP

Function:
Digunakan untuk Remote Desktop Protocol pada Windows.

Example:
Remote Desktop Connection.

---

## Security Considerations

### Why Open Ports Can Be Dangerous

Port yang terbuka ke internet dapat menjadi target serangan jika tidak diamankan dengan baik.

Contoh:

- Brute Force Attack
- Exploitation
- Unauthorized Access

---

## Port 3389 Exposure Risk

Jika Port 3389 dibuka ke internet:

Risiko:
- Brute Force Attack
- Credential Theft
- Ransomware Deployment

Mitigation:
- VPN Access
- MFA
- Restrict Source IP
- Disable Public RDP Access