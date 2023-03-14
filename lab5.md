# Researching Command: find
[source](https://chat.openai.com/chat)

## 1. `find <path> -name <file name>`
- -name: Searches for files or directories with a specific name

**example1**
```

```

I use `grep -r` to search "Lucayans" under `skill-demo-data/written_2`, it searches not only in the specified files, but also in all files under the directory

**example2**
```

```

I use `grep -r` to search "Italy has" under `skill-demo-data/written_2`, instead of manually searching through each file, I can use `grep -r` to automate the process and quickly find the information I need.

- Base on examples, `find -name` can be particularly useful when you need to search for files or directories with a specific name. It takes a string argument that specifies the name of the file or directory to search for.

## 2. `find <path> -type <file type>`
- -type: Searches for files of a specific type

**example1**
```

```
I use the `grep -c` to count the number of lines that match "Italy" under `skill-demo-data/written_2/travel_guides/berlitz1/*.txt`, it shows HistoryFrance.txt has 3 matched lines, HistoryGreek.txt has 1 matched line, and so on

**example2**
```

```
I use the `grep -c` to count the number of lines that match "Lucayans" under `skill-demo-data/written_2/travel_guides/berlitz1/*.txt`, it shows only Bahamas-History.txt has 2 matched lines.

- Base on examples, `find -type`can be useful when you want to search for files of a specific type. It allows you to filter the search results based on the type of file

## 3. `find <path> -mtime <days>`
- -mtime: Searches for files that were modified a specific number of days ago

**example1**
```

```
I use the `grep -w` to match the whole word "sainthood" under `skill-demo-data/written_2/travel_guides/berlitz2/*.txt`, it shows the whole word in the last sentense.

**example2**
```

```
I use the `grep -w` to match the whole word "Lucayans" under `skill-demo-data/written_2/travel_guides/berlitz2/*.txt`, it shows that Bahamas-history has two paragraphs mention the whole word "Lucayans".

- Base on examples, `find -mtime` can be useful when you want to search for files based on their modification date. The sign of the argument determines whether to search for files that were modified more than (+), less than (-), or exactly (=) the specified number of days ago. It is a powerful tool for locating files that have been modified recently or a long time ago.

## 4. `find <path> -size <specific size>`
- -size: Searches for files of a specific size

**example1**
```

```
I use the `grep -n` to find the lines that match the word "sainthood" under `skill-demo-data/written_2/*.txt`, it shows the word is in the line 48 in Portugal-history.

**example2**
```

```
I use the `find -size` to find the lines that match the word "Lucayans" under `skill-demo-data/written_2/*.txt`, it shows the word is in the line 6 and 7 in Bahamas-history.

- Base on examples, `find -size` can be useful when you want to search for files based on their size. The size can be specified in bytes, kilobytes (with the suffix k or K), megabytes (with the suffix m or M), or gigabytes (with the suffix g or G).
