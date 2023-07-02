### None of the core library is loaded in the library
1) you hopped into a namespace that doesn't exist, go back to user => (in-ns 'user)
2) refer to it => (clojure.core/refer 'clojure.core)

---