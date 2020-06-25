# Ekspresi Lompatan

Kotlin mempunyai 3 ekspresi lompatan, yaitu `return`, `break`, dan `continue` . Ekspresi ini umumnya digunakan untuk memanipulasi _flow_ di dalam program. Kita bisa menghentikan _flow_ atau melanjutkan _flow_ dalam kondisi tertentuk menggunakan 3 ekspresi ini.

### return 

`return`  digunakan untuk menghentikan dan mengembalikan nilai dari suatu fungsi. 

```kotlin
package main

fun main() {
    val results = calculate(5, 3) // 15
}

fun calculate(x: Int, y: Int):Int {
    return x * y
}
```

Kapanpun `return` dieksekusi, fungsi tersebut otomatis akan berhenti dan mengembalikan nilai

```kotlin
package main

fun main() {
    val results = calculate(5, 3) // 0
}

fun calculate(x: Int, y: Int):Int {
    if (x > y) {
        return 0
    }
    
    val result = x * y
    return result
}

```

{% hint style="info" %}
 Pada kondisi diatas, karena `x > y`, bernilai true maka fungsi `calculate()` akan mengembalikan nilai `0` dan berhenti, tanpa mengeksekusi kode dibawahnya
{% endhint %}

Kita juga dapat memanfaatkan return untuk sekedar menghentikan flow di dalam suatu fungsi tanpa mengembalikan nilai apapun

```kotlin
package main

fun main() {
    printMe("Bison")
}

fun printMe(name: String) {
    if (name == "Bison") {
        println("You are not a hero")
        return
    }

    println("You are amazing hero $name")
}
```

Hal ini berlaku pula di dalam suatu iterasi. Iterasi otomatis terhenti jika ada return dieksekusi

```kotlin
package main

fun main() {
    for(i in 1..10) {
        println(i)
        if (i == 5) {
            return
        }
    }
    
    println("Ini tidak akan tereksekusi")
}
```

### break

Berbeda dengan `return` yang menghentikan _flow_ di dalam suatu fungsi, `break` hanya bisa digunakan untuk menghentikan suatu iterasi

```kotlin
package main

fun main() {
    for(i in 1..10) {
        println(i)
        if (i == 5) {
            break
        }
    }
    
    println("Ini juga akan tereksekusi")
}
```

### continue

continue digunakan di dalam suatu iterasi untuk untuk meneruskan looping dan mengabaikan eksekusi berikutnya

```kotlin
package main

fun main() {
    for(i in 1..5) {
        if (i == 2) {
            continue
        }
        println(i)
    }
}
```

Kode diatas akan menampilkan angka `1, 3, 4, 5` secara berurutan. Angka `2` akan dilewati.

