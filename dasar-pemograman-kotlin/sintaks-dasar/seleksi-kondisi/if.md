# if

`if` digunakan untuk operasi pengecekan. Penggunaan `if` di Kotlin tidak berbeda dengan bahasa pemograman lainnya

```kotlin
val age = 18
if (age < 18) {
    print("You are under 18yo")
}
```

### if dengan else

`else` digunakan ketika ada aksi lain ketika suatu kondisi tidak terpenuhi di dalam block `if`

```kotlin
val age = 18
if (age < 18) {
    print("You are under 18yo")
} else {
    print("You are not under 18yo")
}
```

### if dengan else if 

`else if` digunakan ketika kita melakukan pengecekan atas banyak kondisi

```kotlin
val age = 18
if (age < 18) {
    print("You are under 18yo")
} else if (age == 18) {
    print("You are 18yo")
} else {
    print("You are over 18yo")
}
```

### Nested if

_Nested if_ adalah membuat blok `if` di dalam suatu blok `if`

```kotlin
val age = 18
if (age < 18) {
    if (age < 10) {
        print("You are under 17yo")
    } else if (age <= 15) {
        print("You are under 15yo")
    } else {
        print("You are under 18yo")
    }
} else if (age == 18) {
    print("You are 18yo")
} else {
    print("You are over 18yo")
}
```

###  if sebagai ekspresi

if di Kotlin dapat mengembalikan nilai, oleh karena itu di Kotlin tidak mengenal operasi _tenary_ 

```kotlin
val x = 20
val y = 15
val top = if (x < y) {
  x 
 } else {
  y
 }
```





