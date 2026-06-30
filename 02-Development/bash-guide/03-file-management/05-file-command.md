# Bash File Management: File Command

## Architecture / Rationale

The `file` command tells you what kind of data a file contains. It looks at the content, not the extension. A file named `photo.jpg` could actually be a PNG, and `file` will tell you.

- `file` reads the first bytes of a file and matches them against known patterns (magic numbers).
- It works even if the file has no extension or a wrong extension.
- It distinguishes between text files, binaries, images, archives, and scripts.

## Query / Code Blocks

```bash
# Check a single file
file document.pdf

# Check multiple files
file photo.jpg archive.zip script.sh

# Check all files in a folder
file *

# Show the MIME type (useful for web servers)
file --mime-type image.png
```

## Performance / Optimization Notes

- Use `file` before opening an unknown file. It prevents opening a binary file in a text editor by mistake.
- File extensions in Unix are optional. `file` is the reliable way to know what something is.
- `file` reads only the first few bytes. It is fast even on large files.
