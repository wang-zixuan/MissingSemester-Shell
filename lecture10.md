## Lecture 10: Potpourri

### Daemons

It's a series of processes that are always running in the background rather than waiting for a user to launch them and interact with them.

### Backups

Off-site backup is a recommended practice.

### Commin command-line flags/patterns

- `--help`, `--version`, `-V`, `-vvv`, `--quiet` are supported by most tools.
- `--` makes a program stop processing flags and options in what follows, such as `rm -- -r` and `ssh machine --for-ssh -- foo --for-foo`.