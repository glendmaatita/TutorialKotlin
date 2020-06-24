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



