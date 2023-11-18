### Bugs and Commands

### Part 1: Bugs

```
// Failure Inducing Input for Buggy Program

  @Test
  public void testReverse2() {
    int[] input1 = {0,0,0,0};
    int[] output1 = ArrayExamples.reversed(input1);
    assertArrayEquals(new int[] {0,0,0,0}, output1);
  }

```
```
// Input that Doesn't Induce a Failure

  @Test
  public void testReverse3() {
    int[] input1 = {4,5,6,7};
    int[] output1 = ArrayExamples.reversed(input1);
    assertArrayEquals(new int[] {7,6,5,4}, output1);
  }
```

`Symptom of Output of Running the Test`

<img width="664" alt="Screen Shot 2023-11-03 at 3 43 50 PM" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/f66513e7-4281-415b-8690-cc79308c7092">


`Before`

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```


`After`

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```


This addresses the issue because the test case `testReverse2` expected value for it to pass can only be {0,0,0,0} and no positive values. This is because the newArray object that was created sets every index value to 0 and setting arr[i] = to newArray times anything will set the indexes of arr[i] to 0. Therefore, setting newArray[i] = arr[arr.length - i - 1] will also set up a new array and reverse the order of the original array with no errors.

### Part 2: Researching Commands

### Find Command

## `-depth option`

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find ./technical/government/Env_Prot_Agen -depth
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/section-by-section_summary.txt
./technical/government/Env_Prot_Agen/jeffordslieberm.txt
./technical/government/Env_Prot_Agen/final.txt
./technical/government/Env_Prot_Agen/ctf7-10.txt
./technical/government/Env_Prot_Agen/ctf1-6.txt
./technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/1-3_meth_901.txt
./technical/government/Env_Prot_Agen/atx1-6.txt
./technical/government/Env_Prot_Agen/tech_sectiong.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/nov1.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Env_Prot_Agen
```

The depth option performs a depth-first search while traversing the directory and lists the files in depth-first search order. The depth option is useful in `find ./technical/government/Env_Prot_Agen` because it ensured the deepest files were processed first, which is beneficial for specific order of directory processing.

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find ./technical/government/About_LSC -depth 
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/About_LSC/Progress_report.txt
./technical/government/About_LSC/Strategic_report.txt
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/Special_report_to_congress.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
./technical/government/About_LSC/diversity_priorities.txt
./technical/government/About_LSC/reporting_system.txt
./technical/government/About_LSC/State_Planning_Report.txt
./technical/government/About_LSC/Protocol_Regarding_Access.txt
./technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
./technical/government/About_LSC/conference_highlights.txt
./technical/government/About_LSC/State_Planning_Special_Report.txt
./technical/government/About_LSC
```


The depth option performs a depth-first search while traversing the directory and lists the files in depth-first search order. The depth option is useful in `find ./technical/government/About_LSC` because it ensured the deepest files were processed first, which is beneficial for specific order of directory processing.


## `-name option`

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find ./technical/government -name "Session*"
./technical/government/Alcohol_Problems/Session2-PDF.txt
./technical/government/Alcohol_Problems/Session3-PDF.txt
./technical/government/Alcohol_Problems/Session4-PDF.txt
```

The name option is used to search for files or directories based on their names. In `find ./technical/government - name "Session*"`, it listed all the files with name "Session" and it is useful for locating files based on their names.

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find ./technical/government/Alcohol_Problems -name "Session*"
./technical/government/Alcohol_Problems/Session2-PDF.txt
./technical/government/Alcohol_Problems/Session3-PDF.txt
./technical/government/Alcohol_Problems/Session4-PDF.txt
```

The name option is used to search for files or directories based on their names. In `find ./technical/government/Alcohol_Problems - name "Session*"`, it resulted in the same output as the one above with a different path and it is useful because it listed out all the files with the name "Session" for locating the files.

## `-type option`

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find ./technical/911report -type f 
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```

The type option is used to specify the type of file to search for such as -type f for searching for regular files and -type d for directories. `In find ./technical/911report -type f`, it displayed all the regular files within this directory which helped to narrow down the specific file type.

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find ./technical/911report -type d
./technical/911report
```

The type option is used to specify the type of file to search for such as -type f for searching for regular files and -type d for directories. `In find ./technical/911report -type d`, it displayed the directory which helped to see the current directory.

## `-s option`

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find -s ./technical/government/Env_Prot_Agen 
./technical/government/Env_Prot_Agen
./technical/government/Env_Prot_Agen/1-3_meth_901.txt
./technical/government/Env_Prot_Agen/atx1-6.txt
./technical/government/Env_Prot_Agen/bill.txt
./technical/government/Env_Prot_Agen/ctf1-6.txt
./technical/government/Env_Prot_Agen/ctf7-10.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/final.txt
./technical/government/Env_Prot_Agen/jeffordslieberm.txt
./technical/government/Env_Prot_Agen/multi102902.txt
./technical/government/Env_Prot_Agen/nov1.txt
./technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
./technical/government/Env_Prot_Agen/section-by-section_summary.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Env_Prot_Agen/tech_sectiong.txt
```

The `-s option` traverses the file hierarchies in alphabetical order within each directory. In `find -s ./technical/government/Env_Prot_Agen`, it lists all the files inside the directory in alphabetical order which helps to organize and easily find files.

```
jamesshin@Jamess-MacBook-Pro docsearch-main % find -s ./technical/government/Post_Rate_Comm 
./technical/government/Post_Rate_Comm
./technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
./technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
./technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
./technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
./technical/government/Post_Rate_Comm/Cohenetal_Scale.txt
./technical/government/Post_Rate_Comm/Cohenetal_comparison.txt
./technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt
./technical/government/Post_Rate_Comm/Gleiman_gca2000.txt
./technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
./technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt
./technical/government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
./technical/government/Post_Rate_Comm/Redacted_Study.txt
./technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt
./technical/government/Post_Rate_Comm/WolakSpeech_usps.txt
```

The `-s option` traverses the file hierarchies in alphabetical order within each directory. In `find -s ./technical/government/Post_Rate_Comm`, it lists all the files inside the directory in alphabetical order which helps to organize and easily find files.


## Works Cited

[find -depth  ..How to use it ? (n.d.). The UNIX and Linux Forums.](https://www.unix.com/unix-for-beginners-questions-and-answers/276933-find-depth-how-use.html)

(-depth option utilized this source)

[Saive, R., & Saive, R. (2023, July 18). 35 Practical examples of Linux Find Command. 35 Practical Examples of Linux Find Command.](https://www.tecmint.com/35-practical-examples-of-linux-find-command/)

(-name option utilized this source)

[Ultimate guide to Linux find command - SnapShooter Tutorials. (n.d.).](https://snapshooter.com/learn/linux/find)

(-type option utilized this source)

[Sort files in Terminal like finder. (n.d.). Ask Different.](https://apple.stackexchange.com/questions/266645/sort-files-in-terminal-like-finder)

(-s option utilized this source)
