# Java Journey, 09: Strings.

In Java, a string is an object that represents a sequence of characters. Strings are widely used in Java programs for storing and manipulating text-based data. Java provides a rich set of built-in methods to manipulate strings, making them a powerful tool for various programming tasks. This repository covers the basics of working with strings in Java, including creating and initializing strings, string concatenation, common string methods, and regular expressions.

## Study the use of strings in Java.

Strings are widely used in Java programming for manipulating text. A string is a sequence of characters that are treated as an object in Java. String objects are immutable, meaning that their contents cannot be changed after creation.

In Java, strings can be created using string literals or by creating a String object using the "new" keyword. There are several methods available in Java for manipulating strings, such as concatenating strings, replacing characters or substrings, converting to uppercase or lowercase, and more.

String objects can also be compared using the "equals" method or the "compareTo" method. Additionally, Java provides a String class that has a variety of static methods for working with strings, such as parsing strings into integers or doubles, formatting strings, and more.

Overall, understanding the use of strings in Java is essential for developing programs that involve working with text.

## Learn about string literal creation and string pooling.

In Java, a string is a sequence of characters. A string can be created in two ways, either by using a string literal or by using the new keyword to create a new string object. A string literal is a sequence of characters enclosed within double quotes. For example, "Hello World!" is a string literal.

String pooling is a mechanism used by Java to save memory. When a string literal is created, it is added to a pool of strings in memory. If a new string literal is created with the same value, then it will reference the same object in the pool, rather than creating a new object. This reduces memory usage and improves performance.

For example:

```bash
String str1 = "Hello";   //string literal
String str2 = "Hello";   //string literal
String str3 = new String("Hello");   //new object

System.out.println(str1 == str2);  //true
System.out.println(str1 == str3);  //false
```

In this example, str1 and str2 are both string literals with the same value "Hello". Therefore, they reference the same object in the string pool. str3 is a new object created using the new keyword, so it is a separate object in memory.

It is important to note that string literals are immutable in Java, meaning their values cannot be changed once they are created. Any operation that appears to modify a string actually creates a new string object.

In addition to string literals, strings can also be created using the String class constructor and various string manipulation methods.

## Get an understanding of string immutability.

In Java, a string is an object that represents a sequence of characters. The string objects are immutable, which means once a string object is created, it cannot be modified. Any operation performed on a string actually creates a new string object. This is known as string immutability.

For instance, consider the following code:

```bash
String str1 = "Hello";
String str2 = str1.concat(" World");
System.out.println(str1);
System.out.println(str2);
```

In the above example, the concat() method is used to concatenate " World" to the str1 object. However, the str1 object remains unchanged, and a new string object str2 is created with the value "Hello World".

This string immutability has some advantages, such as allowing strings to be shared between different parts of a program without worrying about their value being changed unexpectedly. However, it also means that creating new strings can be less efficient, especially when working with large strings.

## Study the use of the "new" keyword with strings.

In Java, strings can be created using a string literal or by using the "new" keyword to create a new instance of a string object.

When the "new" keyword is used, a new instance of the string object is created in the heap memory, which takes up more memory and processing power than creating a string literal. This is because the new instance has its own memory allocation, which is not shared with other strings.

For example, consider the following code snippet:

```bash
String str1 = "Hello World"; // using string literal
String str2 = new String("Hello World"); // using the "new" keyword
```

In this example, str1 is created using a string literal, while str2 is created using the "new" keyword.

It is important to note that using the "new" keyword to create a string object is not always necessary or recommended, as it can lead to unnecessary memory usage and decreased performance. It is generally better to use string literals unless there is a specific need for creating a new instance of a string object.

## Learn the difference between == and equals() method for string comparison.

In Java, the == operator is used to compare the reference of two objects, whereas the equals() method is used to compare the contents of two objects.

When the == operator is used for comparing two string variables, it checks whether both variables refer to the same object in memory. For example:

```bash
String str1 = "Hello";
String str2 = "Hello";
if (str1 == str2) {
    System.out.println("str1 and str2 are referring to the same object");
}
```

In this case, str1 and str2 are both referencing the same string literal "Hello" in the string pool. So, the if statement is true and "str1 and str2 are referring to the same object" will be printed.

On the other hand, the equals() method compares the contents of two string objects. For example:

```bash
String str1 = "Hello";
String str2 = new String("Hello");
if (str1.equals(str2)) {
    System.out.println("str1 and str2 have the same contents");
}
```

In this case, str1 is a string literal and str2 is a new string object created with the new keyword. Even though they have different references, their contents are the same. So, the if statement is true and "str1 and str2 have the same contents" will be printed.

It's important to note that because strings are immutable in Java, using the == operator to compare the contents of two string objects can sometimes give unexpected results. It's generally recommended to use the equals() method for comparing string objects.

## Study the use of the toString() method and string concatenation operator.

In Java, the toString() method is used to obtain a string representation of an object. It is a method of the Object class, and is used to convert an object into a string. The default implementation of toString() returns a string that contains the class name, an @ symbol, and the hash code of the object in hexadecimal form.

The string concatenation operator (+) is used to concatenate two or more strings. When the operator is used with a string and another data type, the other data type is first converted to a string and then concatenated with the original string.

For example:

```bash
String str1 = "Hello";
String str2 = "world";
String str3 = str1 + " " + str2; // str3 is "Hello world"
```

It is important to note that string concatenation can be expensive, especially when done repeatedly in a loop. In such cases, using a StringBuilder or StringBuffer can be more efficient.

In Java, the StringBuilder and StringBuffer classes provide methods for efficient string concatenation. The StringBuilder class is not thread-safe, while the StringBuffer class is thread-safe.

For example:

```bash
StringBuilder sb = new StringBuilder();
sb.append("Hello");
sb.append(" ");
sb.append("world");
String str = sb.toString(); // str is "Hello world"
```

## Learn about StringBuffer and StringBuilder in Java.

In Java, StringBuffer and StringBuilder are classes used for performing string manipulation operations. Both of these classes are used to create and modify mutable (changeable) string objects.

StringBuffer and StringBuilder are similar in many ways, but they have one key difference: StringBuffer is thread-safe, meaning that it can be accessed by multiple threads at the same time without causing any issues. On the other hand, StringBuilder is not thread-safe.

Both StringBuffer and StringBuilder provide methods for appending, inserting, deleting, and replacing characters in a string. The main difference between the two classes is that StringBuilder is faster than StringBuffer because it is not synchronized.

For example, if you need to concatenate multiple strings in a loop or perform any other string manipulation operation, StringBuilder is a better choice. On the other hand, if you are working in a multithreaded environment, or if you need a synchronized string buffer, then StringBuffer would be a better option.

Overall, both StringBuffer and StringBuilder are useful for efficient string manipulation operations in Java.

## Study the various methods available in the String class.

The String class in Java provides several methods to manipulate and analyze strings. Some of the commonly used methods are:

1- length() - returns the length of the string.

2- charAt(int index) - returns the character at the specified index in the string.

3- substring(int beginIndex, int endIndex) - returns a substring of the string from the beginIndex to the endIndex-1.

4- concat(String str) - concatenates the specified string to the 
end of the invoking string.

5- equals(Object obj) - compares the invoking string to the specified object.

6- indexOf(String str) - returns the index of the first occurrence of the specified substring in the invoking string.

7- replace(char oldChar, char newChar) - replaces all occurrences of oldChar with newChar in the string.

8- toUpperCase() - returns a new string with all characters in uppercase.

9- toLowerCase() - returns a new string with all characters in lowercase.

10- trim() - returns a new string with leading and trailing white spaces removed.

These are just a few of the many methods available in the String class. By studying and understanding these methods, one can effectively manipulate and analyze strings in Java.

If you want to explore more Strings methods, click on the link below.

https://docs.oracle.com/javase/8/docs/api/java/lang/String.html
