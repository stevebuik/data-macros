# Expansion using Tracks

Using the [Tracks library](https://github.com/escherize/tracks) from Bryan Mass

```
(let [transform (t/track
                  [attribute-name cardinality data-type description]        ; <<<===  input shape
                  {:db/id                 '(datomic.api/tempid :db.part/db) ; <<<===  output shape
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

* Transform Readability : 5/5     Tracks is designed to optimise this
* Transform Safety :         3/5     when input args are wrong, no error, just incorrect output
* Transform Versatility :   4/5     works for any input and output shape although recursion requires a walk/zipper wrapper

Not obvious how to use variable arities for input sequences.

