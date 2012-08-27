lein
====

Java:

    lein deps
    lein compile
    java -cp $(lein classpath) org.hanworks.MyCode

Clojure

    lein deps
    lein compile
    lein run -m org.hanworks.clj.MyC

Notes
-----

* http://sexp.posterous.com/poor-mans-integrating-leiningen-into-counterc
* Generating Eclipse project files
    * Add `[lein-eclipse "1.0.0"]` to your dependencies in your project.clj file.
    * `lein plugin install lein-eclipse "1.0.0"`
    * `lein eclipse` # generate eclipse .project and .classpath files
    * Source: http://stackoverflow.com/questions/2136792/using-clojure-and-leiningen-with-ides