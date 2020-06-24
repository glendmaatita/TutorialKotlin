# Variabel

Untuk menggunakan variabel di Kotlin, kita cukup menuliskan nama variabel dengan diawali `val` atau `var` . `var` digunakan untuk mendefinisikan variabel yang nilainya bisa berubah, sedangkan `val` untuk variabel yang nilainya tetap/tidak bisa diubah.

```kotlin
var name = "Ryu"
name = "Ken"

val age = 17
age = 20 // error
```

{% hint style="info" %}
Kotlin adalah bahasa pemograman yang mempunyai fitur _type-inference,_ artinya pendefinisian tipe variable sifatnya opsional. Secara otomatis, Kotlin akan mendeteksi tipe dari suatu variabel melalui nilainya.
{% endhint %}

Kita juga dapat mendefinisikan tipe variabel saat mendeklarasikannya

```kotlin
val name: String = "Ryu"
var age: Int = 18

age = "delapan belas" // error
```

{% hint style="info" %}
Hati-hati dalam mengubah nilai dari suatu variabel dan pastikan tipenya sama karena Kotlin adalah bahasa pemograman _strong-type,_ artinya begitu suatu variabel sudah didefinisikan tipe datanya, tipe data tersebut akan melekat pada variabel tersebut dan tidak dapat diubah
{% endhint %}

