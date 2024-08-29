# latihan

```mermaid
erDiagram
    PRODI ||--o{ DOSEN : "has"
    PRODI ||--o{ MAHASISWA : "has"
    PRODI ||--o{ KELAS : "has"
    PRODI ||--o{ MATKUL : "has"
    PRODI ||--o{ KURIKULUM : "has"
    
    MAHASISWA ||--o{ KRS : "enrolls in"
    MAHASISWA ||--o{ NILAI : "receives"
    
    MATKUL ||--o{ KRS : "listed in"
    MATKUL ||--o{ NILAI : "evaluates"
    
    KRS {
        int id_krs
        string nim
        string nama
        string semester
        string kode_mata_kuliah
        string nama_mata_kuliah
        string nama_kelas
        string kode_prodi
        string nama_prodi
        string nilai_huruf
        string nilai_indeks
        int nilai_angka
    }
    
    PRODI {
        int id_prodi
        string kode_prodi
        string nama_prodi
    }
    
    DOSEN {
        int id_dosen
        string nama
        string nidn
        string jenis_kelamin
        string jabatan_fungsional
        string kepangkatan
        int prodi_id
    }
    
    MAHASISWA {
        int id_mahasiswa
        string nim
        string nama
        string tempat_lahir
        date tanggal_lahir
        string jenis_kelamin
        string nik
        string agama
        string nisn
        string jalur_pendaftaran
        string kewarganegaraan
        string jenis_pendaftaran
        date tanggal_masuk_kuliah
        string mulai_semester
        string telp_rumah
        string no_hp
        string email
        bool terima_kps
        string no_kps
        int prodi_id
    }
    
    MATKUL {
        int id_mata_kuliah
        string kode_mata_kuliah
        string nama_mk
        string jenis_mk
        int sks_tatap_muka
        int sks_praktek
        int sks_prak_lapangan
        int sks_simulasi
        string metode_pembelajaran
        date tgl_mulai_efektif
        date tgl_akhir_efektif
        int prodi_id
    }
    
    NILAI {
        int id_nilai
        string nim
        string nama_mahasiswa
        string kode_mata_kuliah
        string nama_mata_kuliah
        string semester
        string nama_kelas
        string nilai_huruf
        string nilai_indeks
        int nilai_angka
        int prodi_id
    }
    
    KURIKULUM {
        int id_kurikulum
        string nama_kurikulum
        date mulai_berlaku
        int jumlah_sks_lulus
        int jumlah_sks_wajib
        int jumlah_sks_pilihan
        int prodi_id
    }
    
    KELAS {
        string lingkup_kelas
        string mode_kuliah
        int prodi_id
        int sks_tatap_muka
        int sks_praktek
        int sks_praktek_lapangan
        int sks_simulasi
    }
