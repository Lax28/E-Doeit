# E-Doeit

Final Projek untuk mata kuliah Pemograman Integratif kelompok 10

## Anggota Kelompok 10

Richard Nicolas - 5027201021
Muhammad Jovan Adiwijaya Yanuarsyah - 5027201025
Dzaki Indra Cahya - 5027201053

{(E-Doeit)} = https://e-doeit.herokuapp.com/api/

## Dokumentasi API

### Registrasi
**Endpoint**:https://e-doeit.herokuapp.com/api/registrasi
**Method**: POST
**Body Request**: Name, Email, dan Pass
**Authorization**: -

**Contoh**:

```
{
    "name":"ric",
    "pass": "ric",
    "email": "ric@gmail"
}
```

**Server Response**:

*BERHASIL*
 ```
 {
    "status": 200,
    "message": "Pendaftaran Berhasil"
}
 ```
 
 *ERROR*
 ```
 {
    "status": 400,
    "message": "Email sudah pernah didaftarkan, silahkan gunakan email lain"
}
 ```
 
 
 ### Login
**Endpoint**:https://e-doeit.herokuapp.com/api/login
**Method**: POST
**Body Request**: Email dan Pass
**Authorization**: -

**Contoh**:

```
{
    "email": "ric@gmail",
    "pass": "ric"
}
```

**Server Response**:

*BERHASIL*
 ```
{
    "status": 200,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZF91c2VyIjoyMSwibmFtZSI6InJpYyIsImVtYWlsIjoicmljQGdtYWlsIiwibm9tb3Jfd2FsbGV0IjoiN1F1SHM4VEhEdiIsImlhdCI6MTY1NTI2MDUwNSwiZXhwIjoxNjU1MjY0MTA1fQ.VsnClzCvXvlaKhxPNo-YUoq5hGlqqqMG7XS0dJnIreY"
}
 ```
 
 *ERROR*
 ```
 {
    "status": 400,
    "message": "Gagal Login, Username atau Password salah"
}
 ```

 ### TopUp
**Endpoint**: https://e-doeit.herokuapp.com/api/topup
**Method**: POST
**Body Request**: Jumlah
**Authorization**: Token JWT

**Contoh**:

```
{
    "jumlah": 100000
}
```

**Server Response**:

*BERHASIL*
 ```
{
    "status": 200,
    "message": "Top Up Berhasil"
}
 ```
 
 *ERROR*
 ```
 {
    "status": 400,
    "message": "token tidak valid"
}
 ```
 
  ### Transfer
**Endpoint**: https://e-doeit.herokuapp.com/api/transfer
**Method**: POST
**Body Request**: id_tujuan, jumlah dan keterangan
**Authorization**: Token JWT

**Contoh**:

```
{
    "id_tujuan": 18,
    "jumlah": 5000,
    "keterangan":"transfer"
}
```

**Server Response**:

*BERHASIL*
 ```
{
    "status": 200,
    "message": "Berhasil transfer"
}
 ```
 
 *ERROR*
 ```
 {
    "status": 400,
    "message": "Saldo tidak mencukupi, silahkan topup"
}
 ```
 
### Payment
**Endpoint**: https://e-doeit.herokuapp.com/api/pay
**Method**: POST
**Body Request**: id_tujuan, jumlah dan keterangan
**Authorization**: Token JWT

**Contoh**:

```
{
    "jumlah": 5000,
    "keterangan":"tes"
}
```

**Server Response**:

*BERHASIL*
 ```
{
    "status": 200,
    "message": "Berhasil bayar"
}
 ```
 
 *ERROR*
 ```
 {
    "status": 400,
    "message": "Saldo tidak mencukupi, silahkan topup"
}
 ```
 
 ### History
**Endpoint**: https://e-doeit.herokuapp.com/api/history
**Method**: GET
**Body Request**: -
**Authorization**: Token JWT

**Server Response**:

*BERHASIL*
 ```
[
    {
        "id_transaksi": 70,
        "id_user": 21,
        "jumlah": 100000,
        "tipe": 1,
        "keterangan": "topup",
        "waktu": "2022-06-07T02:29:15.000Z"
    },
    {
        "id_transaksi": 71,
        "id_user": 21,
        "jumlah": 5000,
        "tipe": 2,
        "keterangan": "tes",
        "waktu": "2022-06-07T02:29:59.000Z"
    },
    {
        "id_transaksi": 73,
        "id_user": 21,
        "jumlah": 5000,
        "tipe": 3,
        "keterangan": "transfer ke id 18",
        "waktu": "2022-06-07T02:30:25.000Z"
    },
    {
        "id_transaksi": 155,
        "id_user": 21,
        "jumlah": 100000,
        "tipe": 1,
        "keterangan": "topup",
        "waktu": "2022-06-15T02:39:44.000Z"
    },
    {
        "id_transaksi": 157,
        "id_user": 21,
        "jumlah": 5000,
        "tipe": 3,
        "keterangan": "transfer ke id 18",
        "waktu": "2022-06-15T02:44:22.000Z"
    },
    {
        "id_transaksi": 158,
        "id_user": 21,
        "jumlah": 5000,
        "tipe": 2,
        "keterangan": "tes",
        "waktu": "2022-06-15T02:48:16.000Z"
    }
]
 ```
 
 *ERROR*
 ```
 {
    "status": 400,
    "message": "token tidak valid"
}
 ```
 
 
 
