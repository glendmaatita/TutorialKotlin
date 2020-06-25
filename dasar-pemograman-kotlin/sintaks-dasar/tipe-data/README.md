# Tipe Data Dasar

Tipe data diberikan kepada suatu variabel agar kompiler mengetahui ekspektasi dari variabel tersebut. Artinya, bila suatu variabel kita beri suatu nilai `String`, maka kompiler akan mempunyai ekspektasi bahwa nilai dari variabel tersebut adalah kumpulan karakter, sehingga variabel tersebut hanya mempunyai properti khusus `String`. Begitu juga jika kita beri tipe data berupa `Integer` ataupun `Boolean`. 

Pemberian tipe data dilakukan saat deklarasi variabel

```kotlin
val name: String = "Ryu"
val age: Int = 20
val power: Long = 1000L
val height: Float = 10.5F
val weight: Double = 70.4
val isMale: Boolean = true
```

Sejauh ini Kotlin mempunyai tipe data dasar berupa `Number`, `Character`, `String`, dan `Boolean`. Number sendiri mempunyai sub tipe seperti _bilangan bulat_, yang terdiri dari `Byte`, `Short`, `Int`, dan `Long`,  serta _bilangan desimal_, yang terdiri dari `Float` dan `Double`.

