# Datomic Schema is Meta-Data

Maps are great for computers reading key-value data but not so good for meat-computers.

All this for 3 database attributes:

```
 {:db/id #db/id[:db.part/db]
  :db/ident :country/name
  :db/valueType :db.type/string
  :db/cardinality :db.cardinality/one
  :db/unique :db.unique/value
  :db/doc "The name of the country"
  :db.install/_attribute :db.part/db}

 ;; artist attributes
 {:db/id #db/id[:db.part/db]
  :db/ident :artist/gid
  :db/valueType :db.type/uuid
  :db/cardinality :db.cardinality/one
  :db/unique :db.unique/identity
  :db/index true
  :db/doc "The globally unique MusicBrainz ID for an artist"
  :db.install/_attribute :db.part/db}

 {:db/id #db/id[:db.part/db]
  :db/ident :artist/name
  :db/valueType :db.type/string
  :db/cardinality :db.cardinality/one
  :db/fulltext true
  :db/index true
  :db/doc "The artist's name"
  :db.install/_attribute :db.part/db}
```

A lot of meta-data is nested and recursive and this makes it harder to read. The example above does not show recursion but Datomic schema is recursive for _Component Attributes_

