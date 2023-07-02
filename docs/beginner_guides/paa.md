### None of the core library is loaded in the library
1) you hopped into a namespace that doesn't exist, go back to user => (in-ns 'user)
2) refer to it => (clojure.core/refer 'clojure.core)

---

### Failed to read artifact descriptor for xyz 

It's basically just saying your project directory is making intellij (and maybe git) angry, but also that it's trying to get your dependencies from somewhere that doesn't exist. The problem happened again when I added this line => :mvn/local-repo ".m2/repository"and didn't have a .m2 directory, and also I couldn't recreate the problem in a repo that didn't have git, but I'm dubious that git actually matters.
solution 2: do not have :mvn/local-repo ".m2/repository" in your deps.edn unless you know what you're doing I guess (that is, unless you have a .m2 directory). 

(old) solution: revert your project to as close as possible to what a default project structure would look like. In general, the approach should be

project
|- /src/
|- /test/
|- deps.edn
