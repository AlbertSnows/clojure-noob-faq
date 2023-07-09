### Map Keys
Problem: I need a data structure that allows me to add values at arbitrary indexes to access later, the indexes specifically need to be numbers.

Solution: Use a map, it should probably work depending on your use case. You don't have to index via traditional keywords, but you should look at the docs to see how not-trad keywords, like numbers or strings, work.
for example normally (:x {:x "foo"}) works fine but won't work if it's (7 {7 "foo"})
instead you have to do either ({7 "foo"} 7) or (get {7 "foo"} 7)
And thanks to everyone who offered input in the thread.
doc: https://clojure.org/guides/learn/hashed_colls

### Namespaces
If you make two namespaces with the same name, interesting things happen. 
For example, use `example.clj`.

In `deps.edn` have `:paths ["src" "test"]`.
Then put both namespaces under test and src in the same directory structure with the namespace of, say, `main.example`. If you put it under `src/main/example.clj` and `test/main/example.clj`.

Add one def to each file `(def foo "bar")` and `(def foo "baz")` respectively. 

Now require in your repl in the form `(require '[main.example :as me])`?

What will `me/foo` return? In my case it returned `bar` but I wouldn't trust that. In general, don't have identical namespaces. 