# Clojure Web Routing Meta-Data

An example from Pedestal. A **verbose** route:

```
 { :route-name :hello-world
   :path       "/hello-world"
   :method     :get
   :scheme     :http               
   :host       "example.com"       
   :port       "8080"              
   :interceptors [hello-world]
   }
```

or in the **terse** form

```
[[:hello-world :http "example.com"
  ["/hello-world" {:get hello-world}]]]
```

Why have a **terse** form? Readability!

