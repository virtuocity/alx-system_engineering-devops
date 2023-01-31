# 0x06-regular_expressions
## Notes
*Super classic industry joke*   
Some people, when confronted with a problem, think
“I know, I'll use regular expressions.”   Now they have two problems.  

   
**A regular expression**, commonly called a *“regexp”*, is a sequence of characters that define a search pattern.  It is mainly for use in pattern matching with strings, or string matching (i.e. it operates like a “find and replace” command)   
One thing you have to be careful with is that different languages use different regexp engines. That means that a regexp in Python, for example, will be interpreted differently in Javascript.   
System administrators and DevOps are the ones using them the most because they are very handy for log parsing.  
You can think of regular expressions as wildcards on steroids. You are probably familiar with wildcard notations such as *.txt to find all text files in a file manager. The regex equivalent is ^.*\.txt$.  
One could use the regular expression \b[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,}\b to search for an email address. Any email address, to be exact. A very similar regular expression (replace the first \b with ^ and the last one with $) can be used by a programmer to check whether the user entered a properly formatted email address. In just one line of code, whether that code is written in Perl, PHP, Java, a .NET language, or a multitude of other languages.  
## Links
+ Regular Expressions Concept  
https://intranet.alxswe.com/concepts/29  
+ The Premier website about Regular Expressions  
https://www.regular-expressions.info/  
+ W3Schools JavaScript RegExp Reference  
https://www.w3schools.com/jsref/jsref_obj_regexp.asp   
+ Rubular: a Ruby regular expression editor  
https://rubular.com/   
