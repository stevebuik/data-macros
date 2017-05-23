# Expansion using Protocols on Clojure data structures

Used in [Pedestal route expansion](https://github.com/pedestal/pedestal/blob/master/route/src/io/pedestal/http/route.clj#L351) and more detail in [Pedestal Route tests](https://github.com/pedestal/pedestal/blob/master/service/test/io/pedestal/http/route_test.clj#L153)

```
[:public "example.com"
   ["/" {:get home-page}
    ["/child-path" {:get trailing-slash}]]
   ["/user" {:get list-users
             :post add-user}
    ["/:user-id"
     ^:constraints {:user-id #"[0-9]+"}
     {:put update-user}
     [^:constraints {:view #"long|short"}
      {:get view-user}]]]
```

* Transform Readability : 3/5          lots of indirection layers, maybe due to depth of feature set
* Transform Safety :         2/5          not much obvious bad data shape checks
* Transform Versatility :   4/5          dispatching on Clojure types limits input variations but don't need many for web routing



Note: this is an example of a **recursive** terse DSL



