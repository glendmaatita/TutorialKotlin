---
description: >-
  Bab ini akan membahas tentang Idiom di Kotlin, sesuatu yang membuat sintaks
  Kotlin berbeda dengan bahasa pemograman lain
---

# Idiom

Setiap bahasa pemograman mempunyai idiom masing-masing. Idiom ibarat dialek pada bahasa lisan, yang membedakan antara satu bahasa dengan bahasa lain meskipun sama-sama memakai abjad atau bahkan kata yang sama. Jadi kita akan bisa membedakan, apakah seorang programmer sudah lama menulis kode Kotlin hanya dengan melihat apakah dia menggunakan idiom Kotlin dengan baik dan benar. 

Biasanya programmer yang baru belajar suatu bahasa pemograman akan membawa gaya penulisan kode dari bahasa pemograman yang sebelumnya dia kuasai. Memaksimalkan penggunaan idiom akan membuat kode kita lebih bersih, \(mungkin\) pendek, dan mudah dibaca. 

Berikut adalah beberapa idiom penting di Kotlin yang perlu selalu kita ingat ketika kita menulis kode di Kotlin

#### Manfaatkan _type-inference_ di Kotlin

Kotlin secara otomatis akan mendeteksi tipe data dari suatu variabel berdasarkan nilai yang dikandungnya. Jika tidak dalam kondisi khusus, manfaatkan fitur ini untuk mempersingkat kode kita

```kotlin
val name: String = "Ryu"

// diganti dengan
val name = "Ryu"
```

#### Di Kotlin, semua adalah _Object_

Di Kotlin, semua adalah _object_, tidak ada tipe data primitif disini. Artinya tiap variabel adalah object, sehingga kita bisa memanfaatkan method-method bawaan yang ada pada variabel tersebut, alih-alih membuat sebuah fungsi untuk melakukan tugas tertentu. Dengan fitur ini pula-lah kita bisa memaksimalkan fitur lainnya pada Kotlin, yaitu funksi ekstensi yang akan dibahas di bab tersendiri.

```kotlin
val name = "Ryu"
val report = "Your name consists of ${name.length} characters"
```

#### Hilangkan semicolon

Kotlin tidak membutuhkan semicolon `;` untuk menandai akhir dari sebuah statement. Kotlin menggunakan `enter` untuk ini

```kotlin
val name = "Ken" // lakukan
val name = "Ryu"; // hindari
```

#### Gunakan `when` daripada `if` ketika melakukan pengecekan nilai suatu variabel secara cascade

```kotlin
// Sederhanakan kode di bawah
val type = "hero"
if (type == "villain") {
    print("I am a villain")
} else if (type == "antihero") {
    print("I am an antihero")
} else {
    print("I am a hero")
}

// menjadi dibawah ini
when (type) {
    "villain" -> {
        print("I am a villain")
    }
    "antihero" -> {
        print("I am an antihero")
    }
    else -> {
        print("I am a hero")
    }
}
```

{% hint style="info" %}
Pengecekan secara _cascade_, artinya pengecekan nilai secara berurutan
{% endhint %}

#### Manfaatkan _single-expression function_ untuk suatu fungsi sederhana yang mengembalikan nilai

Fitur ini akan mempermudah penulisan sebuah fungsi sederhana, membuat kode kita lebih mudah dibaca

```kotlin
// sederhanakan kode dibawah
fun calculate(x: Int, y: Int): Int {
    return x * y
}

// menjadi seperti dibawah
fun calculate(x: Int, y: Int): Int = x * y
```

#### Gunakan `if` dan `when` sebagai suatu ekspresi untuk mendapatkan suatu nilai

Fungsi `if` dan `when` adalah bentuk ekspresi di Kotlin. Artinya keduanya dapat mengembalikan sebuah nilai.

Contoh untuk `if`

```kotlin
// sederhanakan kode dibawah
val x = 20
val y = 15
var top = 0
if (x < y) {
    top = x
} else {
    top = y
}

// menjadi seperti dibawah
top = if (x < y) x else y
```

Contoh untuk `when` 

```kotlin
// sederhanakan kode dibawah ini
var description = ""
when {
    type == "villain" -> {
        description = "I am a villain"
    }
    type == "antihero" -> {
        description = "I am an antihero"
    }
    else -> {
        description "I am a hero"
    }
}

// menjadi seperti dibawah ini
var description = when {
    "villain" -> "I am a villain"
    "antihero" -> "I am an antihero"
    else -> "I am a hero"
} 
```

#### Gunakan `let` untuk melakukan pengecekan `null` sebelum mengeksekusi suatu statement

```kotlin
// Sederhanakan kode dibawah ini
val name: String? = "Ryu"
if (name != null) {
    print("I am Ryu")
}

// menjadi seperti dibawah ini
name?.let { 
    print("I am Ryu")
}
```

