# Sealed Class

_Sealed Class_ hampir mirip dengan _Enum Class_. Jika pada _Enum Class_ kita mempunyai beberapa _object constant_ yang didefinisikan di dalam sebuah _class enum_, di _Sealed Class_ kita tidak hanya bisa punya _object constant_, namun juga _class_ yang harus didefinisikan di dalam satu file Kotlin.

Untuk mendefinisikan _Sealed Class,_ cukup dengan membuat sebuah _class_ yang diawali oleh kata kunci `sealed`. Selanjutnya kita tinggal membuat _class_ turunan dari _Sealed Class_ tersebut

{% code title="SuperheroDC.kt" %}
```kotlin
package dc.hero

// membuat sealed class
sealed class DCSuperhero

// membuat class turunan
class Batman(name: String, age: Int): DCSuperhero()
data class Superman(val name: String, val age: Int, val address: String, val city: String): DCSuperhero()
object WonderWoman: DCSuperhero()
```
{% endcode %}

Turunan _Sealed Class_ **hanya** bisa didefinisikan di dalam **satu file**. Kita tidak akan bisa membuat _class_ turunan di file yang berbeda

{% code title="MarvelSuperhero.kt" %}
```kotlin
package marvel.hero

import dc.hero.DCSuperhero

class Spiderman: DCSuperhero() // error compile
```
{% endcode %}

Dengan begitu, kita bisa tahu pasti apa saja turunan dari sebuah _class_ yang di-_sealed_. Ini akan sangat berguna ketika menggunakan fitur _polymorphism_ seperti pada contoh dibawah

{% code title="DCExtendedUniverse.kt" %}
```kotlin
package cinema

import dc.hero.*

class DCExtendedUniverse {
    fun memberInfo(hero: DCSuperhero) {
        // disini kita sudah dapat memastikan bahwa
        // hero akan bernilai dari satu dari Batman, Superman, dan Wonderwoman
        when(hero) {
            is Batman -> print("I am Batman")
            is Superman -> print("Truth, justice and the American way")
            is WonderWoman -> print("I am Diana of Themyscira")
        }
    }
}
```
{% endcode %}



