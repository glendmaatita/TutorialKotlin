# for

`for` adalah salah satu operator looping di Kotlin. Kita dapat melakukan iterasi pada suatu _collection_ dengan menggunakan operator ini. 

```kotlin
val cars = arrayOf("BMW", "Mclaren")
for (car in cars) {
    println("I am driving a $car")
}
```

_Collection_ dapat berupa _array_, _map_, _set_ maupun tipe iterator yang lain

```kotlin
val cars = mapOf(Pair("BMW", "3 Series"), Pair("Mercedes", "C-Class"))
for (car in cars) {
    println("I am driving a ${car.key} ${car.value}")
}

val motors = setOf("Aprilia", "Ducati")
for (motor in motors) {
    println("I am riding $motor")
}
```

Selain _collection_, `for` juga bisa digunakan untuk iterasi sebuah range

```kotlin
for (count in 1..10) {
    println("Counter: $count")
}
```

