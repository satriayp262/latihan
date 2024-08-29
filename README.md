# latihan

```mermaid
erDiagram
    %% Entitas Prodi
    PRODI {
        string id_prodi
        string kode_prodi
        string nama_prodi
    }
    PRODI ||--o{ DOSEN : mengawasi
    PRODI ||--o{ MAHASISWA : terdaftar_di
    PRODI ||--o{ KELAS : menawarkan
    PRODI ||--o{ MATKUL : menyediakan
    PRODI ||--o{ KURIKULUM : menggunakan

    %% Entitas Dosen
    DOSEN {
        string id_dosen
        string nama
        string NIDN
        string jenis_kelamin
        string jabatan_fungsional
        string kepangkatan
        string kode_prodi
    }
    DOSEN ||--o{ MATKUL : mengajar

    %% Entitas Mahasiswa
    MAHASISWA {
        string id_mahasiswa
        string NIM
        string nama
        string tempat_lahir
        string tanggal_lahir
        string jenis_kelamin
        string NIK
        string agama
        string alamat
        string NISN
        string jalur_pendaftaran
        string kewarganegaraan
        string jenis_pendaftaran
        string tanggal_masuk_kuliah
        string mulai_semester
        string telp_rumah
        string no_hp
        string email
        string terima_kps
        string no_kps
        string kode_prodi
        string nama_prodi
        string SKS_diakui
        string kode_pt_asal
        string nama_pt_asal
        string kode_prodi_asal
        string nama_prodi_asal
        string jenis_pembiayaan
        string jumlah_biaya_masuk
    }
    MAHASISWA ||--o{ KRS : mendaftar_pada
    MAHASISWA ||--o{ NILAI : menerima
    MAHASISWA ||--o{ LULUSDO : lulus_dari

    %% Entitas KRS
    KRS {
        string id_krs
        string NIM
        string nama
        string semester
        string kode_mata_kuliah
        string nama_mata_kuliah
        string nama_kelas
        string kode_prodi
        string nama_prodi
        string nilai_huruf
        string nilai_indeks
        string nilai_angka
    }
    KRS ||--o{ MATKUL : terdaftar_di

    %% Entitas Kelas
    KELAS {
        string kode_kelas
        string lingkup_kelas
        string mode_kuliah
        string kode_prodi
        string nama_prodi
        string sks_tatap_muka
        string sks_praktek
        string sks_praktek_lapangan
        string sks_simulasi
    }
    KELAS ||--o{ NILAI : memiliki
    KELAS ||--o{ MATKUL : menawarkan

    %% Entitas Mata Kuliah
    MATKUL {
        string id_mata_kuliah
        string kode_mata_kuliah
        string nama_mk
        string jenis_mk
        string sks_tatap_muka
        string sks_praktek
        string sks_prak_lapangan
        string sks_simulasi
        string metode_pembelajaran
        string tgl_mulai_efektif
        string tgl_akhir_efektif
        string kode_prodi
        string nama_prodi
    }
    MATKUL ||--o{ NILAI : dinilai_oleh
    MATKUL ||--o{ EVALUASI : dinilai_dengan
    MATKUL ||--o{ KURIKULUM : termasuk_dalam

    %% Entitas Nilai
    NILAI {
        string id_nilai
        string NIM
        string nama_mahasiswa
        string kode_mata_kuliah
        string nama_mata_kuliah
        string semester
        string nama_kelas
        string nilai_huruf
        string nilai_indeks
        string nilai_angka
        string aktivitas_partisipatif
        string hasil_proyek
        string quiz
        string tugas
        string UTS
        string UAS
        string kode_prodi_mahasiswa
        string nama_prodi_mahasiswa
        string kode_prodi_kelas
        string nama_prodi_kelas
    }

    %% Entitas Kurikulum
    KURIKULUM {
        string id_kurikulum
        string nama_kurikulum
        string mulai_berlaku
        string jumlah_sks_lulus
        string jumlah_sks_wajib
        string jumlah_sks_pilihan
        string kode_prodi
        string nama_prodi
    }
    KURIKULUM ||--o{ PRODI : diterapkan_pada

    %% Entitas Evaluasi
    EVALUASI {
        string id_evaluasi
        string kode_mata_kuliah
        string nama_mata_kuliah
        string jenis_evaluasi
        string nama_evaluasi
        string deskripsi_indonesia
        string deskripsi_inggris
        string bobot
        string nomor_urut
        string kode_prodi
        string nama_prodi
    }

    %% Entitas Lulusdo
    LULUSDO {
        string id_lulusdo
        string NIM
        string nama
        string jenis_keluar
        string periode_keluar
        string tanggal_keluar
        string sk_yudisium
        string tanggal_sk_yudisium
        string ipk
        string no_seri_ijasah
        string kode_prodi
        string nama_prodi
        string keterangan_kelulusan
    }
