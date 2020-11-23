## Lecture7: Debugging and Profiling

### Debugging

1. ```shell
   log show --last 24h | grep sudo
   ```

3. ```shell
   #!/bin/sh
   
   for f in *.m3u
   do
       grep -qi 'hq.*mp3' \
       && echo "Playlist $f contains a HQ file in mp3 format"
   done
   ```

### Profiling

5. ```shell
   # cProfile
   python -m cProfile -s tottime sorts.py
   
   # line_profiler
   kernprof -l -v sorts.py
   
   # memory_profiler
   python -m memory_profiler sorts.py
   ```

6. ```shell
   pycallgraph graphviz -- ./fib.py
   ```

7. ```shell
   python -m http.server 4444
   lsof | grep LISTEN
   kill 12394
   ```

8. ```shell
   stress -c 3
   # taskset is not available on MacOS
   taskset --cpu-list 0,2 stress -c 3
   ```

9. ```shell
   curl ipinfo.io
   ```

