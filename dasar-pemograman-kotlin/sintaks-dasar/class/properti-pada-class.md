# Properti & Fungsi di Class

_Class_ dapat mempunyai properti yang nantinya akan digunakan oleh _object_ untuk menyimpan data. Properti berbentuk variabel yang didefinisikan di awal _class_.

```kotlin
class Hero constructor (name: String, age: Int) {
    val life: Int = 100
    var punchPower: Int = 0
}
```

Properti dapat diakses maupun diubah di dalam _class_ maupun di luar _class_

```kotlin
package main

fun main() {
    val batman = Hero("Bruce")
    
    // mengakses properti dari luar class
    batman.life = 50
    
    println(batman.life)
}

class Hero (name: String) {
    var life: Int = 100
    
    fun punchMe(power: Int) {
        // mengakses dan mengubah properti dari dalam class
        life =- power
    }
}
```

Untuk fungsi, pendefinisiannya diawali dengan keyword `fun`. Kemudian diikuti dengan nama fungsi. Dilanjutkan dengan parameter fungsi. Dan diakhiri dengan tipe data dari nilai kembalian fungsi tersebut.

```kotlin
class Hero constructor (name: String, age: Int) {
    val life: Int = 100
    var punchPower: Int = 0
    
    fun punchMe(power: Int): Int {
        life =- power
        return life
    }
    
    fun increaseLife(blood: Int) {
        life += blood
    }
    
    fun decreaseLif(blood: Int): Void {
        life -= blood
    }
}
```

{% hint style="info" %}
Fungsi `increaseLife` secara implisit tidak tertulis tipe data kembalian. Untuk kasus semacam ini, Kotlin secara otomatis menambahkan `Void` sebagai tipe data kembalian seperti pada fungsi `decreaseLife`
{% endhint %}

Sama seperti properti, fungsi juga dapat diakses dari dalam maupun luar _class_

```kotlin
package main

fun main() {
    val batman = Hero("Bruce")
    
    // mengakses fungsi dari luar class
    batman.softPunch()
}

class Hero (name: String) {
    var life: Int = 100

    fun punchMe(power: Int) {
        // mengakses dan mengubah properti dari dalam class
        life =- power
    }
    
    fun softPunch() {
        // mengakses fungsi dari dalam class
        punchMe(10)
    }
}
```

 

