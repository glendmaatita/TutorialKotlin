# Constructor

_Constructor_ adalah fungsi di dalam _class_ yang dipanggil untuk membuat suatu _object_ dari _class_ tersebut. Sebagai sebuah fungsi, _constructor_ dapat menerima _parameter_, namun tidak dapat mengembalikan nilai. 

Secara _default_ tiap _class_ yang kita buat di Kotlin sudah mempunyai _constructor_ di dalamnya, walaupun kita buat class yang bentuknya paling sederhana sekalipun

```kotlin
package main

fun main() {
    val batman = Hero()
}

class Hero
```

Kita dapat membuat _constructor_ pada _class_ yang kita buat untuk dapat menerima parameter. Akibatnya, saat membuat _object_ dari _class_ tersebut, kita juga harus mem-passing nilai untuk _parameter_ dari _constructor_

```kotlin
package main

fun main() {
    val batman = Hero("Bruce")
}

class Hero(name: String)
```

Parameter ini tidak dibatasi tipe data dan jumlahnya. Kita dapat membuat _constructor_ dengan parameter tak terbatas, baik secara jumlah maupun tipe datanya.

```kotlin
package main

fun main() {
    val batman = Hero("Bruce", 40, false)
}

class Hero(name: String, age: Int, isSuperhuman: Boolean)
```

Kita juga dapat membuat beberapa _constructor_, agar class tersebut dapat di-_instance_ dengan beberapa macam cara. 

_Class_ di Kotlin mempunyai dua tipe _constructor_, yaitu _primary constructor_ dan _secondary constructor_. _Secondary constructor_ sifatnya opsional, sedangkan _primary constructor_ akan selalu ada di setiap class yang kita buat

_Primary constructor_ ditulis setelah nama _class_, sedangkan _secondary constructor_ ditulis di dalam body _class_. Keduanya memerlukan kata kunci _constructor_. _Secondary constructor_ harus memanggil _primary constructor_, ditandai dengan keyword `this`

```kotlin
package main

fun main() {
    // membuat object dengan memanggil secondary constructor
    val batman = Hero("Bruce", 40) 
    
    // membuat object dengan memanggil primary constructor
    val superman = Hero("Clark")
}

class Hero constructor (name: String) {
    constructor(name: String, age: Int): this(name)
}
```

{% hint style="info" %}
Jika sebuah _class_ hanya memiliki satu _constructor_, otomatis _constructor_ tersebut akan menjadi _primary constructor,_ dan tidak memerlukan kata kunci _constructor_ seperti contoh-contoh sebelumnya
{% endhint %}

### Init

Meskipun _constructor_ adalah fungsi di dalam _class_ yang pertama kali dipanggil, namun di Kotlin, kita tidak bisa menempatkan kode di dalam _constructor_. Lalu, bagaimana caranya supaya kita ingin agar ada kode kita yang dieksekusi begitu object dibuat? Caranya adalah menempatkan kode kita tersebut di dalam blok `init`

```kotlin
class Hero constructor (name: String) {
    constructor(name: String, age: Int): this(name)
    
    init {
        // kode disini akan dieksekusi begitu object dibuat
        // dari class ini
        print("Object of Hero is created")
    }
}
```



