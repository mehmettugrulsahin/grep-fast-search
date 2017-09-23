# Use Grep for Fast Search from the Command Line

## 1. Search the contents of files using grep

```bash
grep version package.json
grep gulp package.json
```

```bash
grep "#" codestyle.md contributing.md readme.md
grep "#" *.md
```

## 2. Search directory contents recursively using grep
```bash
grep toggle .
grep toggle ./*

grep -r toggle .
grep -r toggle examples/react/js
```

## 3. Use find to search for filename patterns
```bash
find . -name "*jsx"
find . -name "*md"
```

```bash
find examples/ -name "*Spec.js"
```

## 4. Search matching files by combining find and grep with xargs
```bash
find examples -name "*Spec.js | xargs"
find examples -name "*Spec.js | echo"
```

```bash
find examples -name "*Spec.js" | xargs grep "describe"
find examples -name "*Spec.js" | xargs grep "should"
```

```bash
grep -r --include="*Spec.js" "should " examples/
```

## 5. Search the contents of a git repository with git grep
```bash
grep -r bind
```

```bash
git grep bind
grep -r --color bind .
```

## 6. Show context around matches using grep
```bash
grep "#" *.md
grep -n "#" *.md
grep -A 2 *.md

grep -A 2 "#" *.md
grep -A 2 --color "#" *.md
grep -B 2 --color "#" *.md
grep -C 2 --color "#" *.md
```

```bash
grep --color -n -C 2 "#" *.md
```

## 7. Search for basic patterns using grep
```bash
grep --color "h." readme.md
grep --color "http." readme.md
```

```bash
grep --color "\.com" readme.md
grep --color "##*" readme.md
```

```bash
grep --color "(.*)" readme.md
```

## 8. Use grep's extended regular expressions to find complex patterns
```bash
grep --color "https" readme.md
grep --color "http." readme.md
```

```bash
grep --color "https\?" readme.md
grep --color "https\+" readme.md
```

```bash
grep --color "#*" readme.md
grep --color "#\+" readme.md
grep --color "##\+" readme.md
```

```bash
grep --color -E "###?" readme.md
grep --color -E "###+" readme.md
or
grep --color "###\?" readme.md
grep --color "###\+" readme.md
```

## 9. Search for optional patterns with grep OR
```bash
echo "is it grey or gray?" | grep --color "grey\|gray"
or
echo "is it grey or gray?" | grep --color -E "grey|gray"
```

```bash
grep --color -rE "grey|gray" examples/
```

## 10. Specify line beginning and end in patterns using grep
```bash
grep "#" app-spec.md
grep --color "^#" app-spec.md
```

```bash
grep --color "," app-spec.md
```

```bash
grep --color -r "^import .* from" examples/
```

## 11. Match classes of characters using bracket expressions with grep
```bash
echo abc123 | grep --color "[ab]"
echo abc123 | grep --color "[a-z]"
echo abc123 | grep --color "[1-9]"
```

```bash
grep --color "de[a-z]*er" readme.md
or
grep --color "de[[:alpha:]]*er" readme.md
```

```bash
find . -name "*js" | grep --color -E "[sS]pec"
```

## 12. Search with groups using grep
```bash
grep -rE "grey|gray" .
grep -rE --color "(grey|gray)\'" .
grep -rE --color "(grey|gray)(\'|\")" .
grep -rE --color "(grey|gray)(\'|\"): (\'|\")#?[[:xdigit:]]+" .
```

## 13. Find matches excluding a pattern with grep
```bash
find examples/agularjs -name "*js"
find examples/agularjs -name "*js" | grep -v "node_modules"
find examples/agularjs -name "*js" | grep -vE "node_modules|Spec"
```


