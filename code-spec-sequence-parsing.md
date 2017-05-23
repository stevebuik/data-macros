# Expansion using Clojure Spec sequence parsing

\(s/cat ....\) is a regular expression matcher which expands to a map

Seen in [blog post from Frankie Sardo](https://juxt.pro/blog/posts/parsing-routes-clojure-spec.html)

```
[["/" ^:interceptors [:json-body]
  ["/pets" {:get :retrieve-all-pets
            :post :create-pet}
   ["/:id" ^:constraints {:id #"/d+"} ^:interceptors [:pet-exists]
     {:get :retrieve-pet-by-id
      :put :update-pet-by-id}]]]]
```

becomes

```
[{:path "/"
  :interceptors [:json-body]
  :children [{:path "/pets"
              :handlers {:get :retrieve-all-pets
                         :post :create-pet}
              :children [{:path "/:id"
                          :constraints {:id #"/d+"}
                          :interceptors [:pet-exists?]
                          :handlers {:get :retrieve-pet-by-id
                                     :put :update-pet-by-id}}]}
             {:path "/orders"
              :handlers {:get :retrieve-all-orders}}]}]
```

* Transform Readability : 5/5       no code at all! just Specs
* Transform Safety :         5/5       total safety since Spec conforms everything
* Transform Versatility :   2/5 .     only works for sequences -&gt; maps

Other input shapes can be conformed but then code is required for the transform step.

