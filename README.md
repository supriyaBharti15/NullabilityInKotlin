# NullabilityInKotlin
null checking in Kotlin | Safe call (?.) | null-coalescing operator  Elvis (?:) | safe cast (as?)|  not null assertions (!!) | let | 
## non-null references
```kotlin
//a regular variable of type String can not hold null:
        val a = "supriya" // Regular initialization means non-null by default
        a=null // compilation error :: null can not be the value of non-null type String
```
```kotlin
//To allow nulls, we can declare a variable as nullable string, written String?:
        var b: String? = "supriya" // can be set null
        b = null //ok
        println(b) // output :: null
```
```kotlin
 var r = a.length  //it's guaranteed not to cause an NPE, so you can safely
     r = b.length //// error: variable 'b' can be null
     
     r = b!!.length
        println(r)//output :: null
```
