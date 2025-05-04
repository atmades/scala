# A little Scala coding challenge
**Convert this code to a functional style**  

## Start
```sh
object StringProcessor {
  def processStrings(strings: List[String]): List[String] = {
    var result = List[String]()
    for (str <- strings) {
      if (str.length > 3) {
        result = result :+ str.toUpperCase
      }
    }
    result
  }

  def main(args: Array[String]): Unit = {
    val strings = List("apple", "cat", "banana", "dog", "elephant")
    val processedStrings = processStrings(strings)
    println(s"Processed strings: $processedStrings")
  }
}
```
## Result
```
object StringProcessor {
  def processStrings(strings: List[String]): List[String] = {
    strings
      .filter(_.length > 3)     // Фильтрация строк длиннее 3 символов
      .map(_.toUpperCase)       // Преобразование в верхний регистр
  }

  def main(args: Array[String]): Unit = {
    val strings = List("apple", "cat", "banana", "dog", "elephant")
    val processedStrings = processStrings(strings)
    println(s"Processed strings: $processedStrings")
  }
}
```
