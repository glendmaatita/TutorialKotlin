# Object

Terlebih dahulu, kita akan perjelas beberapa definisi. _Obyek_ adalah _instance_ dari sebuah _class_. Sedangkan _**Object**_ adalah topik bahasa bab ini.

Konsep _**Object**_ di Kotlin mirip dengan Javascript. Di Javascript, kita bisa membuat sebuah _obyek_, tanpa membuat _instance_ dari sebuah _class,_ konsep ini dinamakan **anonymous object** . Hal ini mirip dengan _**object**_ di Kotlin. Kita bisa membuat sebuah _obyek_ tanpa _class_. 

```kotlin
val person = object {
   val name: String = "Ryu"
   val age: Int = 40
}

println(person.name) // Ryu
println(person.age) 
```

_**Object**_ biasanya dipakai ketika ingin membuat sebuah obyek simple yang tidak memerlukan definisi _class_, atau ketika kita ingin membuat implementasi dari sebuah _Interface_ secara cepat tanpa repot membuat _class_ yang meng-_implement_ _Interface_ tersebut

Berikut adalah cara yang lebih panjang untuk mendapatkan sebuah _obyek_ dari _Interface_

```kotlin
package main

fun main() {
    val flash = Flash()
    flashPoint(flash)
}

fun flashPoint(runner: Speedster) {
    runner.runFast()
}

interface Speedster {
    fun runFast()
}

class Flash: Speedster {
    override fun runFast() {
        println("Run at 10000 km/second")
    }
}
```

Jika kita sekadar ingin dapat menjalankan fungsi `flashPoint()`, kita bisa menggunakan _**object**_ tanpa perlu membuat _class_ terlebih dahulu

```kotlin
package main

fun main() {
    flashPoint(object : Speedster {
        override fun runFast() {
            println("Run at 50000 km/second")
        }
    })
}

fun flashPoint(runner: Speedster) {
    runner.runFast()
}

interface Speedster {
    fun runFast()
}
```

### Scope Object

_Scope_ dari sebuah _**object**_ secara _default_ adalah _local_. Artinya, secara _default_, kita hanya dapat mengakses properti/fungsi dalam sebuah _**object**_ dari dalam fungsi yang sama

```kotlin
class Superman {
    val fly = object {
        val height: Int = 20000
        val speed: Int = 50000
    }
    
    fun showPower() {
        val power = object {
            var punch: Int = 5000
            var kick: Int = 7000
        }
        println("The power of his punch is ${power.punch}")
        println("The power of his lick is ${power.kick}")
    }
    
    fun showFly() {
        // error karena properti/fungsi dalam object
        // hanya bisa diakses secara local
        println("The speed of his fly is ${fly.speed}") 
    }
}
```

Kita harus secara implisit menandai bahwa suatu variabel _**object**_ adalah _class_ properti, dengan memberi _visibility modifier_ sebagai `private`

```kotlin
class Superman {
    private val fly = object {
        val height: Int = 20000
        val speed: Int = 50000
    }
    
    fun showPower() {
        val power = object {
            var punch: Int = 5000
            var kick: Int = 7000
        }
        println("The power of his punch is ${power.punch}")
        println("The power of his lick is ${power.kick}")
    }
    
    fun showFly() {
        // compile success
        println("The speed of his fly is ${fly.speed}") 
    }
}
```



