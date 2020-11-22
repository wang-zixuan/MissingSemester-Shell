## Lecture 11: Q & A

1. Difference between `source script.sh` and `./script.sh`

   For `source` the commands are executed in current bash session and any changes made to the current environment will persist in the current session once the `source` command finishes executing. When running scripts standalone, current bash session starts a new instance of bash, and the parent session remains in the same place.

2. Filesystem

- `/bin`: command binaries
- `/sbin`: system binaries
- `/dev`: device files
- `/sys`: information and configuration for the system
- `/usr`: read-only user data

3. Web browser

- Chrome / Firefox / Microsoft Edge: Blink
- Safari: WebKit