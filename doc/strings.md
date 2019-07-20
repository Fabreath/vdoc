# [V Programming language](https://vlang.io/docs)
#### (Unofficial Docs & Tutorials by [Fabreath](https://gitlab.com/fabreath))

### [doc](..\vdoc.md)/[strings](strings.md)
---

#### Declaration:
```go
// Declare with ':=' operator and single quotes 
s1 := 'This is an immutable string'
mut s2 := 'This is a mutable string'

// Example:
println(s1)   // -->  This is an immutable string
println(s2)   // -->  This is a mutable string
```

---
#### Concatenation:
String concatenation is valid only with **MUTABLE** strings.

```go
// Mutable string declaration and assignament
mut s := 'That'
println(s)   // -->  That


// Re-assignament
s = 'This'
println(s)   // -->  This


// Concatenation with '+' operator
s = s + ' is' + ' a' + ' concatenated' + ' string'
println(s)   // -->  This is concatenated string


// Appending string with '+=' operator
s += ' ...and appended'
println(s)   // -->  This is concatenated string ...and appended


// Appending string with 'add' method
s = s.add(' ...and added with add method')
println(s)   // -->  This is concatenated string ...and appended ...and added with add method
```