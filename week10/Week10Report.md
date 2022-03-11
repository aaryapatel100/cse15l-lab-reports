## Finding Different Results
I found the test cases with different results by using the `diff` command to compare the results.txt file from my repository and Joe's repository. The results.txt files were created by running the command `bash script.sh > results.txt` in both of the cloned repositories.

## Test Case 1 (500.md)
```
[link](#fragment)

[link](http://example.com#fragment)

[link](http://example.com?foo=3#frag)
```
Joe's Output: [#fragment, http://example.com#fragment,http://example.com?foo=3#frag]

My Output: [http://example.com#fragment, http://example.com?foo=3#frag]

Correct: Joe's implementation was correct here as it contains all three links, while mine is missing #fragment.

```
if (!checkExtension(markdown.substring(openParen +1, closeParen)) && openParen-nextCloseBracket==1)
{
    if(markdown.substring(openParen + 1, closeParen).indexOf(".")!=-1)
        toReturn.add(markdown.substring(openParen + 1, closeParen));
}
```
The bug for this test case lies in this portion of the code as the if statement checks for a '.' in orer for something to count as a link (causing #fragment to fail). 

## Test Case 2 (194.md)
```
[foo]: <bar>(baz)

[foo]
```
Joe's Output: [baz]

My Output: [ ]

Correct: My implementation is correct here as there are no links and so the outcome should be [ ].

```
if(nextOpenBracket == -1 || nextCloseBracket == -1
      || closeParen == -1 || openParen == -1) {
    return toReturn;
}
String potentialLink = markdown.substring(openParen + 1, closeParen).trim();
if(potentialLink.indexOf(" ") == -1 && potentialLink.indexOf("\n") == -1) {
    toReturn.add(potentialLink);
    currentIndex = closeParen + 1;
}
```

The bug within this code is that it doesn't do any sort of check for characters between the close bracket and the set of parentheses, thus counting `baz` as a link. The .trim() added to potentialLink allows it to pass the second check of whitespace and be returned from getLinks().