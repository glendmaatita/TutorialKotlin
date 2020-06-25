---
description: Bab ini akan membahas apa itu fungsi main dan kegunaannya
---

# Fungsi main\(\)

Fungsi `main()` adalah pintu masuk untuk mengeksekusi kode Kotlin. Artinya, jika kita menjalankan sebuah program yang dibuat dengan Kotlin, kode yang pertama kali dieksekusi adalah kode yang berada dalam fungsi `main()`. 

Jadi di fungsi ini kita bisa melakukan hal-hal yang berkaitan dengan inisialisasi program. Semua yang diperlukan agar program dapat berjalan dengan baik dapat diinisiasi di fungsi `main()` ini.

Fungsi `main()` dapat diletakkan di file mana saja dan di package mana pun. Runtime Kotlin akan mendeteksi dimana terdapat fungsi `main()` untuk kemudian mengeksekusinya. Yang perlu diingat adalah jangan memasukkan fungsi ini ke dalam sebuah _class_. Cukup definisikan di sebuah file Kotlin

{% code title="MyApplication.kt" %}
```kotlin
package myapp

fun main() {
    print("Run program")
}
```
{% endcode %}



