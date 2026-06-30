# Bash Setup: History of Bash

## Architecture / Rationale

Bash was created in 1989 by Brian Fox as a free replacement for the Bourne shell. It is part of the GNU Project. Understanding its history helps you understand why some things look the way they do.

Key milestones:
- 1971: The first Unix shell (Thompson shell).
- 1979: Bourne shell (`sh`) — the ancestor of modern shells.
- 1989: Bash 1.0 released.
- Today: Bash 5.x is the standard on Linux and macOS.

## Query / Code Blocks

```bash
# Bash is backwards-compatible with sh scripts
# A script starting with #!/bin/sh can run under Bash
```

## Performance / Optimization Notes

- Bash syntax carries decades of history. Some patterns look odd because they come from the 1970s.
- Knowing the history helps you understand why alternatives like Zsh and Fish exist.
- Bash remains the most widely installed shell. Learning it gives you the most reach.
