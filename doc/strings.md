# [V Programming language](https://vlang.io/docs)
##### [doc](..\vdoc.md)/[strings](strings.md)

## STRINGS

"Strings" is a builtin module in V, so you can use it always (declarations is not necessary).

You can find the original open-source code in the "{v_install_path}\vlib\builtin\string.v" file

---
#### Declaration:
You can declare **mutable** or **immutable** strings.

```go
// Declare with ':=' operator and single quotes 
si := 'This is an immutable string'
mut sm := 'This is a mutable string'

// Example:
println(si)   // -->  This is an immutable string
println(sm)   // -->  This is a mutable string
```

---
#### Concatenation:
String concatenation is valid only with **MUTABLE** strings. You can join only strings with strings.

```go
// Mutable string declaration and assignament
mut s := 'That'
println(s)   // -->  That


// Re-assignament
s = 'This'
println(s)   // -->  This


// Concatenation with '+' operator
s = s + ' is' + ' a' + ' concatenated' + ' string'
println(s)   // -->  This is a concatenated string


// Appending string with '+=' operator
s += ' ...and appended'
println(s)   // -->  This is a concatenated string ...and appended


// Appending string with 'add' method
// string.add('str') --> str : return the modified string
s = s.add(' ...and added with add method')
println(s)   // -->  This is a concatenated string ...and appended ...and added with add method
```


---
#### Lenght:
```go

// string.len: return the lenght of the string
l := s.len
println(l)   // -->  74
```

---
#### Comparison:
```go
// Comparison by lenght, using operators '<', '>', '<=', '>=', '==', '!=':
// A boolean value will be returned
s1 := 'This string has some characters'
s2 := 'This one has few chars'
s3 := 'This string in longer than others, because it has a lot of characters'
println(s1 > s2)   // --> 1
println(s3 <= s1)   // --> 0
println(s2 == s3)   // --> 0
println(s1 != s3)   // --> 1
```


---
#### String Manipulation Methods:
You can modify strings with some usefull builtin methods

```go

// string.replace('str', 'str_new') --> str : return the modified string
s = s.replace('concatenated', 'replaced')
println(s)   // -->  This is a replaced string ...and appended ...and added with add method


// string.split('str_sep') --> []str : return an array of strings, splitted by the separator (argument)
s1 := s.split('...')
println(s1)   // -->  ["This is a replaced string", "and appended", "and added with add method"]


// string.left(int_n) --> str : return the first 'int_n' characters of the string
sl := s.left(5)
println(sl)   // -->  This


// string.right(int_n) --> str : return the last characters, starting from 'int_n' character of the string.
sr := s.right(5)
println(sr)   // -->  is a replaced string ...and appended ...and added with add method


// string.reverse() --> string : return the reversed string
sre := s.reverse()
println(sre)   // -->  dohtem dda htiw dedda dna... dedneppa dna... gnirts decalper a si sihT


// string.contains('str_sub') --> boolean : return 1 if the string contains the sub-string passed as argument, otherwise 0
sc := s.contains('appended')
println('The string contains "appended" : $sc')   // -->  1


// string.starts_with('str_sub') --> boolean : return 1 if the string starts with the sub-string passed as argument, otherwise 0
ssw := s.starts_with('This')
println('The string starts with "This" : $ssw')   // -->  1


// string.ends_with('str_sub') --> boolean : return 1 if the string ends with the sub-string passed as argument, otherwise 0
sew := s.ends_with('method')
println('The string ends with "method" : $sew')   // -->  1


// string.to_lower() --> str : return a string with all uppercase characters converted into lowercase characters.
stl := s.to_lower()
println(stl)   // -->  this is a replaced string ...and appended ...and added with add method


// string.to_upper() --> str : return a string with all lowercase characters converted into uppercase characters.
stu := s.to_upper()
println(stu)   // -->  THIS IS A REPLACED STRING ...AND APPENDED ...AND ADDED WITH ADD METHOD


// string.substr(int_start, int_end) --> str : return a sub-string from 'int_start' to 'int_end' character.
sub := s.substr(5, 15)
println(sub)   // -->  is a repla


// string.find_between('str_start', 'str_end') --> str : return a sub-string from 'str_start' to 'str_end' string.
fb := s.find_between('replaced', 'added')
println(fb)   // -->   string ...and appended ...and
```


---
#### Casting:

```go
// value.str() --> str: transform a value in a string
iv := 123   // integer value
fv := 3.14  // float value
//converting values in strings with '.str()' method
mut sx := iv.str() + ' is an integer value, ' + fv.str() + ' is a float value'
println(sx)   // --> 123 is an integer value, 3.140000 is a float value
```

##### (Unofficial Docs & Tutorials by [Fabreath](https://gitlab.com/fabreath))