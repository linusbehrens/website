# Website with saait

```sh
for file in markdown/*.md; do pandoc "$file" -o "html/$(basename "${file%.md}.html")"; done
```

```sh
rm output/*css
cp css/* output
find pages -type f -name '*.cfg' -print0 | sort -zr | xargs -0 saait
```

