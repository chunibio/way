# telia
Statically typed data oriented garbage collected programming language

##### Implamented in Rust. Inspired by Rust, Scala, Dyon

### Features:
- statically typed
- type inference

### Basic Example
```telia

hello() -> ... (

)

main  (

)
```

### Data Structures
```telia

empty_tuple <- ()
empty_list <- []
empty_set <- {}
```

### Grammar
```ohm
Telia {
  Exp
    = Block
    | CallableUnit
    
  Block
  	= "(" Exp ")"  --paren
    | "_"
    
  CallableUnit 
  	= Function
    | Procedure
    
  Function
  	= ident Block* right_arrow Block
    
  Procedure
  	= ident Block
    
  ArgList
  	= (Arg ";") *
    
  Arg
  	= ident ":" type_ident
    
   
  
    
    
  
    
  right_arrow
  	= "->"
    
  type_ident
  	= upper alnum*
  
  ident  (an identifier)
    = letter alnum*

  number  (a number)
    = digit* "." digit+  -- fract
    | digit+             -- whole
    
   AddExp
    = AddExp "+" MulExp  -- plus
    | AddExp "-" MulExp  -- minus
    | MulExp

  MulExp
    = MulExp "*" ExpExp  -- times
    | MulExp "/" ExpExp  -- divide
    | ExpExp

  ExpExp
    = PriExp "^" ExpExp  -- power
    | PriExp

  PriExp
    = "(" Exp ")"  -- paren
    | "+" PriExp   -- pos
    | "-" PriExp   -- neg
    | ident
    | number
    
}
```

### Resources
- https://cs.lmu.edu/~ray/notes/languagedesignnotes/
- http://web.cs.ucla.edu/~todd/theses/warth_dissertation.pdf
- https://github.com/harc/ohm
- https://github.com/harc/ohm/blob/master/doc/syntax-reference.md
- https://ohmlang.github.io/editor/#
- https://users.rust-lang.org/t/what-is-the-difference-between-rhai-gluon-dyon-and-monkey/35522/2
- https://github.com/gluon-lang/gluon

### Influenced by
- https://github.com/PistonDevelopers/dyon
