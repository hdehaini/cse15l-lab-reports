# Lab Report 3

## grep

---

## *-i*


- The `-i` makes case of the input not matter.
- This is useful for:
    - Finding terms in a specific file.
    - To find all terms with the letters of the input, without worryingabout the case of the letters.

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
$ grep -r -i ALPHABET
technical/911report/chapter-13.4.txt:                problem, as KSM had to send emails in Arabic using the English alphabet. Ibid. In
technical/911report/chapter-13.5.txt:                to be translated into the Roman alphabet, ensuring one common spelling for all
technical/biomed/1471-2105-3-12.txt:          in the characterization of an "alphabet" of putatively
technical/biomed/1471-2105-3-12.txt:            elucidation of an "alphabet" of essential genes
technical/biomed/1471-2105-3-18.txt:            (e.g. the observable alphabet, a,c,g,u for RNA). I will
technical/biomed/1471-2105-3-2.txt:            the output from these links are sorted alphabetically.
technical/biomed/1471-2105-3-2.txt:            (black text). Diagrams are listed alphabetically by
technical/biomed/1471-2105-3-2.txt:            entries are sorted alphabetically first by their
technical/biomed/1471-2105-3-2.txt:            order. The alphabetical/numerical order for any
technical/biomed/1471-2105-3-28.txt:          number of coordinates required to represent the alphabet
technical/biomed/1471-2105-3-28.txt:          required. If, for example, an alphabet of 4 is required,
technical/biomed/1471-2105-3-28.txt:          coordinates from 2 to 3. If, however, an alphabet of 20
technical/biomed/1471-2105-3-6.txt:          are alphabetic characters) by a unique binary number -
technical/biomed/1471-2164-4-6.txt:          ] we have chosen the alphabetically minimal name.
technical/biomed/1471-2253-2-4.txt:        and alphabetically within a year.
technical/biomed/1472-6882-1-10.txt:          alphabetical order.
technical/biomed/1472-6882-3-3.txt:        Annotated Alphabetic list, 2002 [ 6 ] . While the National
technical/biomed/1472-6882-3-3.txt:          Headings-Annotated Alphabetic List, 2001, which was the
technical/biomed/gb-2003-4-1-r7.txt:          of representing each GO process as an alphabetical list
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:original statements (Volume I) and to standards alphabetized by
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:presents the standards alphabetized by topic, pulls together all
technical/government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:organized alphabetically by topic. Topics will be specific
technical/plos/pmed.0020028.txt:        incrementally to the alphabet soup of public health. But instead, we could choose to
```

- With this command, we recusivly searched through all the files in /technical using the `r` command and searched for the term 'ALPHABET'.
- Using the `-i` command makes the all uppercase input not matter, and search for all terms with the letters in the input.


---

## *-H*

---

## *-c*

```
$ grep -c cat technical/plos/pmed.0020246.txt
30
```

- This command outputs the number of times the input appears in a file, using the `-c` option.
- This is useful if you just wanted to know if a term appears in a file or files, and how many times, rather than where in-text specifically.
