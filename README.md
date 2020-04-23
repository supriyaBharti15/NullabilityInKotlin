# NullabilityInKotlin
null checking in Kotlin | Safe call (?.) | null-coalescing operator  Elvis (?:) | safe cast (as?)|  not null assertions (!!) | let | 
## non-null references
```kotlin
//a regular variable of type String can not hold null:
        val str = "supriya" // Regular initialization means non-null by default
        str=null // compilation error :: null can not be the value of non-null type String
```
```kotlin
//To allow nulls, we can declare a variable as nullable string, written String?:
        var str: String? = "supriya" // can be set null
        str = null //ok
        println(str) // output :: null
```
