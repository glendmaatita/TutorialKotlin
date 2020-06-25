# Class

Karena Kotlin adalah bahasa pemograman yang mendukung _Object Oriented Programming_ \(OOP\), dan semua yang ada di Kotlin adalah _object_, maka _class_ menjadi hal yang sangat essensial di Kotlin.

Konsep _class_ mungkin akan berbeda-beda di setiap bahasa pemograman, namun di Kotlin, kita bisa anggap _class_ seperti sebuah cetakan. Cetakan untuk menciptakan _object_ dengan membuat _instance_ dari _class_ tersebut.

Semua class dari Kotlin dimulai dengan kata kunci `class`, dan satu file Kotlin \(_.kt_\) bisa menampung banyak _class_

{% code title="Human.cs" %}
```kotlin
class Hero
class Superhero
```
{% endcode %}

Sedangkan object adalah instance dari class yang didapat dengan memanggil _constructor_ dari sebuah _class_

```kotlin
val superman = Hero()
```

Konsep _constructor_ akan dijelaskan di bab selanjutnya. 

Sebuah _class_ tidak akan berguna apa-apa sebelum kita membuat _object_ dari _class_ tersebut. _Object_ inilah yang akan berperan besar dalam program kita nantinya.

_Class_ dapat memiliki _properties_ dan fungsi di dalamnya. Dan _object_ dari _class_ tersebut dapat memanfaatkan _properties_ dan fungsi tersebut.

```kotlin
fun main() {
    val superman = Hero()
    superman.punch()
}

class Hero {
    val life: Int = 0
    
    fun punch() {
        print("Do punch")
    }
}
```

Penjelasan lebih lanjut mengenai _constuctor_, fungsi, serta _properties_ akan dibahas lebih mendalam di bab-bab berikutnya.

