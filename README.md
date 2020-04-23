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
        
        
    var j = b?.length
    println(j)//null
```
```kotlin
//Safe calls are useful in chains. For example, if Bob, an Employee, may be assigned to a Department (or not), that in turn may have //another Employee as a department head, then to obtain the name of Bob's department head (if any), we write the following:
bob?.department?.head?.name
```

```kotlin
//To perform a certain operation only for non-null values, you can use the safe call operator together with let:
val listItem :List<String> = listOf("ram","raja")
        for (item in listItem){
            println(item) // it will print all item 
            //output:: ram raja
        }
  // if i put null value to list then 
        val listItem :List<String?> = listOf("ram","raja",null)
        for (item in listItem){
            println(item) // it will print all item include null
             //output:: ram raja null
        }

//ingore null and print rest of item
 val listItem: List<String?> = listOf("ram", "raja", null)
        for (item in listItem) {
            item?.let { println(item) }// print all item and exclude null
             //output:: ram raja 
        }
```
## Elvis Operator
```kotlin
//If the expression to the left of ?: is not null, the elvis operator returns it, otherwise it returns the expression to the right. Note that the right-hand side expression is evaluated only if the left-hand side is null.


//When we have a nullable reference b, we can say "if b is not null, use it, otherwise use some non-null
val l: Int = if (b != null) b.length else -1

//Along with the complete if-expression, this can be expressed with the Elvis operator, written ?::
val l = b?.length ?: -1
```
