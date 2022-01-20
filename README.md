# staircase problem introduction

In a staircase problem, you try to calculate the different ways to reach the n'th stair where you are allowed to take up to m steps at a time.

This is often used as an interview question. Most of these questions are memorization problems so they are well suited for new hires. For people who have been working for sometime, these questions are not that good because they really do not show the skills a person has during an interview, but we can revist these problems and use them for thinking and developing our analytical skills. 

In practical terms we use this to generate a collection of all possible ways to achieve a outcome given some fixed unit of measure. If we had 4 as a staircase (n) and this represented the outcome and we had three steps of 1,2, or 3, we would have these seven ways to get there {1,1,1,1},{1,1,2},{1,2,1},{2,1,1},{2,2},{1,3},{3,1}. This idea of sets is where the concept of permutations comes in because this is looking at combinations where order is distinct in each set. The text I have read refer to this also as ordered arrangements of n elements, such as 19 elements, of a set S such as {1,2,3}, where repetition is allowed, and are called n-tuples. In this case there is a rule that states that 19 is the limit of elements and the maxiumum sum of the elements. Generally speaking this may be more applicable to combinatorics.  

## staircase 19 steps

1-2-3 steps at a time given a number of steps in a staircase.

I designed two iterative functions I came up with by looking at a spreadsheet.

![image](https://user-images.githubusercontent.com/5507643/150052884-efb64829-c750-48ca-80d1-b21069102467.png)


I made the spreadhseet to help me look for patterns. 

My spreadsheet analysis showed me two iterative methods I could use. 

I coded them up in JavaScript. This is a screenshot from the browser.

![image](https://user-images.githubusercontent.com/5507643/150048754-db690a6a-f633-4333-9b3b-ed93cabae417.png)

Both functions require you start it out with some initial data.

The b variables is what is different between them. In one case, mr_stairs1, I ended up adding the prior 3 indexes of b. In the second case, I sum the prior value in index of a,b, and c array. From what I have have found as of today, mr_stairs2 is the more common iterative version, they usually only do a 1-2 step though. These both do a 1-2-3 mix, but mr_stairs1 is quite different for summing the prior three indexes of the b array. The c array I used two methods, one method sums the prior to indexes and adds two to the value, I think this is the more common. The other method uses the prior two indexes of the b-array and subtracts one. I think this is different than other approaches I have seen because I have not seen anyone do this. 

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
   c[3]=2;

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
