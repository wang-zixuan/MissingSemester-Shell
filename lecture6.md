## Lecture6: Version Control (Git)

2. ```shell
   git clone git@github.com:missing-semester/missing-semester.git
   ```

   1. ```shell
      git log --all --graph --decorate
      ```

   2. ```shell
      git log -- README.md
      ```

   3. ```shell
      git blame _config.yml
      git show a88b4eac
      ```

3. ```shell
   cd demo
   echo "Passwd: 123456" > passwd.txt
   git add passwd.txt
   git commit -m "Add password file"
   ```

   ```shell
   git filter-branch --force --index-filter "git rm --cached --ignore-unmatch passwd.txt"
   ```

4. ```shell
   git clone https://github.com/wang-zixuan/Missing_Semester_IAP_2020_Shell.git
   ```

   And then I make some changes in README.md,

   ```shell
   git stash
   git log --all --oneline
   git stash pop
   ```

5. ```shell
   vim ~/.gitconfig
   ```

   ```shell
   [alias]
           graph = log --all --graph --decorate --oneline
   ```

6. ```shell
   git config --global core.excludesfile ~/.gitignore_global
   vim ~/.gitignore_global
   ```