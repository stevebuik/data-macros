# Clojure Web Routing Meta-Data

An example from Pedestal:

```
 {:route-name :hello-workd
   :path       "/hello-world"
   :method     :get
   :scheme     :http               
   :host       "example.com"       
   :port       "8080"              
   :interceptors [...]             ; vector of interceptors to be enqueued on the context
   
   }
```

or in the terse form

```
[[:hello-world :http "example.com"
 ["/hello-world" {:get hello-world}]]]
```



