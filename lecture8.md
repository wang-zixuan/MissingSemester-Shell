## Lecture 8: Metaprogramming

1. ```shell
   paper.pdf: paper.tex plot-a.png
   	pdflatex paper.tex
   
   plot-%.png: %.dat plot.py
   	./plot.py -i $*.dat -o $@
   
   clean:
   	rm paper.pdf
   ```

3. ```shell
   git init
   cd .git/hooks
   mv pre-commit.sample pre-commit
   vim pre-commit
   ```

   ```shell
   #!/bin/sh
   
   # Redirect output to stderr.
   exec 1>&2
   
   if make
   then
     echo "make done."	
   else
   	cat <<\EOF
   Error: Can't make paper.pdf. 
   
   EOF
   	exit 1
   fi
   ```

