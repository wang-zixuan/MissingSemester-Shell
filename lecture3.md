## Lecture3: Editors (Vim)

2. ```shell
   vim ~/.vimrc
   ```

3. ```shell
   mkdir -p ~/.vim/pack/vendor/start
   cd ~/.vim/pack/vendor/start
   git clone https://github.com/ctrlpvim/ctrlp.vim
   ```

4. ```shell
   vim fizz_buzz.py
   ```

   ```python
   import sys
   
   def fizz_buzz(limit):
       for i in range(1, limit):
           if not i % 3 and not i % 5:
               print('fizz_buzz')
               continue
           if i % 3 == 0:
               print('fizz')
           if i % 5 == 0:
               print('buzz')
           if i % 3 and i % 5:
               print(i)
   
   def main(arg):
       fizz_buzz(arg)
   
   if __name__ == '__main__':
       main(int(sys.argv[1]))
   ```

   ```shell
   python3 fizz_buzz.py 100
   ```

8. ```shell
   vim example-data.xml
   ```

   ```shell
   Gdd
   ggdd
   ```

   Go to line with ```<name>```

   ```shell
   qe^r"f>S": "<ESC>f<C"<ESC>q
   ```

   Go to line with ```<person>```

   ```shell
   qpS{<ESC>j@eA,<ESC>j@ejS},<ESC>q
   ```

   Go to line with ```<person>```

   ```shell
   qq@pjq
   999@q
   ```

   Manually remove last ```,``` and add ```[``` and ```]``` delimiters.

   ```shell
   mv example-data.xml example-data.json
   ```

   