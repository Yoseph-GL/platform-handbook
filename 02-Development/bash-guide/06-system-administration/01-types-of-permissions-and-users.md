# Bash System Administration: Types of Permissions and Users

## Architecture / Rationale

Every file and folder in Unix has an owner, a group, and a set of permissions. Permissions decide who can do what.

Three user categories:
- **Owner (user)**: the person who created the file.
- **Group**: a set of users who share access.
- **Others (world)**: everyone else.

Three permission types:
- **Read (r)**: see the content of a file or list a folder.
- **Write (w)**: modify a file or add/delete files in a folder.
- **Execute (x)**: run a file as a program or enter a folder.

## Query / Code Blocks

```bash
# See permissions with ls -l
ls -l

# Output: -rwxr-xr-- 1 user group 1234 Jan 1 12:00 file.txt
# |  |  |  |
# |  |  |  +-- others: r--
# |  |  +----- group:  r-x
# |  +-------- owner:  rwx
# +----------- type:   - (file), d (directory), l (symlink)

# See which groups you belong to
groups
```

## Performance / Optimization Notes

- Folders need execute (`x`) permission to be opened. Without it, you cannot `cd` into them even with read permission.
- The root user (UID 0) ignores all permissions. Root can read, write, and execute anything.
- Permissions are the first line of defense. A web server running as a normal user cannot modify system files.
