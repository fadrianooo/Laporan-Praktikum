# <h1 align="center">Laporan Praktikum Modul 1 - Codeblocks IDE & Pengenalan Bahasa C++ (Bagian Pertama)</h1>
<p align="center">Fadriano Bumindra Abiyyu - 109082500170</p>

## Dasar Teori
C++ adalah bahasa pemrograman yang bisa dipakai untuk membuat program dengan variabel, tipe data, operator, serta input dan output[3].

### A. Input dan Output pada C++<br/>
Input adalah data yang dimasukan kedalam program, sedangkan output adalah hasil yang ditampilkan program kepada pengguna[6].
#### 1. Library iostream
iostream adalah library yang ditulis di awal program agar cin dan cout bisa dipakai.
#### 2. Output dengan cout
cout digunakan untuk menampilkan tulisan atau isi variabel. Penulisanya menggunakan tanda <<. Lalu jika ingin menampilkan teks dan variabel sekaligus, keduanya dipisah dengan << [3].
#### 3. Input dengan cin
cin digunakan untuk membaca data yang diketik pengguna. Penulisanya menggunakan tanda >> [3]. Kemudian data yang diketik akan disimpan di dalam variabel[6].

### B. Tipe Data dan Operator<br/>
Tipe data adalah nilai yang bisa di simpan oleh sebuah variabel[4].
#### 1. Tipe Data int dan float
int digunakan untuk bilangan bulat. float digunakan untuk bilangan pecahan atau desimal[3].
#### 2. Operator aritmatika
Operator aritmatika digunakan untuk melakukan perhitungan matematika seperti tambah(+), kurang(-), kali(*), bagi(/), dan sisa bagi atau modulus(%)[3].
#### 3. Percabangan dan Perulangan
percabangan seperti if, else, else if digunakan agar program bisa memilih tindakan sesuai dengan kondisi. Perulangan for digunakan untuk mengulang perintah beberapa kali.

## Guided 

### 1. 

```C++
#include <iostream>
using namespace std;
int main(){
    cout << "Hello world" << endl;
    return 0;
}
```
Program ini bertujuan untuk menampilkan teks, menggunakan cout untuk mencetak kalimat "Hello world", kemudian endl untuk berpindah ke baris baru.

### 2. 

```C++
#include <iostream>
using namespace std;
int main(){
    int inp;
    cin >> inp;
    cout << "nilai = " << inp;
    return 0;
}
```
Program ini bertujuan untuk menerima input angka dari pengguna dan menampilkan ke layar. Variabel inp memiliki tipe data int digunakan untuk menyimpan angka bilangan bulat yang di inputkan lewat perintah cin.

### 3. 

```C++
#include <iostream>
using namespace std;
int main() {
  float W, X, Y, Z;
  X = 7; Y = 3; W = 1;
  Z = (X + Y) / (Y + W);
  cout<< "Nilai z = " << Z << endl;
  return 0;
}
```
Program ini bertujuan untuk mengoperasikan aritmatika dasar, variabel W, X, Y, Z bertipe data float agar nanti hasilnya bisa menjadi desimal. Pertama program melakukan penjumlahan dan pembagian (7 + 3)/(3 + 1) kemudian menghasilkan 10/4 = 2.5, dan menampilkan hasilnya menggunakan perintah cout.

## Unguided 

### 1. Buatlah program yang menerima input-an dua buah bilangan bertipe float, kemudian memberikan output-an hasil penjumlahan, pengurangan, perkalian, dan pembagian dari dua bilangan tersebut.

```C++
#include <iostream>
using namespace std;

int main() {
    float a, b;

    cout << "Masukkan bilangan pertama : ";
    cin >> a;
    cout << "Masukkan bilangan kedua   : ";
    cin >> b;

    cout << "Penjumlahan : " << a + b << endl;
    cout << "Pengurangan : " << a - b << endl;
    cout << "Perkalian   : " << a * b << endl;
    cout << "Pembagian   : " << a / b << endl;

    return 0;
}
```
### Output Unguided 1 :
bilangan pertama = 10
bilangan kedua = 5
penjumlahan = 10 + 5 = 15
pengurangan = 10 - 5 = 5
perkalian = 10 * 5 = 50
pembagian = 10 / 5 = 2

##### Output 1
![Screenshot Output Unguided 1_1](https://github.com/fadrianooo/Laporan-Praktikum/blob/main/Praktikum-Modul-1/Output-Unguided-1_1.png)

Program ini ada dua variabel yaitu a dan b yang bertipe data float agar bisa menyimpan bilangan desimal. Kemudian a dan b diisi dengan cin, kemudian program menghitung dan menanpilkan hasilnya dengan cout. 

### 2. Buatlah sebuah program yang menerima masukan angka dan mengeluarkan output nilai angka tersebut dalam bentuk tulisan. Angka yang akan di-input-kan user adalah bilangan bulat positif mulai dari 0 s.d 100.

```C++
#include <iostream>
using namespace std;

void tulisAngka(int x) {
    if (x == 0) cout << "nol";
    else if (x == 1) cout << "satu";
    else if (x == 2) cout << "dua";
    else if (x == 3) cout << "tiga";
    else if (x == 4) cout << "empat";
    else if (x == 5) cout << "lima";
    else if (x == 6) cout << "enam";
    else if (x == 7) cout << "tujuh";
    else if (x == 8) cout << "delapan";
    else if (x == 9) cout << "sembilan";
}
int main() {
    int angka;
    cin >> angka;
    cout << angka << " : ";

    if (angka < 0 || angka > 100) {
        cout << "angka di luar 0 sampai 100";
    }
    else if (angka < 10) {
        tulisAngka(angka);
    }
    else if (angka == 10) {
        cout << "sepuluh";
    }
    else if (angka == 11) {
        cout << "sebelas";
    }
    else if (angka < 20) {
        tulisAngka(angka % 10);
        cout << " belas";
    }
    else if (angka < 100) {
        tulisAngka(angka / 10);
        cout << " puluh";
        if (angka % 10 != 0) {
            cout << " ";
            tulisAngka(angka % 10);
        }
    }
    else {
        cout << "seratus";
    }

    cout << endl;
    return 0;
}
```
### Output Unguided 2 :
input = 12
output = 12 : dua belas
##### Output 1
![Screenshot Output Unguided 2_1](https://github.com/fadrianooo/Laporan-Praktikum/blob/main/Praktikum-Modul-1/Output-Unguided-2_1.png)

Program membaca angka dari cin, lalu memeriksanya dengan if dan else if. Kemudian fungsi tulisAngka dibuat agar kata "satu" sampai "sembilan" tidak ditulis berulang kali. 

### 3. Buatlah program yang dapat memberikan input dan output sbb.

```C++
#include <iostream>
using namespace std;

int main() {
    int n;

    cout << "input: ";
    cin >> n;
    cout << "output:" << endl;

    for (int i = n; i >= 0; i--) {
        for (int s = 0; s < n - i; s++) {
            cout << " ";
        }
        for (int j = i; j >= 1; j--) {
            cout << j;
        }
        cout << "*";
        for (int j = 1; j <= i; j++) {
            cout << j;
        }
        cout << endl;
    }
    return 0;
}
```
### Output Unguided 3 :
input: 3
output:
321*123
 21*12
  1*1
   *
##### Output 1
![Screenshot Output Unguided 3_1](https://github.com/fadrianooo/Laporan-Praktikum/blob/main/Praktikum-Modul-1/Output-Unguided-3_1.png)

Program akan membaca angka n, lalu mencetak pola setiap baris. Pada setiap baris ada empat langkah, pertama mencetak spasi di depan sebanyak n-i agar polanya menjorok ketengah, kemudian mencetak angka dari i turun ke 1, mencetak tanda *, lalu mencetak angka dari 1 naik ke i.

## Kesimpulan
Kesimpulan dari praktikum ini, saya belajar menggunakan cin untuk memasukkan data dan cout untuk menampilkan hasil, serta memakai tipe data int dan float dan operator aritmatika dan percabangan dan perulangan.

## Referensi
[1] Triase. (2020). Diktat Edisi Revisi : STRUKTUR DATA. Medan: UNIVERSTAS ISLAM NEGERI SUMATERA UTARA MEDAN. 
<br>[2] Indahyati, Uce., Rahmawati Yunianita. (2020). "BUKU AJAR ALGORITMA DAN PEMROGRAMAN DALAM BAHASA C++". Sidoarjo: Umsida Press. Diakses pada 10 Maret 2024 melalui https://doi.org/10.21070/2020/978-623-6833-67-4.
<br>[3] Ma'arif, Alfian. "Buku Ajar Dasar Pemrograman C++". Program Studi Teknik Elektro, Universitas Ahmad Dahlan. Diakses pada 29 September 2026 melalui https://eprints.uad.ac.id/32726/1/Dasar%20Pemrograman%20Bahasa%20C++.pdf.
<br>[4] "Modul Dasar Pemrograman - Modul 1: Pengenalan Pemrograman". Jurusan Teknik Elektro, Universitas Negeri Malang. Diakses pada 29 September 2026 melalui https://elektro.um.ac.id/wp-content/uploads/2016/04/Dasar-Pemrograman-Modul-1-Pengenalan-Pemrograman.pdf.
<br>[5] "Pengenalan Bahasa C++" (modul praktikum). Diakses pada 29 September 2026 melalui https://www.slideshare.net/slideshow/pengenalan-bahasa-c-22250627/22250627.
<br>[6] "Pengertian dan Dasar Input Output C++". Belajar C++. Diakses pada 29 September 2026 melalui https://www.belajarcpp.com/tutorial/cpp/dasar-input-output/.
