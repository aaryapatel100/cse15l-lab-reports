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

## Test Case 2 (194.md)
```
[foo]: <bar>(baz)

[foo]
```
Joe's Output: [baz]

My Output: [ ]

Correct: My implementation is correct here as there are no links and so the outcome should be [ ].

