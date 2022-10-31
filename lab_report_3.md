# Lab Report 3
## find


```
$ find -empty
./.git/objects/info
./.git/refs/tags
```

- The `-empty ` in the command simply finds all the empty files in the working directory.
- This could be useful if you have a new file made that you want to code in, or if there are any empty, old, trash files that you wnat to find to clear out.


---


```
$ find -name "*.txt" > allTXTfiles.txt

In allTXTfiles.txt:
./allTXTfiles.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-2.txt
.
..
...
```

- This command finds all the files with ".txt" in their name, as indicated from the `-name`, and stores them in a new file called allTXTfiles.txt.
- This could be very useful if you were looking for any files of a certain type listed out, for example, .java files.

---


```
$ find . -name chapter-1.txt
./technical/911report/chapter-1.txt
```

- This command finds the path from the `.` point, of the inputed name of a file.
- This can also be useful for easily getting the path of any specific file, all you need is its name.


## grep

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

- This


---


```
$ grep -r -i alphabet
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


---


```
$ grep -c cat technical/plos/pmed.0020246.txt
30
```


## less

```
$ less -N technical/911report/chapter-1.txt



      1 
      2
      3
      4 "WE HAVE SOME PLANES"
      5 
      6     Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structu      6 res of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania A      6 venue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
      7 
      8     For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland      8 , Maine.
      9 
     10 INSIDE THE FOUR FLIGHTS
     11
     12 Boarding the Flights
     13
     14     Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.
     15
     16     When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be s     16 ubject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had bo     16 arded the aircraft. This did not hinder Atta's plans.
     17
     18     Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.   
     19
     20     It would be their final conversation.
     21
     22     Between 6:45 and 7:40, Atta and Omari, along with Satam al Suqami, Wail al Shehri, and Waleed al Shehri, checked in and boarded American Airlines Flight 11, bound for Los Angeles. The flight was scheduled to depar     22 t at 7:45.
     23
```

- This is a 

---

```
$ less -X technical/911report/chapter-1.txt

        

"WE HAVE SOME PLANES"

    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.

    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.

INSIDE THE FOUR FLIGHTS

Boarding the Flights

    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.

    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.

    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.

    It would be their final conversation.

    Between 6:45 and 7:40, Atta and Omari, along with Satam al Suqami, Wail al Shehri, and Waleed al Shehri, checked in and boarded American Airlines Flight 11, bound for Los Angeles. The flight was scheduled to depart at 7:45.

    In another Logan terminal, Shehhi, joined by Fayez Banihammad, Mohand al Shehri, Ahmed al Ghamdi, and Hamza al Ghamdi, checked in for United Airlines Flight 175, also bound for Los Angeles. A couple of Shehhi's colleagues

```

---


```
$ less technical/911report/chapter-1.txt technical/911report/preface.txt





"WE HAVE SOME PLANES"

    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.

    For those heading to an airport, weather conditions could not have been better for a safe and pleasant journey. Among the travelers were Mohamed Atta and Abdul Aziz al Omari, who arrived at the airport in Portland, Maine.

INSIDE THE FOUR FLIGHTS

Boarding the Flights

    Boston: American 11 and United 175. Atta and Omari boarded a 6:00 A.M. flight from Portland to Boston's Logan International Airport.

    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.

    Atta and Omari arrived in Boston at 6:45. Seven minutes later, Atta apparently took a call from Marwan al Shehhi, a longtime colleague who was at another terminal at Logan Airport. They spoke for three minutes.

    It would be their final conversation.

    Between 6:45 and 7:40, Atta and Omari, along with Satam al Suqami, Wail al Shehri, and Waleed al Shehri, checked in and boarded American Airlines Flight 11, bound for Los Angeles. The flight was scheduled to depart at 7:45.

    In another Logan terminal, Shehhi, joined by Fayez Banihammad, Mohand al Shehri, Ahmed al Ghamdi, and Hamza al Ghamdi, checked in for United Airlines Flight 175, also bound for Los Angeles. A couple of Shehhi's colleagues :n...skipping...



            PREFACE
            We present the narrative of this report and the recommendations that flow from it to
                the President of the United States, the United States Congress, and the American
                people for their consideration. Ten Commissioners-five Republicans and five
                Democrats chosen by elected leaders from our nation's capital at a time of great
                partisan division-have come together to present this report without dissent.
            We have come together with a unity of purpose because our nation demands it.
                September 11, 2001, was a day of unprecedented shock and suffering in the history of
                the United States. The nation was unprepared. How did this happen, and how can we
                avoid such tragedy again?
            To answer these questions, the Congress and the President created the National
                Commission on Terrorist Attacks Upon the United States (Public Law 107-306, November
                27, 2002).
            Our mandate was sweeping. The law directed us to investigate "facts and circumstances
                relating to the terrorist attacks of September 11, 2001," including those relating
                to intelligence agencies, law enforcement agencies, diplomacy, immigration issues
                and border control, the flow of assets to terrorist organizations, commercial
                aviation, the role of congressional oversight and resource allocation, and other
                areas determined relevant by the Commission. In pursuing our mandate, we have
                reviewed more than 2.5 million pages of documents and interviewed more than 1,200
                individuals in ten countries. This included nearly every senior official from the
                current and previous administrations who had responsibility for topics covered in
                our mandate. We have sought to be independent, impartial, thorough, and nonpartisan.
                From the outset, we have been committed to share as much of our investigation as we
                can with the American people. To that end, we held 19 days of hearings and took
                public testimony from 160 witnesses.
technical/911report/preface.txt (file 2 of 2)
```
