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

<img width="377" alt="Screen Shot 2023-11-03 at 3 37 59 PM" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/d43f5271-5070-4832-a039-83b0d0641cab">


`After`

<img width="379" alt="Screen Shot 2023-11-03 at 3 38 31 PM" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/8520eb28-5902-45f9-9ec8-51af60c33ed1">


This addresses the issue because the test case `testReverse2` expected value for it to pass can only be {0,0,0,0} and no positive values. This is because the newArray object that was created sets every index value to 0 and setting arr[i] = to newArray times anything will set the indexes of arr[i] to 0. Therefore, setting newArray[i] = arr[arr.length - i - 1] will also set up a new array and reverse the order of the original array with no errors.

### Part 2: Researching Commands

### Find Command

## `-depth option`

<img width="555" alt="Screen Shot 2023-11-04 at 6 57 30 PM" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/4859ee20-129b-44c1-8b6c-b1a915468ca7">

The depth option performs a depth-first search while traversing the directory and lists the files in depth-first search order. The depth option is useful in `find ./technical/government/Env_Prot_Agen` because it ensured the deepest files were processed first, which is beneficial for specific order of directory processing.

<img width="540" alt="depth option" src="https://github.com/shinaegyo/lab-report-3/assets/137027086/b874d931-25e9-4f67-941a-78cbabcff123">

The depth option performs a depth-first search while traversing the directory and lists the files in depth-first search order. The depth option is useful in `find ./technical/government/About_LSC` because it ensured the deepest files were processed first, which is beneficial for specific order of directory processing.


## `-name option`

<img width="532" alt="Screen Shot 2023-11-04 at 6 20 17 PM" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/d4f24ca5-2cdf-4552-a381-e7467ef151ce">

The name option is used to search for files or directories based on their names. In `find ./technical/government - name "Session*"`, it listed all the files with name "Session" and it is useful for locating files based on their names.

<img width="636" alt="Screen Shot 2023-11-04 at 6 20 09 PM" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/35317d75-900d-46a0-b314-526e89b8fa83">

The name option is used to search for files or directories based on their names. In `find ./technical/government/Alcohol_Problems - name "Session*"`, it resulted in the same output as the one above with a different path and it is useful because it listed out all the files with the name "Session" for locating the files.

## `-type option`

<img width="470" alt="-type f" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/acf133c0-6185-4ded-9ac6-840ffccb05af">

The type option is used to specify the type of file to search for such as -type f for searching for regular files and -type d for directories. `In find ./technical/911report -type f`, it displayed all the regular files within this directory which helped to narrow down the specific file type.

<img width="473" alt="-type d" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/6dbf53d4-9ac1-4d0e-909f-cf19213af80b">

The type option is used to specify the type of file to search for such as -type f for searching for regular files and -type d for directories. `In find ./technical/911report -type d`, it displayed the directory which helped to see the current directory.

## `-s option`

<img width="545" alt="-s option Env_Prot_Agen" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/0b64315b-bc01-4114-8e74-57fd2eddb164">

The `-s option` traverses the file hierarchies in alphabetical order within each directory. In `find -s ./technical/government/Env_Prot_Agen`, it lists all the files inside the directory in alphabetical order which helps to organize and easily find files.

<img width="533" alt="-s option post_rate_comm" src="https://github.com/shinaegyo/cse15l-lab3/assets/137027086/19ced74c-71ae-4185-8c68-3d7ed21bf8e8">

The `-s option` traverses the file hierarchies in alphabetical order within each directory. In `find -s ./technical/government/Post_Rate_Comm`, it lists all the files inside the directory in alphabetical order which helps to organize and easily find files.


## Works Cited
https://www.unix.com/unix-for-beginners-questions-and-answers/276933-find-depth-how-use.html

https://www.tecmint.com/35-practical-examples-of-linux-find-command/

https://snapshooter.com/learn/linux/find
