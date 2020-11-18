## Lecture2: Shell Tools and Scripting

1. ```shell
   ls -lsatG
   ```

2. We are now in the /tmp/missing

   ```shell
   vim macro.sh
   ```

   The function looks like:

   ```shell
   function macro() {
       cur_dir=$(pwd)
       echo "cur_dir is $cur_dir"
       echo "$cur_dir" > /tmp/missing/cur_dir.txt
   }
   ```

   And then in the shell:

   ```shell
   source macro.sh
   macro
   ```

   ```shell
   vim polo.sh
   ```

   The function looks like:

   ```shell
   function polo() {
       nav_dir=$(cat /tmp/missing/cur_dir.txt)
       cd "$nav_dir"
   }
   ```

   And then you can change your directory, and type

   ```shell
   source /tmp/missing/polo.sh
   polo
   ```

3. ```shell
   vim random.sh
   ```

   ```shell
   #!/usr/bin/env bash
   
   n=$(( RANDOM % 100 ))
   
   if [[ n -eq 42 ]]; then
       echo "Something went wrong"
       >&2 echo "The error was using magic numbers"
       exit 1
   fi
   
   echo "Everything went according to plan"
   ```

   ```shell
   chmod +x ./random.sh
   vim check.sh
   ```

   ```shell
   #!/usr/bin/env bash
   count=0
   while true; do
       ./random.sh &> tmp.txt
       if [[ "$?" -ne 0 ]]; then
           break
       fi
       count=$((count+1))
   done
   
   echo "run times: $count"
   cat tmp.txt
   ```

4. On macOS.

   ```shell
   find . -name "*.html" -print0 | xargs -0 zip -r -m html.zip
   ```

5. ```shell
   ls -lt | head -n 10
   ```

   More Generally:

   ```shell
   ls -lt
   ```

