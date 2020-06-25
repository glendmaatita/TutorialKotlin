---
description: 'Bab ini akan membahas apa itu Package, kegunaannya, dan cara menggunakannya'
---

# Package

Package adalah suatu cara untuk mengelompokkan kode agar rapi dan mudah dibaca. Package dalam Kotlin bersifat _physical_, artinya nama package akan sesuai dengan lokasi tempat kode berada, dan relatif terhadap lokasi folder _src/_. Semua kode Kotlin idealnya berada di dalam sebuah package, agar mudah di-maintain. 

Deklarasi package dapat ditulis sebagai berikut:

```kotlin
package study

class Book
```

{% hint style="warning" %}
 Karena relatif terhadap folder _src/_, maka kode dengan package seperti contoh diatas akan berlokasi di _src/study/_
{% endhint %}

Kegunaan Package akan jelas terlihat ketika kita menggunakan kode dari package lain

{% code title="student.kt" %}
```kotlin
package main

import study.Book

val book = Book()


```
{% endcode %}

{% hint style="info" %}
Untuk menggunakan class dari package lain, gunakan kata kunci `import nama_package/nama_class`
{% endhint %}

Terlihat dari kode diatas, di dalam `student.kt` kita menggunakan class `Book` yang berada di package lain dengan menggunakan kata kunci `import`

