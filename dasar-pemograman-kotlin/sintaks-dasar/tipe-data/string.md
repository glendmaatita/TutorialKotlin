# String

String adalah kumpulan karakter yang dibungkus oleh tanda _double-quote_ `" "` .  String dapat berisi abjad, angka, maupun simbol umum. Untuk karakter-karakter tertentu semisal `\n` Kotlin tidak akan serta-merta menganggapnya bagian dari karakter, namun akan mem-parsing-nya terlebih dahulu. Untuk kasus `\n` Kotlin akan mengubahnya menjadi _enter_

```kotlin
val name = "Freya Agnessa Maatita"
val address = "Sleman,\nYogyakarta"
//Sleman,
//Yogyakarta
```

Umumnya kita menulis `String` dalam satu baris, namun `String` bisa juga ditulis di dalam banya baris. Untuk kasus ini kita harus membungkus kumpulan karakternya dengan _triple-quote_ `"""`

```kotlin
val history = """
Sukarno was the leader of the Indonesian struggle for 
independence from the Dutch Empire. 

He was a prominent leader of Indonesia's nationalist 
movement during the Dutch colonial period and spent 
over a decade under Dutch detention until released by 
the invading Japanese forces in World War II. 

Sukarno and his fellow nationalists collaborated to 
garner support for the Japanese war effort from the population,
in exchange for Japanese aid in spreading nationalist ideas.
"""
```

{% hint style="info" %}
Saat menggunakan _triple-quote_ `"""` untuk menyimpan suatu `String`,  Kotlin akan menyimpan `String` tersebut apa adanya. Artinya, Kotlin tidak akan menghilangkan _enter_ atau _space_ yang terkandung di dalamnya, dan tidak melakukan parsing apapun. Misalnya, karakter `\n` akan tidak dianggap sebagai _enter_
{% endhint %}

### Template String

Kita akan sering menemui kasus dimana kita ingin menggabungkan beberapa variabel `String` menjadi satu. Di Kotlin kita bisa melakukan ini dengan menambahkan prefix `$` pada variabel yang akan digabungkan

```kotlin
val name = "Ryu"
val city = "Yogyakarta"
val greet = "Hi $name from $city" // Hi Ryu from Yogyakarta
```



