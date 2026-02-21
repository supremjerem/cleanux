# cleanux

A bash script to remove Emacs backup and auto-save files from a directory.

## Targets

| Pattern | Description |
|---------|-------------|
| `*~`    | Backup files (e.g. `file.txt~`) |
| `.*~`   | Hidden backup files (e.g. `.file.txt~`) |
| `#*#`   | Auto-save files (e.g. `#file.txt#`) |

## Usage

```
cleanux [-h] [-n] [-r] [DIRECTORY]
```

If no directory is specified, the current directory is used.

## Options

| Flag | Long form | Description |
|------|-----------|-------------|
| `-h` | `--help` | Show the help message |
| `-n` | `--dry-run` | Show files that would be deleted without deleting them |
| `-r` | `--recursive` | Clean all subdirectories recursively |

## Examples

```bash
# Clean the current directory
cleanux

# Preview what would be deleted (dry run)
cleanux -n

# Clean a specific directory recursively
cleanux -r ~/projects/myproject

# Dry run, recursive, on a system directory
sudo cleanux -n -r /etc
```

## Requirements

- bash 4.0+
- Standard Unix utilities: `tput`, `find`

## Notes

- Requires `sudo` only when the target directory is not writable by the current user.
- Colors are automatically disabled on terminals that don't support them.
