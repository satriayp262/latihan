# latihan

```mermaid
erDiagram
    PRODI ||--o{ MAHASISWA : enrolls
    PRODI ||--o{ MATKUL : offers
    DOSEN ||--o{ KELAS : teaches
    MATKUL ||--o{ KELAS : contains
    MAHASISWA ||--o{ KRS : registers
    KRS ||--o{ MATKUL : selects
    KELAS ||--o{ NILAI : assigns
    MAHASISWA ||--o{ NILAI : receives

    PRODI {
        int prodiID
        string namaProdi
    }
    MAHASISWA {
        int mahasiswaID
        string namaMahasiswa
        int prodiID
    }
    DOSEN {
        int dosenID
        string namaDosen
    }
    MATKUL {
        int matkulID
        string namaMatkul
        int prodiID
    }
    KELAS {
        int kelasID
        int matkulID
        int dosenID
        string waktu
    }
    KRS {
        int krsID
        int mahasiswaID
        int semester
    }
    NILAI {
        int nilaiID
        int mahasiswaID
        int kelasID
        string nilai
    }
