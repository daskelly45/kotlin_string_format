# kotlin_string_format
How to use the String.format method in Kotlin
`
fun main(args : Array<String>){
    var good = "good"
    var great = "great"
 
    println("Using Kotlin String templates")
    var templateGood = "Bob is a $good chef"
    var templateGreat = "Bob is a $great chef"
 
    println(templateGood)
    println(templateGreat)
 
    var formatTemplate = "%-2s\t%s"
    var func = {pair : Pair<String, String> -> println(formatTemplate.format(pair.first, pair.second))}
 
    var table = arrayOf(
            "%b" to "Boolean",
            "%c" to "Character",
            "%d" to "Signed Integer",
            "%e" to "Float in scientific format",
            "%f" to "Float in decimal format",
            "%g" to "Float in either decimal or scientific notation based on value",
            "%h" to "Hashcode of argument",
            "%n" to "Line separator",
            "%o" to "Octal Integer",
            "%s" to "String",
            "%t" to "Date or Time",
            "%x" to "Hexadecimal Integer")
 
    println("\n%[flags][width][.precision]type")
 
    println("\nFormatting Symbols")
    table.forEach(func)
}
`

String formatting allows developers to define a common string template and then interchange values as needed.

String Templates
Kotlin has a feature known as String Templates that allow you specify a string and then reference variables as required.

1
2
3
4
5
var good = "good"
var great = "great"
 
var templateGood = "Bob is a $good chef"
var templateGreat = "Bob is a $great chef"
In the above example, the value of the variable good is inserted at $good in the templateGood string. Likewise, the value of the variable great is inserted at $great in the templateGreat string.

We are also free to do evaluations.

1
var plus = "Eagerly awaiting ${1 + 2}"
The 1 + 2 will add to 3 and the result will be “Eagerly awaiting 3”

String.format()
The String class has a format method that takes in a format string and then any number of arguments. The number of arguments must match the same number of format specifiers in the string or an exception will get raised.

To begin, the format string takes the form of “[flags][width][.precision]type” so for example.

1
2
3
val simple = "%d" //very basic
val medium = "Have a nice %s" //More complex
val advanced = "%-2s\t%s"
The first example, simple, only has the type, %d. The same is true with the second String, which only has %s. The final example, has a left-justified flag “-“, followed by the width of two characters (2), and its type, String.

Type Specifiers
Here is a list of the type specifiers and their meanings.

%b	Boolean
%c	Character
%d	Signed Integer
%e	Float in Scientific Notation
%f	Float in Decimal Format
%g	Float in Decimal or Scientific Notation, depending on value
%h	Hashcode of the supplied argument
%n	Line separator
%o	Octal Integer
%s	String
%t	Date or Time
%x	Hexadecimal Integer
Here is an example of how to use the String.format() method.

1
2
var formatTemplate = "%-2s\t%s"
println(formatTemplate.format("%b", "Boolean") //prints %b  Boolean


### [Source](https://stonesoupprogramming.com/2017/11/17/kotlin-string-formatting)
