# P06 Keamanan Sistem Informasi — Web Dummy Chatbot Kantin Koperasi

Praktikum **P06: Risiko AI LLM dan Direct Prompt Injection Demo**

## Identitas Mahasiswa
- **Nama**: M.Putara Meca Abzanro
- **NIM**: 24781078
- **Kelas**: MI 5C
- **Program Studi**: Manajemen Informatika — Politeknik Negeri Lampung

---

## Ringkasan Proyek
Repositori ini memuat implementasi Web Dummy Asisten Chatbot Kantin Koperasi Mahasiswa yang mendemonstrasikan kerentanan **Direct Prompt Injection** serta implementasi **Mitigasi Pertahanan Berlapis (Defense-in-Depth)**.

### 1. Versi RENTAN (`24781078-kantin-voucher-rentan.html`)
- **Kelemahan Arsitektur**: Prompt datar tanpa pemisahan peran (*string concatenation*).
- **Vulnerabilitas**: Input pengguna dapat menimpa aturan sistem (*jailbreak/system override*), memaksa AI menjadi kasir dan menerbitkan voucher diskon 100%.
- **Live Demo**: [Versi Rentan](24781078-kantin-voucher-rentan.html)

### 2. Versi AMAN (`24781078-kantin-voucher-aman.html`)
- **Hierarki Peran**: Pemisahan tegas pesan sistem (`[SYSTEM]`) dan pesan pengguna (`[USER]`).
- **Prinsip Hak Minimum (Least Privilege)**: Wewenang pembuatan voucher dicabut sepenuhnya dari kapabilitas bot asisten.
- **Sanitasi & Filter Input/Output**: Guardrail Regex di luar model mendeteksi percobaan manipulasi dan memblokir kebocoran token voucher.
- **Live Demo**: [Versi Aman](24781078-kantin-voucher-aman.html)

---

## Struktur Berkas Repositori
```text
p06-kantin-voucher/
├── index.html                           # Halaman Portal Utama Praktikum (NIM: 24781078)
├── 24781078-kantin-voucher-rentan.html  # Web Chatbot Versi Rentan
├── 24781078-kantin-voucher-aman.html    # Web Chatbot Versi Aman / Terproteksi
├── .gitignore                           # Git ignore konfigurasi lokal
└── README.md                            # Dokumentasi Proyek
```

---

## Cara Menjalankan
1. Clone repositori ini:
   ```bash
   git clone https://github.com/MecaAbzanro/p06-kantin-voucher.git
   ```
2. Buka berkas `index.html` langsung di peramban web (browser).
3. Anda dapat memilih membuka **Versi RENTAN** atau **Versi AMAN**.
