# Conclusions

Data macros are a useful general technique and are very useful when creating readable data DSL's i.e. systems meta-data

Lots of projects are doing this. You probably will too.

A combination of Spec conform and native Clojure seems to be the _simplest_ way to expand data. It supports recursion natively and works well for vector -&gt; map transformations which seems to be how most **terse** DSLs are being built.

Comments welcome at the Clojure [Google group in this thread](https://groups.google.com/forum/#!topic/clojure/XJqm4LCGSk0)

