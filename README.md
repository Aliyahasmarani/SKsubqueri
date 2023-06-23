# SKsubqueri

```s
NAMA    : ALIYAH ASMARANI
NIM     : 312210203
KELAS   : TI.22.A.2
MATKUL  : BASIS DATA
```
# LATIHAN

### 1. Tampilkan data karyawan yang bekerja pada departemen yang sama dengan karyawan yang bernama Dika!
```
SELECT nik, nama, id_dept
    -> FROM karyawan
    -> WHERE id_dept = (
    ->   SELECT id_dept FROM karyawan
    ->   WHERE nama = 'Dika'
    -> );
```
![image](https://github.com/Aliyahasmarani/SKsubqueri/assets/115197672/b9de9c8a-24b0-43ce-9db4-2b1b8315228a)

### 2. Tampilkan data karyawan yang gajinya lebih besar dari rata-rata gaji semua karyawan. Urutkan menurun berdasarkan besaran gaji!
```
SELECT nik, nama, id_dept, sup_nik, gaji_pokok
    -> FROM karyawan
    -> WHERE gaji_pokok > (
    ->     SELECT AVG(gaji_pokok) FROM karyawan)
    -> ORDER BY gaji_pokok DESC;
```
![image](https://github.com/Aliyahasmarani/SKsubqueri/assets/115197672/a318e5e3-eb63-4082-8d40-f13fd516c7d5)

### 3. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di departement yang sama dengan karyawan dengan nama yang mengandung huruf 'K'!
```
SELECT nik, nama
    -> FROM karyawan
    -> WHERE id_dept IN (
    ->   SELECT id_dept FROM karyawan
    ->   WHERE nama LIKE '%k%'
    -> );
```
![image](https://github.com/Aliyahasmarani/SKsubqueri/assets/115197672/7e86c107-cbf3-4150-affc-bfaf136b7023)

### 4. Tampilkan data karyawan yang bekerja pada departemen yang ada di kantor pusat!
```
SELECT karyawan.nik, karyawan.nama, karyawan.id_dept
    -> FROM karyawan
    -> JOIN departemen ON karyawan.id_dept = departemen.id_dept
    -> WHERE departemen.id_p = 'P01';
```
![image](https://github.com/Aliyahasmarani/SKsubqueri/assets/115197672/bb49c008-2f8c-4ae7-9fe9-1ccd3e9a45aa)

### 5. Tampilkan nik dan nama karyawan untuk semua karyawan yang bekerja di departemen yang sama dengan karyawan dengan nama yang mengandung huruf 'K' dan yang gajinya lebih besar dari rata-rata gaji semua karyawan!
```








