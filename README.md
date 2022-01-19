# code_examples

This was a interview question which I found odd. Most of them are memorization problems but we can use them for thinking and developing some analytical skills.


## staircase 19 steps

1-2-3 steps at a time given a number of steps in a staircase

I designed a iterative function I came up with by looking at a spreadsheet.

![image](https://user-images.githubusercontent.com/5507643/150047645-9c4ca817-61a1-4fe2-beb4-f16dc0cd8d11.png)

I made the spreadhseet to help me look for patterns. 

My spreadsheet analysis showed me two iterative methods I could use. 

I coded them up in JavaScript. This is a screenshot from the browser.

![image](https://user-images.githubusercontent.com/5507643/150047959-21266906-9472-4814-acb6-c3e474ef424a.png)


Both functions require you start it out with some initial data.

The b variables is what is different between them. In one case, mr_stairs1, I ended up adding the prior 3 indexes of b. In the second case, I sum the prior value in index of a,b, and c array. 
