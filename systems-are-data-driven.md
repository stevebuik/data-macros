# Systems are data driven

or more accurately, **meta data** driven     \( not the Clojure kind i.e.`(with-meta {})` but the system config kind \)

System Phase examples of meta-data :

* **Compile time** : all code is meta-data, especially Clojure i.e. `[1]` and `(do 1)` are both data. So is `var count = 0;` or any code
* **Startup time** : environment variables, JVM System properties, config files
* **Run-time** : Multi-tenant SAAS meta data is read for each request. Each tenant has a different experience.



