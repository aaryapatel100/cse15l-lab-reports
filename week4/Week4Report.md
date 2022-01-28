# Code Change One
![Github Commit](./Fix1.png)
**Input File:** [Test 1](test2-file.md)
## Failing Output
![Incorrect Output](./test2FileError.png)
* The initial MarkdownParse program could not recognize the issue of an incorrect ordering of brackets/parenthesis within this test case. Due to this, the while loop in `getLinks()` became an infinite loop which caused an out of memmory error to arise.

# Code Change Two
![Github Commit](./Fix2.png)
**Input File:** [Test 2](test3-file.md)
## Failing Output
![Incorrect Output](./test3FileError.png)
* The program failed on this new test case due to its inability to filter out files with image extensions (.png in this particular test) within correct syntax for links. As a result, this particular test file would cause the program to return an incorrect ouput.

# Code Change Three
![Github Commit](./Fix3.png)
**Input File:** [Test 3](test4-file.md)
## Failing Output
![Incorrect Output](./test4FileError.png)
* The program failed on this test file as it was unable to filter out links missing parentheses and did not check next to the closing bracket for this case in particular (unable to check all required cases of correct link syntax). As a result, `getLinks()` returned an array that included incorrect results.