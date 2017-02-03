# REGEX Challenge

### Goal

This lite exercise will help you gain practice in using regular expressions. While all problems require you to provide the proper regex, some will require you to also provide additional information or research the internet.

### Directions

It's recommended that the student uses https://regex101.com/ when attempting to solve the problem set. Put your fully explained solution in this file. 

### Exercises

Provide three regexes that matches `yes yes yes` but not `no no no`

```c#
answer: /[a-z][a-z][a-z] [a-z][a-z][a-z] [a-z][a-z][a-z]/
				/\w\w\w \w\w\w \w\w\w/
				/\w{3} \w{3} \w{3}/

```

Provide a regex that matches valid phone numbers with the forms `678-123-1122` and `(678) 123-1122` while still allowing symbols to be optional. HINT: Research the rules around valid phone numbers.

```c#
answer:/.?\d{3}.*\d{3}.*\d{4}/

```

Provide a regex that matches URLs like `https://regex101.com`, `http://facebook.com` and `https://www.godaddy.com` but not `https://msdn.microsoft.com`. (Trailing `/` should be allowed and optional)

```c#
answer:/http\w?:\/\/\w*\.*\w{3,8}\.com/

```

Provide a regex that matches dates with the format: `Wed Aug 11, 2013`.

```c#
answer:/\w{3} \w{3} \d\d, \d{4}/

```

Provide a regex that matches dates with the format: `MM/DD/YYYY`. Use named captures to extract Day, Month and Year.

```c#
answer:/(?<Month>\d\d)\/(?<Day>\d\d)\/(?<Year>\d{4})/

```

Provide a regex that matches `function returnOne() {return 1;}` and captures the value returned.

```c#
answer:/function \w+\(\) {return (?<value>\d+);}/

```

Provide a regex that matches `List<int> my_List = new List<int>();` and captures the variable name.

```c#
answer:/List<int> (?<name>\w+).*=.*new List<int>\(\);/

```

Provide two regexes that matches `Billy Jean` but not `billy jean`.

```c#
answer:/\p{Lu}\w* \p{Lu}\w*/
				/[A-Z]\w* [A-Z]\w*/

```

Provide two regexes that matches `NSS Evening Cohort 3` and captures "Cohort 3".

```c#
answer:/NSS Evening (?<name>\w{6} \d+)/

```

	Provide a regex that matches emails of the forms `first.last@example.com` and `something99@history.com`. Allow for numbers in the domain name as well as the email prefix. Capture the domain name.

```c#
answer:/\w*\.?\w+@(?<name>\w+\.com)/

```

Provide a regex (as if for a password checker), that enforces a password to have at least one symbol and one number.

```c#
answer:/(?=.*\W)(?=.*\d)[A-Za-z\d]{8,}/

```

Provide a regex that matches emails from the domains `.com`, `.org`, `.net`, `.io` and `.ly` but not `.biz` and `.com.uk`. This regex should capture the end result. (use #10 as a starting point).

```c#
answer:/\w*\.?\w+@(?<name>\w+\.[ac-z]\w*)/

```

Provide a regex that matches the entire [2nd paragraph of the Wikipedia page about John Lennon](https://en.wikipedia.org/wiki/John_Lennon).

```c#
answer:/Born and raised.*its release\./

```

Provide a regex that matches the numbered exercises from this challenge.

```c#
answer:/Provide .*\d+.*\./

```

Provide two regexes that matches the following C# code and captures the property names. (HINT: How could you match a newline?)

```c#
public class Part
{
    public string PartName { get; set; }
    public int PartId { get; set; }
}
```

```c#
answer:/public class \w+\n{\n.*public string (?<property1>\w+) {.*}\n.*public int (?<property2>\w+) {.*}\n}/

/public class \w+
{
.*public string (?<property1>\w+) { get; set; }
.*public int (?<property2>\w+) { get; set; }
}/m

```
