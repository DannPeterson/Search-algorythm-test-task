# SMIT HOMEWORK

Task completed using Java and Maven.  
You can build JAR using Maven commands:  
```
mvn clean
mvn install
```
After that you can run compiled JAR from '\target' folder using command promt:  

```
java -jar ClassFinder.jar <filename> <pattern> 
```

For example: 

```
java -jar ClassFinder.jar C:\Users\...\classes.txt fbb 
```
 
## TASK DESCRIPTION:

The goal of this homework is to implement class finder functionality
in a similar way to the Intellij IDEA Ctrl+N search.

You can use any language of your choice for this task.

You have to implement a program that can be executed from the command line:

```
./class-finder <filename> '<pattern>'
```

where `<filename>` refers to the file containing class names separated by line breaks, e.g.:

```
a.b.FooBarBaz
c.d.FooBar
```

Search pattern `<pattern>` must include class name camelcase upper case letters
in the right order and it may contain lower case letters to narrow down the search results,
for example `'FB'`, `'FoBa'` and `'FBar'` searches must all match
`a.b.FooBarBaz` and `c.d.FooBar` classes.

Upper case letters written in the wrong order will not find any results, for example
`'BF'` will not find `c.d.FooBar`.

If the search pattern consists of only lower case characters then the search becomes
case insensitive (`'fbb'` finds `FooBarBaz` but `'fBb'` will not).

If the search pattern ends with a space `' '` then the last word in the pattern must
also be the last word of the found class name (`'FBar '` finds `FooBar` but not `FooBarBaz`).

The search pattern may include wildcard characters `'*'` which match missing letters
(`'B*rBaz'` finds `FooBarBaz`i but `BrBaz` does not).

The found class names must be sorted in alphabetical order ignoring package names
(package names must still be included in the output).

Solution limitations:
- Regexp must not be used.
- Use of other libraries (other than the language itself) is prohibited.

Solution requirements:
- Unit tests must be present. For unit tests you are allowed to use libraries
(such as JUnit, Rspec, Jasmine and equivalent)

It is good enough if the solution implements the functionality described in this file.
To get familiar with the Intellij IDEA class finder functionality you can try it
out in the IDE but be informed that the real search has some extra complexity
not described here.
