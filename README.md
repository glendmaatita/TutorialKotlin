# Pengenalan Kotlin

### Sejarah

Kotlin dikenalkan oleh sebuah perusahaan pembuat IDE terkemuka bernama [Jetbrains](https://www.jetbrains.com/) pada tahun 2011. Setelah itu, Kotlin dikembangkan secara intensif di dalam internal JetBrains sampai release stable versi pertamanya pada tahun 2016.  Sejak saat itu, Kotlin mendapat perhatian dan sorotan dari berbagai kalangan dan komunitas developer sampai pada puncaknya di tahun 2017, pada acara Google I/O, Google mengumumkan bahwa Kotlin akan mendapat dukungan _first-class_ untuk pengembangan Android. 

Artinya, framework Android, beserta seluruh library yang akan dirilis Google di masa mendatang akan sepenuhnya kompatibel dengan Kotlin. Google juga secara langsung menyarankan Android developer untuk menggunakan Kotlin dalam pengembangan aplikasi Android.

### Desain bahasa pemograman Kotlin

Kotlin adalah bahasa pemograman _cross-platform_. Kode Kotlin bisa di-_compile_ untuk digunakan pada platform Android, iOS, Server Side/Backend Application \(jalan diatas Java Virtual Machine\), maupun langsung ke Native OS seperti Windows, Linux, atau MacOS. Sederhananya, dengan menguasai bahasa Kotlin, kita dapat dengan mudah membuat aplikasi untuk berbagai macam target platform, baik itu native OS, backend, maupun mobile app. Menarik bukan?

### Null Safety

Kotlin menyediakan beberapa mekanisme untuk menghindari runtime error yang paling terjadi di Java, yaitu _NullPointerException._ Error ini terjadi umumnya karena faktor yang sepele yaitu tidak adanya pengecekan terlebih dahulu sebelum memanggil fungsi dari suatu object. Bagaimana cara Kotlin membantu programmer untuk menghindari error ini ?

Caranya _****_adalah dengan membedakan tipe data menjadi dua, yang bisa mengandung nilai `null` \(atau biasa disebut _nullable_\) dan tidak bisa mengandung nilai `null`. Tipe data yang bisa mengandung `null` dicirikan dengan suffix `?`

```kotlin
val name: String = null // compile error
val myName: String? = null // compile success

val age: Int = null // compile error
val myAge: Int? = null // compile success
```

Pembedaan dua tipe data _nullable_ dan tidak berlaku secara menyeluruh termasuk pengecekan parameter pada suatu fungsi. 

```kotlin
val name: String = "Ryu"
val myName: String? = null

printMyName(name) // compile success
printMyName(myName) // compile error

fun printMyName(name: String) {
    print(name)
}
```

Pertanyaannya, bagaimana kemudian jika kita ingin membuat fungsi `printMyName` diatas bekerja untuk variabel `myName` ? Untuk kasus ini terdapat dua cara, _pertama_ dengan melakukan pengecekan _null_ terlebih dahulu, dan _kedua_ kita bisa mengkonversi tipe _nullable_ ke _non-nullable_ dengan menggunakan operator `!!` 

```kotlin
val myName: String? = null

// cara pertama
if (myName != null) {
    printMyName(myName)
}

// cara kedua
printMyName(myName!!)

fun printMyName(name: String) {
    print(name)
}
```

#### Safety Call

 Adanya pembedaan ini membuat kita bisa memanfaatkan fitur yang dinamakan _safety call_. Fitur ini membuat pemanggilan fungsi dari suatu variabel yang nilainya `null` menjadi aman. Kotlin terlebih dahulu akan mengecek, apakah variabel tersebut nilanya `null`. Jika iya, maka tidak akan ada pemanggilan fungsi

```kotlin
val name: String? = null
name?.capitalize() // tidak dipanggil jika name == null
```

{% hint style="info" %}
Pada contoh diatas, fungsi `capitalize()` hanya akan dipanggil jika variabel `name` isinya tidak null
{% endhint %}



