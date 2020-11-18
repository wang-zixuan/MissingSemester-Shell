## Lecture1: Course Overview + The Shell

1. ```shell
   echo $SHELL
   ```

2. ```shell
   mkdir /tmp/missing
   ```

3. ```shell
   man touch
   ```

4. ```shell
   cd /tmp/missing
   touch semester
   ```

5. ```shell
   echo '#!/bin/sh' >> semester
   echo 'curl --head --silent https://missing.csail.mit.edu' >> semester
   cat semester
   ```

6. ```shell
   man chmod
   ```

7. ```shell
   chmod +x ./semester
   ./semester
   ```

8. ```shell
   ./semester | grep -i last-modified | cut -f2- -d ' ' > last_modified.txt
   ```

