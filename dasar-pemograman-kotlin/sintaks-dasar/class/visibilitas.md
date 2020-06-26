# Visibilitas

Visibilitas menentukan hak akses atas suatu properti, fungsi, atau bahkan sebuah _class_. Di Kotlin ada 4 _visibility modifier_, yaitu `private`, `protected`, `public`, dan `internal`. Masing-masing mempunyai kegunaan dan manfaat masing-masing.

Untuk memberikan suatu visibilitas, cukup menambahkan _visibility modifier_ di awal deklarasi class/properti/fungsi.

```kotlin
class Person {
    val city: String = "Surabaya" // public
    public val name: String = "Ryu" // public
    private val age: Int = 35 // private
    protected val birthday: String = "1990-05-02" // protected
    internal val postalCode: String = "50235" // internal
    
    fun printName() {
        print(name)
    }
    
    private fun printAge() {
        print(age)
    }
}
```

{% hint style="info" %}
Default visibilitas adalah _public_. Jadi, jika kita tidak memberi _visibility-modifier_ saat pendeklarasian maka class/fungsi/properti tersebut akan dianggap _public_
{% endhint %}

### Visibilitas Public

Sesuai namanya, `public`, artinya bisa diakses dari mana saja. Properti dan Fungsi yang mempunyai visibilitas `public` dapat diakses di dalam maupun di luar _class_, bebas.

```kotlin
package main

fun main() {
    val person = Person()
    println(person.name)
    person.printName()
}

class Person{
    val name: String = "Ryu"
    fun printName() {
        println(name)
    }
}
```

Hal ini juga berlaku bagi _class_ yang berada di file lain ataupun _package_ lain

{% code title="Human.kt" %}
```kotlin
import Car.Mercedes

package Human

class Person {
    fun driving() {
        val car = Mercedes()
        car.driveMe()
    }
}
```
{% endcode %}

{% code title="Mercedes.kt" %}
```kotlin
package Car

class Mercedes {
    fun driveMe() {
        print("You are driving a Mercedes")
    }
}
```
{% endcode %}

### Visibilitas Private 

Jika _visibility-modifier_ `private` melekat ke fungsi atau properti dalam suatu _class_, artinya fungsi/properti hanya bisa diakses di dalam _class_ tersebut, tidak akan bisa diakses di luar _class_

```kotlin
package main

fun main() {
    val person = Person()
    // error, properti name hanya bisa diakses dari dalam class
    println(person.name)
    
    // error, fungsi printName hanya bisa diakses dari dalam class
    person.printName()
}

class Person{
    private val name: String = "Ryu"
    fun printName() {
        // properti name dapat diakses
        println(name)
    }
}
```

Sedangkan jika _visibility-modifier_ `private` melekat ke suatu _class_, artinya _class_ tersebut hanya bisa diakses oleh _class_ lain di dalam file yang sama

{% code title="MyCar.kt" %}
```kotlin
package mycar

class Driver {
    fun driving() {
        // class Jeep dapat diakses di file yang sama
        val jeepCar = Jeep()
    }
}

private class Jeep {
    fun drive() {
        print("I am driving Jeep")
    }
}
```
{% endcode %}

{% code title="YourCar.kt" %}
```kotlin
import mycar.Jeep

package yourcar

class Driver {
    fun driving() {
        // error, class Jeep hanya dapat diakses di file yang sama
        val jeepCar = Jeep()
    }
}
```
{% endcode %}

### Visibilitas Protected

Fungsi/properti dari suatu class yang mempunyai _visibility modifier_ sebagai `protected` akan dapat diakses dari dalam _class_ tersebut, sama seperti `private`, plus dapat diakses oleh class turunannya. Penjelasan mengenai _class_ turunan akan dijabarkan pada bab Pewarisan

{% code title="LuxuryCar.kt" %}
```kotlin
package luxcar

open class Mercedes {
    protected var speedPerHour = 500
    
    protected fun increaseSpeed(speed: Int) {
        speedPerHour += speed
    }
    
    fun driving() {
        print("I am driving on $speedPerHour km/h")         
    }
}

// class turunan dari class Mercedes
class MercedesTurbo: Mercedes() {
    private val turbo: Int = 5
    fun increaseSpeedWithTurbo(speed: Int) {
        // mengakses fungsi protected
        increaseSpeed(turbo * speed)
    }
}
```
{% endcode %}

{% code title="MyApplication.kt" %}
```kotlin
package main 

import LuxuryCar.MercedesTurbo

fun main() {
    val mercy = MercedesTurbo()
    mercy.driving() // driving in 500 km/h
    
    // let's drive faster
    mercy.increaseSpeedWithTurbo(500)
    mercy.driving() // driving in 1500 km/h
}
```
{% endcode %}

### Visibilitas Internal

_Modifier_ internal membatas pengaksesan pada suatu _class_/fungsi/properti menjadi terbatas hanya pada class di satu _module_. Mirip dengan `public`, namun ini terbatas dalam lingkup satu _module_

Apa itu _module_? _Module_ dalam Kotlin artinya sekumpulan kode yang di-_compile_ menjadi satu dan diatur dalam setting _build_ yang sama. Contoh misalnya, jika kita menggunakan suatu _library_ dalam program kita, maka _library_ tersebut adalah satu _module_ terpisah dari program kita. Jika ada _class_/properti/fungsi dalam _library_ tersebut yang memiliki _modifier_ `internal`, maka mereka hanya bisa diakses oleh kode-kode didalam _library_ itu saja, dan kita tidak bisa mengaksesnya dari program kita.

Untuk memakai _modifier_ ini, cukup dengan menggunakan kata kunci `internal`

{% code title="LuxuryCar.kt" %}
```kotlin
package luxcar

class Mercedes {
    protected var speedPerHour = 500
    
    protected fun increaseSpeed(speed: Int) {
        speedPerHour += speed
    }
    
    internal fun driving() {
        print("I am driving on $speedPerHour km/h")         
    }
}
```
{% endcode %}



