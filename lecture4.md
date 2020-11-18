## Lecture4: Data Wrangling

2. Find the three most common last two letters of those words:

   ```shell
   cat /usr/share/dict/words | grep ".*a.*a.*a.*[^s]$" | sed -E 's/.*(..)$/\1/' | sort | uniq -c | sort -nk1,1 | tail -n3
   ```

   How many of those two-letter combinations are there:

   ```shell
   cat /usr/share/dict/words | grep ".*a.*a.*a.*[^s]$" | sed -E 's/.*(..)$/\1/' | sort | uniq -c | wc -l
   ```

3. ```shell
   sed -i 's/before/after/g' file
   ```

6. ```shell
   wget https://ucr.fbi.gov/crime-in-the-u.s/2016/crime-in-the-u.s.-2016/topic-pages/tables/table-1
   ```

   Find the min and max of one column in a single command:

   ```shell
   cat table-1 | pup 'td.group1 text{}' | tr -s '\n' | awk 'NR>2{print p}{p=$0}' | sort | sed -n '1p;$p'
   cat table-1 | pup 'td.group2 text{}' | tr -s '\n' | awk 'NR>2{print p}{p=$0}' | sort | sed -n '1p;$p'
   ```

   Sum of each colomn:

   ```shell
   cat table-1 | pup 'td.group1 text{}' | tr -s '\n' | awk 'NR>2{print p}{p=$0}' | sort > data1.txt
   cat table-1 | pup 'td.group2 text{}' | tr -s '\n' | awk 'NR>2{print p}{p=$0}' | sort > data2.txt
   
   paste -s -d + data1.txt | sed 's/,//g' | bc -l
   paste -s -d + data2.txt | sed 's/,//g' | bc -l
   ```

   Find the difference:

   ```shell
   d1=$(paste -s -d + data1.txt | sed 's/,//g' | bc -l)
   echo $d1
   
   d2=$(paste -s -d + data2.txt | sed 's/,//g' | bc -l)
   echo $d2
   
   echo $[$d1-$d2]
   ```

   

   



