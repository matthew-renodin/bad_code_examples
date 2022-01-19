# code_examples

This was an interview question which I found odd. Most of them are memorization problems but we can use them for thinking and developing some analytical skills.


## staircase 19 steps

1-2-3 steps at a time given a number of steps in a staircase.

I designed two iterative functions I came up with by looking at a spreadsheet.

![image](https://user-images.githubusercontent.com/5507643/150047645-9c4ca817-61a1-4fe2-beb4-f16dc0cd8d11.png)

I made the spreadhseet to help me look for patterns. 

My spreadsheet analysis showed me two iterative methods I could use. 

I coded them up in JavaScript. This is a screenshot from the browser.

![image](https://user-images.githubusercontent.com/5507643/150048754-db690a6a-f633-4333-9b3b-ed93cabae417.png)

Both functions require you start it out with some initial data.

The b variables is what is different between them. In one case, mr_stairs1, I ended up adding the prior 3 indexes of b. In the second case, I sum the prior value in index of a,b, and c array. 

```javascript

function mr_stairs1(n)
{
let a = [];
let b = [];
let c = [];

a[0]=1;
a[1]=1;
a[2]=1;
a[3]=1;


b[0]=0;
b[1]=1;
b[2]=2;
b[3]=4;

c[0]=0;
c[1]=0;
c[2]=1;

let i = 0;

for(i = 4; i <= n; i++){
   a[i] = 1;
   b[i] = (b[i-3] + b[i-2] + b[i-1]);
   c[i] = (b[i-2] + b[i-1])-1;
}
return (a[n-1]+ b[n-1] + c[n-1]);
}

function mr_stairs2(n)
{
let a = [];
let b = [];
let c = [];

a[0] = 1;
a[1] = 1;
a[2] = 1;


b[0] = 0;
b[1] = 1;
b[2] = 2;

c[0] = 0;
c[1] = 0;
c[2] = 1;

let i=0;

for(i = 3; i <= n; i++){
   a[i] = 1;
   b[i] = (a[i-1] + b[i-1] + c[i-1]);
   c[i] = (b[i-2] + b[i-1])-1;
}

return (a[n-1]+ b[n-1] + c[n-1]);
}
```
