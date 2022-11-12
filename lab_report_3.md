# Lab Report 3

## grep

---

## *-i*


The `-i` makes case of the input not matter. This is useful for finding terms in a specific file without worrying about the case of the letters.

```
$ grep -i risk technical/biomed/1468-6708-3-1.txt
        excess risk for persons with very low BMI, but that persons
        with moderately high BMI had little or no extra risk except
        In older adults, risk factors may have a greater effect
        whom risk factors, subclinical disease, and morbidity are
          33 34 ] . For older adults, the risks associated with
          effects of obesity on risk factors for future health. A
        no excess risk for older adults who would be classified as
```

- This grep command simply looks for all the times the inputed term "risk" shows up in the file of the inputed path.


```
$ grep -i sUiTaBle technical/government/Env_Prot_Agen/atx1-6.txt
        toxicity tests. They are also suitable for determining the toxicity
        adequate, qualified technical staff and suitable space and
        Suitable trout chow, Artemia, and other foods must be obtained as
        potassium dichromate (K2Cr2O7), are suitable for use in the NPDES
        disposable plastic test chambers are suitable. Test chamber volumes
        checked against known suitable reference cysts by performing a
        Additional species may be suitable for toxicity tests in
        water or a freshwater such as well water or a suitable surface
```

- Even if the caseing for the input word was messed up as shown, using the `-i` in our grep command still works to find the inputed words in any case



```
$ grep -i ALPHABET technical/911report/chapter-13.4.txt > alphabetLines.txt

In alphabetLines.txt:

                problem, as KSM had to send emails in Arabic using the English alphabet. Ibid. In

```

- With this command, search through a specific directory to look for the ALPHABET.
- Notice how using the `-i` command makes the all uppercase input not matter, and search for all terms with the letters in the input.


---

## *-r*

The `-r` is a very useful command that allows us to look through all files withen a given folder. This command extension could be very handy giving us the option to look through all files in a folder rather tahn limiting us to only look through one file at a time.

```
$ grep -r fantastic
technical/plos/journal.pbio.0020148.txt:        ‘That was a fantastic time’, says Derek Stemple, then a postdoc with Driever but now a
technical/plos/journal.pbio.0020306.txt:        information that leads to spinoffs for nanotechnology, that will be fantastic’, she
```


- This command returns all the file diretories in our working directory that contains the word fantastic


```
$ grep -r rabbit technical/plos/
technical/plos/journal.pbio.0020348.txt:        Antoine Ranvier had already observed that some muscles of the rabbit were redder in color,
technical/plos/pmed.0020018.txt:          secondary anti-rabbit or anti-mouse antibodies. For the detection of transfected ROCK1
technical/plos/pmed.0020045.txt:          States), rabbit polyclonal anti-CD36 (Santa Cruz Biotechnology), rabbit polyclonal
technical/plos/pmed.0020045.txt:          States), rabbit polyclonal phospho38/MAPK and mouse monoclonal p38 (Cell Signaling
technical/plos/pmed.0020045.txt:          Technology, Beverly, Massachusetts, United States), rabbit polyclonal p-src (Y418)
technical/plos/pmed.0020045.txt:          revealed with horse radish peroxidase (HRP)-conjugated anti-mouse IgM, or anti-rabbit IgG
technical/plos/pmed.0020061.txt:        thalidomide induced gross defects in rabbits but not in rats, these guidelines called for
technical/plos/pmed.0020061.txt:        rabbits, but not rats; functional effects have only recently been described [81].
technical/plos/pmed.0020103.txt:          Missouri, United States), mouse anti-β-tubulin III, 1:500 (Sigma); rabbit anti-C-peptide,
technical/plos/pmed.0020103.txt:          (Novocastra, Newcastle, United Kingdom); rabbit anti–cleaved caspase-3, 1:200 (Cell
technical/plos/pmed.0020103.txt:          Signaling, Beverly, Massachusetts, United States); rabbit anti-glucagon, 1:200 (Dako,
technical/plos/pmed.0020103.txt:          Carpinteria, California, United States); rabbit anti-Glut-2, 1:200 (ADI, San Antonio,
technical/plos/pmed.0020103.txt:          (Sigma); and rabbit anti-Olig2, 1:1,000 (H. Takebayashi, National Institute for
```

- This command uses the `-r` extension to recusively look through the folder that was inputed for the word "rabbit"


```
$ grep -r temporarily technical/911report/  technical/plos/ > temporarilyRecurences.txt


In temporarilyRecurences.txt:

technical/911report/chapter-11.txt:                was no conscious decision to stop the operation after the trail was temporarily lost
technical/911report/chapter-13.4.txt:                operation to stop temporarily. Intelligence report, interrogation of Nashiri, Feb.
technical/911report/chapter-6.txt:            Though Nawaf 's trail was temporarily lost, the CIA soon identified"Khalid" as Khalid
technical/911report/chapter-7.txt:                in Karachi and stayed there temporarily before being deployed to the United States
```

- This command shows how you can recurently look through two different folders.
- It then funnels the results in a file called "temporarilyRecurences.txt"


---

## *-c*

`-c` is a command extension that returns the number of times the input appears in a directory. This is useful to find out how many of a certain term comes up in different files. For example, if it was statistical data, you can find out the number of times a type of data was shown if you don't care about where specifically.

```
$ grep -c cat technical/plos/pmed.0020246.txt
30
```

- This command outputs the number of times cat appears in a file, using the `-c` option.


```
$ grep -c cat technical/911report/chapter-1.txt technical/911report/chapter-2.txt technical/911report/chapter-3.txt
technical/911report/chapter-1.txt:62
technical/911report/chapter-2.txt:23
technical/911report/chapter-3.txt:82
```

- This command uses `-c` to count how many times the term "cat" appeared in three differnt files, and outputs how many appeared next to each path of the files.



```
$ grep -c funny technical/government/About_LSC/Progress_report.txt 
0
```
- This is a demonstration if none of the words in the file are the input word, in this case "funny".
- The output differs slightly by simple outputing 0 without the path next to it.
