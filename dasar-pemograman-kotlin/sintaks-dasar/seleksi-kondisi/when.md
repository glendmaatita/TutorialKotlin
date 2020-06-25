# when

Sama seperti if, when digunakan untuk melakukan pengecekan. when paling cocok digunakan untuk pengecekan yang bersifat sekuensial, atau berurutan. Berbeda dengan kebanyakan bahasa pemograman lain, when di Kotlin tidak mempunyai statemen `break`, artinya ketika suatu kondisi ada yang cocok, secara otomatis tidak akan ada pengecekan selanjutnya

```kotlin
val type = "superhero"
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
`else` digunakan ketika tidak ada kondisi yang cocok
{% endhint %}

Pengecekan kondisi di when tidak terpaku hanya pencocokan value seperti contoh diatas. Kita juga misalnya dapat mengecek apakah suatu bilangan ada di dalam range tertentu

```kotlin
val age = 15
when (age) {
    in 1..10 -> {
        print("I am a child")
    }
    in 11..20 -> {
        print("I am a teenager")
    }
    else -> {
        print("I am an adult")
    }
}
```

Atau menggunakannya untuk kondisi `true` atau `false` dari value suatu variabel. Metode ini bisa digunakan untuk menggantikan `if else`

```kotlin
val value = "10"
when {
   value.isBlank() -> print("value is blank")
   value.isNotBlank() -> print("value is not blank")
   value.isNotEmpty() -> print("value is not empty")
}
```

{% hint style="info" %}
Saat digunakan untuk menggantikan peran `if else` , kita tidak perlu me-_passing_ variabel sebagai parameter dari `when`
{% endhint %}

### When sebagai ekspresi

`when` dapat mengembalikan nilai, oleh karena itu `when` dapat digunakan untuk memberi nilai pada suatu variabel

```kotlin
val type = "superhero"
val description = when (type) {
    "villain" -> "I am a villain"
    "antihero" -> "I am an antihero"
    else -> "I am a hero"
}

print(description) // I am a hero
```

{% hint style="info" %}
Jika statemen di suatu kondisi di dalam when hanya terdiri dari _satu_ baris, kita tidak perlu membungkusnya dengan kurung kurawal `{ }`
{% endhint %}

Selain untuk memberi nilai pada suatu variabel, sebagai ekspresi, when juga bisa digunakan untuk mengembalikan nilai dari suatu fungsi

```kotlin
package main

fun main() {
    val type = "superhero"
    val description = getDescription(type)
}

fun getDescription(type: String): String = when (type) {
    "villain" -> "I am a villain"
    "antihero" -> "I am an antihero"
    else -> "I am a hero"
}
```

