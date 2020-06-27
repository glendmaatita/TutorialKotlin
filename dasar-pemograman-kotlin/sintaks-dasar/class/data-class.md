# Data Class

_Data Class_ adalah _class_ yang hanya berisi properti untuk menyimpan suatu data. Class ini tidak mempunyai fungsi. _Data Class_ adalah padanan Kotlin atas konsep _POJO_ atau _Plain Old Java Object_ di Java, yang mana merupakan sebuah _class_ di Java yang hanya berisi properti dan fungsi untuk _setter_ dan _getter_. 

Kita bisa menggunakan _Data Class_ jika kita ingin memiliki _class_ yang hanya berfungsi sebagai tempat untuk menyimpan data tanpa ada logika lain di dalamnya. 

{% code title="Person.kt" %}
```kotlin
package human

data class Person(
    val name: String,
    val phone: String,
    val email: String,
    val age: Int
)
```
{% endcode %}

Dapat dilihat diatas jika _Data Class_ hanya memiliki properti. Kita lantas dapat  untuk menyimpan data.

{% code title="MyApplication.kt" %}
```kotlin
package main

import human.Person

fun main() {
    val person = Person(
        name = "Ryu",
        phone = "08954566334",
        email = "ryu@gmail.com",
        age = 40)
        
    printPersonData(person)
}

fun printPersonData(person: Person) {
    print(person.toString()) // Person(name=Ryu, phone=08954566334, email=ryu@gmail.com, age=40)
}

```
{% endcode %}

_Data Class_ tidak mempunyai fungsi sendiri, hanya mempunyai fungsi dasar bawaan dari Kotlin yaitu `copy()`, `equals()`, dan `toString()`

### Meng-copy Data Class

Kita dapat meng-_copy_ suatu data class ke dalam sebuah variabel, sekaligus dapat mengubah nilai dari propertinya

{% code title="MyApplication.kt" %}
```kotlin
package main

import human.Person

fun main() {
    val person = Person(
        name = "Ryu",
        phone = "08954566334",
        email = "ryu@gmail.com",
        age = 40)
        
    val anotherPerson = person.copy(name = "Ken", age = 20)
}

```
{% endcode %}

### Decompose Data Class

Terakhir, kita dapat mengekstrak nilai properti dari sebuah _Data Class_ dan memasukkannya ke dalam variabel secara berurutan.

{% code title="MyApplication.kt" %}
```kotlin
package main

import human.Person

fun main() {
    val person = Person(
        name = "Ryu",
        phone = "08954566334",
        email = "ryu@gmail.com",
        age = 40)
        
    val(hisName, hisPhone, emailAddress) = person
    println(hisName) // Ryu
    println(hisPhone) // 08954566334
    println(emailAddress) // ryu@gmail.com
}

```
{% endcode %}

{% hint style="info" %}
Decompose dijalankan secara berurutan sesuai urutan properti di dalam Data Class
{% endhint %}

