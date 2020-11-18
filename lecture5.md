## Lecture5: Command-line Environment

### Job control

1. ```shell
   sleep 1000
   ```

   Then tab ```Ctrl+z```,

   ```shell
   bg %1
   pkill -9 sleep 1000 # on MacOS
   ```

2. ```shell
   sleep 60 &
   wait
   ls
   ```

   ```shell
   vim pidwait.sh
   ```

   ```shell
   function pidwait() {
       for pid in "$@"
       do
           while kill -0 "$pid"
           do
           	echo "Process $pid still exists"
           	sleep 1
           done
           echo "Process $pid terminated"
       done
       echo 'All processes terminated'
   }
   ```

### Aliases

1. ```shell
   alias dc='cd'
   ```

2. ```shell
   history 1 | awk '{$1="";print substr($0,2)}' | sort | uniq -c | sort -n | tail -n 10
   ```

### Dotfiles

1. ```shell
   mkdir ~/git/Dotfiles
   mv ~/.zshrc ~/git/Dotfiles/bashrc
   ln -s ~/git/Dotfiles/bashrc ~/.bashrc
   
   cd ~/git/Dotfiles
   git init
   git add bashrc
   git commit -m "add .bashrc"
   # ... other version control
   ```

