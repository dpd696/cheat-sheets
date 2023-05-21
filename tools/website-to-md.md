# CONVERTING A WEBSITE INTO MARKDOWN

1. Install Pandoc

```
sudo apt install pandoc
```

2. Run this command in the directory where it will be downloaded

```
wget -O - http://example.com | pandoc -f html -t markdown > example.md
```

# Best-Practices & Post-Installation

## Clean Up

It does not transfer format 100% so use something like Obsidian to Edit file. 

# Additional Referfences

[Markdown Cheat-Sheet](https://github.com/dpd696/cheat-sheets/blob/main/misc/markdown.md)