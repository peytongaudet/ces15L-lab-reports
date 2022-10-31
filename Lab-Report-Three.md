# CSE 15L Lab Report 3
## Peyton Gaudet (A17573280)

**Part 1: grep -c**

The command grep -c displays the count of lines that match a pattern. This can be useful for finding how often a certain pattern shows up in text.
``` 
% cat technical/*/*.txt > output1.txt
% grep -c "taxation" output1.txt
2
```
If none are found, 0 gets printed.
```
% grep -c "string that will not be found" output1.txt
0
```
If you search without putting the .txt files into a new .txt file, the output lists every file matching the format (even the ones without the matched part) and reports how many matching lines are in each file. A few lines of output are shown below:
```
% grep -c "research" technical/*/*.txt
technical/plos/pmed.0020246.txt:5
technical/plos/pmed.0020247.txt:0
technical/plos/pmed.0020249.txt:2
technical/plos/pmed.0020257.txt:3
technical/plos/pmed.0020258.txt:4
```

**Part 2: grep -n**

The command grep -n displays the matched lines and their line numbers. This can be useful for finding where a match is in the text.

```
% cat technical/*/*.txt > output1.txt
% grep -n "taxation" output1.txt 
225839:        tobacco control strategy, including legislation, taxation,
518533:        could be via general taxation, although in countries with a private health insurance system
```

If no matched lines are found, nothing gets returned.
```
% grep -n "string that will not be found" output1.txt
%
```


If you search without putting the .txt files into a new .txt file, the output lists every file with the matched pattern and ouputs the line where the match is found along with the line itself. A few lines of output are shown below:
```
% grep -n "biomed" technical/*/*.txt
technical/plos/pmed.0020212.txt:170:        other biomedical disorders. The alternative possibility is that the current findings are
technical/plos/pmed.0020249.txt:9:        countries exist. The development of a vaccine or other preventive biomedical intervention
technical/plos/pmed.0020249.txt:53:        biomedical intervention aiming to protect from infection, whereas zidovudine is most
```

**Part 3: grep -o**

The command grep -o prints only the matched parts of a matching line,
with each match on a separate output line. This command option looks like it is less useful than the others as printing the matched part over and over seems redundant. However, it can still be used to find matched texts in files.
```
% cat technical/*/*.txt > output1.txt
% grep -o "taxation" output1.txt
taxation
taxation
```

If no matched parts are found, nothing gets returned.
```
% grep -o "string that will not be found" output1.txt
%
```

If you search without putting the .txt files into a new .txt file, the output lists every file with the matched part and prints the matched part. A few lines of output are shown below:
```
% grep -o "research paper" technical/*/*.txt
technical/biomed/1471-2105-4-26.txt:research paper
technical/biomed/1472-6920-2-3.txt:research paper
technical/plos/journal.pbio.0020145.txt:research paper
```
