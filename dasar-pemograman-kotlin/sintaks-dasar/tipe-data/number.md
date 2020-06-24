# Number

Tipe data _Number_ adalah tipe data yang berkaitan dengan angka, termasuk di dalamnya adalah integer, float, double, ataupun long. Kita akan bahas satu per satu

### Bilangan Bulat

Bilangan bulat atau disebut Integer mungkin adalah tipe data berformat Number yang paling sering dipakai. Kotlin mendukung setidaknya 4 macam tipe data bilangan bulat yang masing-masing dibedakan berdasarkan ukuran bit pada _memory_ 

| Tipe  | Nilai Minimal | Nilai Maksimal |
| :--- | :--- | :--- |
| Byte | -127 | 127 |
| Short | -32768 | 32768 |
| Int | -2.147.483.648 | 2.147.483.647 |
| Long | -9.223.372.036.854.775.808 | 9.223.372.036.854.775.808 |

Jadi kita mesti perlu benar-benar memikirkan kira-kira variabel kita akan berisi value seperti apa, sebelum kita menentukan tipe datanya

```kotlin
val inum: Int = 2000 // benar
val snum: Short = 50000 // salah
val bnum: Byte = 100 // benar
```

Jika kita tidak menyertakan tipe data saat deklarasi variabel, Kotlin akan secara cerdas menentukan tipe data suatu variabel berdasarkan nilai dari variabel tersebut. Jika nilai suatu variabel berada pada _range_ `Int`, maka secara otomatis variabel tersebut akan bertipe `Int`. Jika melebih range dari `Int`, maka Kotlin akan memberikan tipe data `Long` pada variabel tersebut

```kotlin
val snum = 30 // integer
val bnum = 100 // integer
val lnum = 9223372036854775804 // long
```

Bagaimana jika kita ingin membuat variabel bertipe `Long` namun nilainya masih dalam _range_ `Int` ? Ada dua cara. Pertama kita sertakan secara eksplisit tipe datanya saat mendeklarasikan variabel. Kedua dengan memberi tanda `L` setelah nilai variabel

```kotlin
val lnum: Long = 20 // Long
val longNum = 20L // Long
```

### Bilangan Desimal

Bilangan desimal adalah bilangan yang mempunyai pecahan seperti `5.4`, `6.8`, dan lain sebagainya. Kotlin mendukung setidaknya dua tipe data untuk bilangan desimal yaitu `Float` dan `Double` yang masing-masing dibedakan oleh jumlah presisi pecahannya, seperti terlihat pada tabel berikut

| Tipe | Digit Desimal |
| :--- | :--- |
| Float | 7 |
| Double | 16 |

Tiap deklarasi variabel yang bernilai bilangan desimal akan dianggap Kotlin mempunyai tipe data `Double`, kecuali jika kita secara implisit mendeklarasikan tipe datanya. 

Pada contoh dibawah, variabel `height` akan bertipe data `Double` karena kita tidak secara implisit mendeklarasikan variabel bertipe `Float` atau `Double`. Untuk mendeklarasikan variabel bertipe `Float` ada 2 cara, yaitu secara implisit menentukan tipe data variabel, yang kedua dengan menambahkan huruf `F` di belakang nilai sebuah variabel

```kotlin
val height = 4.5 // double
val myWeight: Float = 15.798 // float
val yourWeight = 16.893F // float
```

#### Konversi antar bilangan

Kotlin menyediakan fungsi-fungsi yang melekat pada semua variabel bertipe `Number` untuk mengkonversi nilai suatu variabel dengan tipe bilangan tertentu ke tipe bilangan lainnya. 

```kotlin
val weight = 4.5
val bweight = weight.toByte() // 4
val sweight = weight.toShort()) //4 
val iweight = weight.toInt()) // 4
val lweight = weight.toLong()) // 4
val fweight = weight.toFloat()) // 4.5

val height = 123
val bheight = height.toByte()) // 123
val sheight = height.toShort()) // 123
val lheight = height.toLong()) // 123
val fheight = height.toFloat()) //123.0
val dheight = height.toDouble()) // 123.0
```

