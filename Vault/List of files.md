
# List of files

```base
views:
  - type: table
    name: Table
    groupBy:
      property: file.folder
      direction: ASC
    order:
      - file.name
      - file.folder
      - file.ext

```

```dataview
table created, file.folder
sort file.path
```