# praktikum4
## Nama : Fahmi Arifin 
## Nim  : 312310662  
## Kelas : TI.23.A.6



## Deskripsi Program
Program ini bertujuan untuk menghitung luas dan keliling beberapa bentuk geometri (Lingkaran, Segitiga, dan Persegi) menggunakan konsep inheritance dan polymorphism di Java.

## Struktur Kelas
- **BangunDatar**: Kelas abstrak dengan metode abstrak `luas()` dan `keliling()`.
- **Lingkaran**: Menghitung luas dan keliling lingkaran.
- **Segitiga**: Menghitung luas dan keliling segitiga (diasumsikan segitiga sama sisi).
- **Persegi**: Menghitung luas dan keliling persegi.

## Hasil Eksekusi Program
![Cuplikan layar 2024-10-28 202652](https://github.com/user-attachments/assets/78217023-74e0-4539-910a-dc24eef65ac8)

## kode
```
// Class BangunDatar
abstract class BangunDatar {
    abstract float luas();
    abstract float keliling();
}

// Class Lingkaran
class Lingkaran extends BangunDatar {
    int r;

    Lingkaran(int r) {
        this.r = r;
    }

    @Override
    float luas() {
        return (float) (Math.PI * r * r);
    }

    @Override
    float keliling() {
        return (float) (2 * Math.PI * r);
    }
}

// Class Segitiga
class Segitiga extends BangunDatar {
    int alas, tinggi;

    Segitiga(int alas, int tinggi) {
        this.alas = alas;
        this.tinggi = tinggi;
    }

    @Override
    float luas() {
        return (float) (0.5 * alas * tinggi);
    }

    @Override
    float keliling() {
        // Asumsi segitiga sama sisi untuk memudahkan perhitungan
        return 3 * alas;
    }
}

// Class Persegi
class Persegi extends BangunDatar {
    int sisi;

    Persegi(int sisi) {
        this.sisi = sisi;
    }

    @Override
    float luas() {
        return sisi * sisi;
    }

    @Override
    float keliling() {
        return 4 * sisi;
    }
}

// Class Utama
public class Utama {
    public static void main(String[] args) {
        BangunDatar lingkaran = new Lingkaran(7);
        BangunDatar segitiga = new Segitiga(5, 10);
        BangunDatar persegi = new Persegi(4);

        System.out.println("Luas Lingkaran: " + lingkaran.luas());
        System.out.println("Keliling Lingkaran: " + lingkaran.keliling());
        
        System.out.println("Luas Segitiga: " + segitiga.luas());
        System.out.println("Keliling Segitiga: " + segitiga.keliling());

        System.out.println("Luas Persegi: " + persegi.luas());
        System.out.println("Keliling Persegi: " + persegi.keliling());
    }
}
