# Expansion using Clojure De-structuring

```Clojure
(let [transform (fn [[attribute-name cardinality data-type description]]    ; input shape
                  {:db/id                 '(datomic.api/tempid :db.part/db) ; output shape
                   :db/ident              attribute-name
                   :db/valueType          (keyword "db.type" (name data-type))
                   :db/cardinality        (keyword "db.cardinality" (name cardinality))
                   :db.install/_attribute :db.part/db
                   :db/doc                description})]
  (transform [:pet-store.pet/id :one :long "The id of a pet"]))

  => {:db/id (datomic.api/tempid :db.part/db),
      :db/ident :pet-store.pet/id,
      :db/valueType :db.type/long,
      :db/cardinality :db.cardinality/one,
      :db.install/_attribute :db.part/db,
      :db/doc "The id of a pet"}
```

* Transform Readability : 5/5     easy to see input and output shape
* Transform Safety :         4/5     none above but adding Specs to the fn would provide safety
* Transform Versatility :   4/5     works for any input and output shape. needs extra code for recursion



