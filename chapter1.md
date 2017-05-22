# What is a macro?

A transformation of code \(data\) to different code e.g. 

```
(macroexpand
  '(when true 1))
  
=> (if true (do 1))  
```



