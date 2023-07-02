### #1
If you make two namespaces with the same name, interesting things happen. 
For example, use `example.clj`.

In `deps.edn` have `:paths ["src" "test"]`.
Then put both namespaces under test and src in the same directory structure with the namespace of, say, `main.example`. If you put it under `src/main/example.clj` and `test/main/example.clj`.

Add one def to each file `(def foo "bar")` and `(def foo "baz")` respectively. 

Now require in your repl in the form `(require '[main.example :as me])`?

What will `me/foo` return? In my case it returned `bar` but I wouldn't trust that. In general, don't have identical namespaces. 