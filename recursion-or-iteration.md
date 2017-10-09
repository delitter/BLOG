# **Recursion Or Iteration?**
&nbsp;&nbsp;Actually during my past code study, I've been told that we should make our code as shorter as we can. Maybe shorter code can make us seem better at coding. However, when I read my textbook **_Data Structures and Algorithm Analysis in C_**, I found that in algorithm analysis part, the book mentioned that recursion can be some way bad used. 

&nbsp;&nbsp;We all know that recursion is a very strong way to solve some loop question. But there are some shortcomings. Just as the book says
> When recursion is properly used, it is difficult to convert the recursion into a simple loop
 structure 
    
&nbsp;&nbsp;Well we also know that calling a function can bemore complecated than doing a loop, in general. The stack things, and if there is any temporary variable, the function will take more memory. That is some thing we won't want it happen. So we know, if we can use a loop, even it will be a little bit complecated, we use it. Maybe comparing to recursion, loop, or iteration,  is more close to the way that machine thinks in.

&nbsp;&nbsp;And there is a situation that maybe corret to use reucursion: _tail recursion_. 

&nbsp;&nbsp;When we use recursion, we must take responsibility of the whole function. As a person to coding, I think our thinking should be more like machine but not human. So when we use recursion, we should not just use, we should do some algorithm design things and make the number of times of recursion smaller and smaller.

&nbsp;&nbsp;At last, let me put a example from the textbook. It's an example of good use of recursion. Algorithm for _finding the biggest subsequence sum problem_, the thinking is make a sequence half and half and compare left half to right half. Classic thinking of recursion and classic way to be solved by reursion.
***
    static int
    MaxSubSum(const int A[], int Left, int Right)`
    {
	    int MaxLeftSum, MaxRightSum;
	    int MaxLeftBorderSum, MaxRightBorderSum;
	    int LeftBorderSum, RightBorderSum;
	    int Center, i;

	    if(Left == Right) /*Base Case*/
		    if(A[Left] > 0)
			    return A[Left];
		    else
			    return 0;

	    Center = (Left + Right) / 2;
	    MaxLeftSum = MaxSubSum(A, Left, Center);
	    MaxRightSum = MaxSubSum(A, Center + 1, Right);
	
	    MaxLeftBorderSum = 0; LeftBorderSum = 0;
	    for(i = Center; i >= Left; i--)
	    {
		    LeftBorderSum += A[i];
		    if(LeftBorderSum > MaxLeftBorderSum)
			    MaxLeftBorderSum = LeftBorderSum;
	    }

	    MaxRigthBorderSum = 0; RightBorderSum = 0;
	    for(i = Center + 1; i <= Right; i++)
	    {
		    RightBorderSum += A[i];
		    if(RightBorderSum > MaxRightBorderSum)
			    MaxRightBorderSum = RightBorderSum;
	    }

	    return Max3(MaxLeftSum, MaxRightSum, 
		    MaxLeftBorderSum + MaxRightBorderSum);
    }
	
***
  