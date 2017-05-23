# Expansion using EDN Readers

Uses this [transformation function](https://github.com/cognitect-labs/vase/blob/master/src/com/cognitect/vase/literals.clj) in Vase

```Clojure
#vase/schema-tx [[:pet-store.pet/id :one :long :unique "The id of a pet"]
                 [:pet-store.pet/name :one :string "The name of a pet"]
                 [:pet-store.pet/tag :one :string "The tag of a pet"]]
```

* Transform Readability : 4/5      can see output shape easily in fn
* Transform Safety :         4/5      lots of code, why not spec?
* Transform Versatility :   5/5      reader macros can read any custom shape

Other implications of using the reader? Discuss!

