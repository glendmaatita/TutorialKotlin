# while

`while` akan melakukan loop selama suatu kondisi di dalam `while` masih bernilai true

```kotlin
var i = 1
while (i <= 10) {
   println(i)
   i++
 }
```

{% hint style="info" %}
 Dalam contoh diatas, blok statemen di dalam `while` akan terus dieksekusi selama `i < 10` bernilai `true`
{% endhint %}

Kondisi di dalam `while` dapat kita ubah di dalam blok statemen 

```kotlin
var i = 0
var onLoop = true
while (onLoop) {
    i++
    println(i)
    if (i > 10) {
        onLoop = false
    }
}
```

### Do-While

Pada contoh diatas, pengecekan kondisi `while` , yaitu `while(onLoop)` selalu dilakukan di awal proses, sebelum mengeksekusi program di dalam statemen `while`. Kita bisa memindahkan pengecekan kondisi `while` tersebut di akhir, setelah mengeksekusi program di dalam statemen `while` dengan menggunakan operator `do-while`

```kotlin
var i = 1
do {
    println(i)
    i++
}
while (i <= 10)
```



