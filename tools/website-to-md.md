# CONVERTING A WEBSITE INTO MARKDOWN

## INSTALL pandoc

```
sudo apt install pandoc
```

- Run this command in the directory where it will be downloaded

```
wget -O - http://example.com | pandoc -f html -t markdown > example.md
```
