# latihan

```mermaid
erDiagram
    PRODI ||--o{ DOSEN : memiliki
    PRODI ||--o{ MAHASISWA : terdaftar_di
    PRODI ||--o{ KRS : dikelola_oleh
    PRODI ||--o{ KELAS : menyelenggarakan
    PRODI ||--o{ MATA_KULIAH : menawarkan
    PRODI ||--o{ NILAI : terkait_dengan
    PRODI ||--o{ KURIKULUM : menggunakan

    MAHASISWA ||--o{ KRS : membuat
    MAHASISWA ||--o{ NILAI : menerima

    MATA_KULIAH ||--o{ KRS : termasuk_dalam
    MATA_KULIAH ||--o{ NILAI : dinilai_dalam

    PRODI {
        int id_prodi
        string kode_prodi
        string nama_prodi
    }

    DOSEN {
        int id_dosen
        string Nama
        string NIDN
        string Jenis_Kelamin
        string Jabatan_Fungsional
        string Kepangkatan
        int id_prodi
    }

    MAHASISWA {
        int id_mahasiswa
        string NIM
        string Nama
        string Tempat_Lahir
        date Tanggal_Lahir
        string Jenis_Kelamin
        string NIK
        string Agama
        string alamat
        string NISN
        string Jalur_Pendaftaran
        string Kewarganegaraan
        string Jenis_Pendaftaran
        date Tanggal_Masuk_Kuliah
        string Mulai_Semester
        string Telp_Rumah
        string No_HP
        string Email
        boolean Terima_KPS
        string No_KPS
        int id_prodi
    }

    KRS {
        int id_krs
        string NIM
        string Nama
        string Semester
        string Kode_Mata_Kuliah
        string Nama_Mata_Kuliah
        string Nama_Kelas
        int id_prodi
        char Nilai_Huruf
        float Nilai_Indeks
        float Nilai_Angka
    }

    KELAS {
        string Lingkup_Kelas
        string Mode_Kuliah
        int id_prodi
        int SKS_Tatap_Muka
        int SKS_Praktek
        int SKS_Praktek_Lapangan
        int SKS_Simulasi
    }

    MATA_KULIAH {
        int id_mata_kuliah
        string Kode_Mata_Kuliah
        string Nama_MK
        string Jenis_MK
        int SKS_Tatap_Muka
        int SKS_Praktek
        int SKS_Prak_Lapangan
        int SKS_Simulasi
        string Metode_Pembelajaran
        date Tgl_Mulai_Efektif
        date Tgl_Akhir_Efektif
        int id_prodi
    }

    NILAI {
        int id_nilai
        string NIM
        string Kode_Mata_Kuliah
        string Nama_Mata_Kuliah
        string Semester
        string Nama_Kelas
        char Nilai_Huruf
        float Nilai_Indeks
        float Nilai_Angka
        int id_prodi
    }

    KURIKULUM {
        int id_kurikulum
        string Nama_Kurikulum
        date Mulai_Berlaku
        int Jumlah_SKS_Lulus
        int Jumlah_SKS_Wajib
        int Jumlah_SKS_Pilihan
        int id_prodi
    }

