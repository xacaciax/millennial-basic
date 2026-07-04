# Bash in 5 Minutes — Cheat Sheet

## The core idea
Bash is just: **run a program, give it options, tell it what to act on.**
Almost everything follows this pattern:

```bash
command -flags argument
```

Example: `zip -r obsidian_backup.zip obsidian_backup` → command, flag, output name, input name.

---

## 1. Moving around

```bash
pwd          # "print working directory" - where am I?
cd folder    # move into folder
cd ..        # move up one level
cd ~         # jump home
ls           # list what's here
ls -la       # list, including hidden files (-a), in detail (-l)
```

## 2. Files & folders

```bash
mkdir name       # make a folder
touch file.txt   # create an empty file
cp source dest   # copy
mv source dest   # move (also used for renaming!)
rm file          # delete a file (no trash bin — be careful)
rm -r folder     # delete a folder and everything in it
```

## 3. Looking inside things

```bash
cat file.txt     # dump entire file to screen
head file.txt    # first 10 lines
tail file.txt    # last 10 lines
```

## 4. Pipes and redirects (the real power)

- `|` (pipe) = take the output of one command and feed it as input to the next
- `>` = take output and write it to a file (overwriting)
- `>>` = same, but append instead of overwrite

```bash
ls | wc -l                # list files, then count how many lines (= how many files)
echo "hello" > note.txt   # write "hello" into note.txt
```

## 5. Finding things

```bash
find ~ -name "*.md"        # find files by name pattern
grep "word" file.txt       # search for "word" inside a file
grep -r "word" folder/     # search recursively through a folder
```

## 6. Variables and loops

```bash
name="Claude"
echo $name          # prints: Claude

while read line; do
  echo "$line"
done < file.txt      # runs the loop once per line in file.txt
```

---

## The one habit that saves you

Before running anything destructive (`rm`, overwriting with `>`), run `echo` first to preview what will happen:

```bash
echo rm -r obsidian_backup    # just prints the command, doesn't run it
```
