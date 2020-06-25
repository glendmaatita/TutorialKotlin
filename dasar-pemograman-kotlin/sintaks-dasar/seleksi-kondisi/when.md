# When

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

