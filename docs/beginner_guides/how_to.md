### Convert a string to an array of chars?

```clojure
(def phrase "foobar")
(def result (vec phrase))
; => [\f \o \o \b \a \r]
```