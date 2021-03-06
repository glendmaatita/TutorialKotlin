# Enum Classes

_Enum Class_ adalah _class_ yang berisi _constant_, tipenya _object_. Konsepnya sama dengan di kebanyakan bahasa pemograman lain, plus ditambah ada beberapa fleksibilitas yang disediakan oleh Kotlin

```kotlin
enum class SuperPowers {
    FLY, ENDURANCE, SUPER_STRENGTH
}
```

{% hint style="info" %}
Tiap _constant_ dalam _Enum Class_ ditulis dengan dipisah tanda koma `(,)`
{% endhint %}

_Enum Class_ dapat mempunyai fungsi _abstract_  yang harus di-_implement_ oleh semua _constant objects_ di dalamnya

```kotlin
enum class SuperPowers {
    FLY {
        override fun execute() {
            print("Let's fly")
        }
    }, ENDURANCE {
        override fun execute() {
            print("Let's fight all day long")
        }
    }, SUPER_STRENGTH {
        override fun execute() {
            print("Let me punch the villain")
        }
    };

    abstract fun execute()
}
```

Sebuah enum class dapat meng-_implement_ _Interface_, yang akan membuat semua _constact objects_ di dalamnya harus membuat implementasi dari _Interface_ tersebut. Perlakuannya sama dengan saat mempunyai fungsi _abstract_ sendiri di dalamnya

```kotlin
enum class SuperPowers: PowerExecution {
    FLY {
        override fun execute(level: Int) {
            print("Let's fly")
        }
    }, ENDURANCE {
        override fun execute(level: Int) {
            print("Let's fight all day long")
        }
    }, SUPER_STRENGTH {
        override fun execute(level: Int) {
            print("Let me punch the villain")
        }
    };
}

interface PowerExecution {
    fun execute(level: Int)
}
```

###  Menggunakan Enum Class

_Enum Class_ digunakan untuk membatasi nilai dari sebuah variabel, mencegah programmer untuk membuat sendiri implementasinya sehingga dapat menjamin konsistensi dari sebuah nilai tertentu

{% code title="SuperPower.kt" %}
```kotlin
package super

enum class SuperPowers: PowerExecution {
    FLY {
        override fun execute() {
            print("Let's fly")
        }
    }, ENDURANCE {
        override fun execute() {
            print("Let's fight all day long")
        }
    }, SUPER_STRENGTH {
        override fun execute() {
            print("Let me punch the villain")
        }
    };
}

interface PowerExecution {
    fun execute()
}
```
{% endcode %}

{% code title="SuperHero.kt" %}
```kotlin
package super

class SuperHero {
    var superPower: SuperPowers? = null

    fun setPower(power: SuperPowers) {
        this.superPower = power
    }

    fun showPower() {
        superPower?.execute(500)
    }
}
```
{% endcode %}

{% code title="MyApplication.kt" %}
```kotlin
package main

fun main() {

    val superman = SuperHero()
    superman.setPower("super speed") // compile error
    
    superman.setPower(SuperPowers.FLY) // compile success
    superman.showPower() // Let's fly
}
```
{% endcode %}

