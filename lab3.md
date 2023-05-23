# Lab Report 3
### Long Tran

I chose `grep` for my specific command. I asked ChatGPT for 4 ways to use `grep` and I will demonstrate them with 2 example each on technical.

**Usage 1: `grep` with color**

The ``--color`` option highlight the query word in the line, which is very useful for long lines (eg paragraphs in txt files).

**Example 1** This should highlight the word "Bush" and make finding it easier.
Code:
```
grep --color "Bush" ./911report/*.txt
```

Output (truncated):
```
./911report/chapter-1.txt:    Tuesday, September 11, 2001, dawned temperate and nearly cloudless in the eastern United States. Millions of men and women readied themselves for work. Some made their way to the Twin Towers, the signature structures of the World Trade Center complex in New York City. Others went to Arlington, Virginia, to the Pentagon. Across the Potomac River, the United States Congress was back in session. At the other end of Pennsylvania Avenue, people began to line up for a White House tour. In Sarasota, Florida, President George W. Bush went for an early morning run.
./911report/chapter-1.txt:    In Sarasota, Florida, the presidential motorcade was arriving at the Emma E. Booker Elementary School, where President Bush was to read to a class and talk about education. White House Chief of Staff Andrew Card told us he was standing with the President outside the classroom when Senior Advisor to the President Karl Rove first informed them that a small, twin-engine plane had crashed into the World Trade Center. The President's reaction was that the incident must have been caused by pilot error.
...
```

**Example 2:** This should highlight the word "San Diego" and make finding it easier.

Code:
```
grep --color "San Diego" ./government/Media/*.txt
```

Output:
```
./government/Media/Bridging_legal_aid_gap.txt:The San Diego Union-Tribune
./government/Media/Free_Legal_Assistance.txt:operating in Sacramento, San Diego and Ventura.
```

**Usage 2: Using recursive `grep`**

This will be useful to look for stuff in the ``technical`` folder without keying in to one txt pattern.


**Example 1:** This should find all the files that contain the word "San Diego" in the ``government`` folder.

Code:
```
grep -r "San Diego" ./government
```

Output:
```
./government/About_LSC/Comments_on_semiannual.txt:San Diego, LSC and the Project for the Future of Equal Justice held
./government/About_LSC/State_Planning_Report.txt:Aid Society of San Diego and Inland Counties Legal Services, were
./government/About_LSC/State_Planning_Report.txt:other statewide initiatives. For example, Inland and San Diego have
./government/Gen_Account_Office/pe1019.txt:low-problem centers. We could do this by selecting 1 (San Diego, 4
./government/Gen_Account_Office/pe1019.txt:Here we might select numbers 1 (San Diego, 800 beds), 6
./government/Gen_Account_Office/pe1019.txt:San Diego site, or allegations might be made that the high costs of
./government/Media/Free_Legal_Assistance.txt:operating in Sacramento, San Diego and Ventura.
./government/Media/Bridging_legal_aid_gap.txt:The San Diego Union-Tribune
```

**Example 2:** This should find all the files that contain the word "Computer" in the ``911report`` folder.

Code:
```
grep -r "Computer" ./911report
```

Output:
```
./911report/chapter-13.3.txt:                CAPPS, also known as CAPS (Computer Assisted Profiling System), see FAA security
./911report/chapter-3.txt:                FAA-approved computerized algorithm (known as CAPPS, for Computer Assisted Passenger
./911report/chapter-1.txt:    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.
```

**Usage 3: Case-insensitive search**

This will be useful to look for common words, since they may be used at the beginning of the sentence.

**Example 1:** ``mathematic`` is a common word, so we should use case-insensitive search to find it.

Code
```
grep -i -r "mathematic" ./government
```

Output:
```
./government/Env_Prot_Agen/ctf7-10.txt:derived from a mathematical model that assumes a continuous
./government/Env_Prot_Agen/ctm4-10.txt:derived from a mathematical model that assumes a continuous
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt:used to analyze economic data through mathematical and statistical
./government/Gen_Account_Office/im814.txt:Software metrics, which use mathematical models to measure
```

**Example 2:** ``Computer`` is a common word, so we should use case-insensitive search to find it.

Code:
```
grep -i -r "Computer" ./911report
```

Output:
```

./911report/chapter-13.4.txt:            3. President Clinton spoke of the Y2K computer problem in his January 19, 1999, State
./911report/chapter-13.4.txt:                computer programmer in Arizona before resuming flight training during the summer of
./911report/chapter-13.5.txt:            51. FDNY interview 60, HQ (May 11, 2004); see FDNY record, computer-aided dispatch
./911report/chapter-13.5.txt:            101. FDNY records, computer-aided dispatch report, alarm box 8087, Sept. 11, 2001,
./911report/chapter-13.5.txt:            102. For the 23 engines and 13 ladders dispatched, see FDNY records, computer-aided
./911report/chapter-13.5.txt:                10, Jan. 10, 2001. For the delayed dispatch, see FDNY records, computer-aided
./911report/chapter-13.5.txt:                units, see FDNY records, computer-aided dispatch report, alarm box 1377, Sept.
./911report/chapter-13.5.txt:            136. For the fifth alarm, see FDNY records, computer-aided dispatch report, alarm box
./911report/chapter-13.3.txt:                CAPPS, also known as CAPS (Computer Assisted Profiling System), see FAA security
./911report/chapter-13.3.txt:                1997. Under the previous noncomputerized profiling system, selectees were subject to
./911report/chapter-3.txt:                FAA-approved computerized algorithm (known as CAPPS, for Computer Assisted Passenger
./911report/chapter-3.txt:                system was computerized in 1997.55 This policy change also reflected the perception
./911report/chapter-3.txt:                computer-to-computer communications and modern communication systems, while
./911report/chapter-3.txt:                computer networks. . . . Third, we will undertake a concerted effort to prevent the
./911report/chapter-3.txt:                tactics-a chemical, biological, nuclear, or computer threat-not terrorist
./911report/chapter-3.txt:                computer operations and weapons procurement, was arrested in Germany. He was the
./911report/chapter-2.txt:                Center. The casing team also included a computer expert whose write-ups were
./911report/chapter-2.txt:                diagrams prepared by the team's computer specialist. He, his top military committee
./911report/chapter-1.txt:    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.
./911report/chapter-5.txt:                al Adl, by assisting them with computer and media projects.
./911report/chapter-5.txt:                other al Qaeda members with their outdated computer equipment. Bin Ladin, apparently
./911report/chapter-5.txt:                the training involved using flight simulator computer games, viewing movies that
./911report/chapter-5.txt:                    violence. Atta and Binalshibh used Bahaji's computer for Internet research, as
./911report/chapter-6.txt:                but about computer breakdowns-the Y2K scare. Some government officials were
./911report/chapter-7.txt:                pages to his computer's hard drive.
./911report/chapter-7.txt:                and attended services at the Islamic Center. He borrowed his housemate's computer
./911report/chapter-9.txt:                sophisticated computerized fire alarm system with redundant electronics and control
./911report/chapter-9.txt:                he initially gave announcements to those floors that had generated computerized
./911report/chapter-9.txt:                complex controlled by the buildings' computerized security system, including doors
./911report/chapter-8.txt:                search Moussaoui's laptop computer.
./911report/chapter-8.txt:                search Moussaoui's computer hard drive and belongings. Either the British
./911report/chapter-12.txt:                have been introduced into an antiquated computer environment. Replacement of these
./911report/chapter-12.txt:            On 9/11, the 19 hijackers were screened by a computer-assisted screening system
./911report/chapter-11.txt:                millennium and possible computer programming glitches ("Y2K") that might obliterate
```

We see a lot more matches for "Computer".

**Usage 4: Displaying line number**

This will be very convenient as a reference system for future usage.

**Example 1:** This should display the line number of the word "San Diego" in the ``government`` folder.

Code
```
grep -i -r -n "San Diego" ./government
```

Output:
```
./government/About_LSC/Comments_on_semiannual.txt:198:San Diego, LSC and the Project for the Future of Equal Justice held
./government/About_LSC/State_Planning_Report.txt:331:Aid Society of San Diego and Inland Counties Legal Services, were
./government/About_LSC/State_Planning_Report.txt:340:other statewide initiatives. For example, Inland and San Diego have
./government/Gen_Account_Office/pe1019.txt:724:low-problem centers. We could do this by selecting 1 (San Diego, 4
./government/Gen_Account_Office/pe1019.txt:749:Here we might select numbers 1 (San Diego, 800 beds), 6
./government/Gen_Account_Office/pe1019.txt:773:San Diego site, or allegations might be made that the high costs of
./government/Media/Free_Legal_Assistance.txt:28:operating in Sacramento, San Diego and Ventura.
./government/Media/Bridging_legal_aid_gap.txt:5:The San Diego Union-Tribune
```

**Example 2:** This should display the line number of the word "University of California" in the ``government`` folder.

Code:
```
grep -i -r -n "University of California" ./government
```

Output:

```
./government/Gen_Account_Office/pe1019.txt:3419:University of California, Center for the Study of Evaluation,
./government/Gen_Account_Office/pe1019.txt:3470:Los Angeles: University of California, Center for the Study of
./government/Gen_Account_Office/pe1019.txt:3537:Los Angeles: University of California,
./government/Gen_Account_Office/pe1019.txt:3642:Berkeley, Calif.: University of California Press, 1973.*
./government/Media/Kiosks_for_court_forms.txt:19:A University of California, Irvine, study released Wednesday
```