# Bouble sort
     Index:-     0     1     2    3    4      5     6    7 
     Ar:-       176  -272  -272  -45  269   -327  -945  176 
     
So here we are going to sort this array in Ascending order.

Below are the steps we need to follow to understand bouble sort.


## Step 1
So here we will start from index 0 and next index which is 1 [ 0, 1 ].

[![image](https://www.linkpicture.com/q/boubleSort.png)](https://www.linkpicture.com/view.php?img=LPic631b393013982334312092)

If we check in given array (176 > -272) so it is true.Here we need to swap the elements.
Array will looks like this:

     Index:-     0     1     2    3    4      5     6    7 
     Ar:-       -272  176  -272  -45  269   -327  -945  176 
     
## Step 2
Now the index will change [1,2] we will compare (1 ind > 2 ind) which is (176 > -272) that is true so again we will swap the elements.
Array will be:-  
  
     Index:-     0     1     2    3    4      5     6    7 
     Ar:-       -272  -272  176  -45  269   -327  -945  176   


## Step 3
Like that we will do till n-1 index.
And we will find the biggest element at the last position in array.
why n-1 index because we are working with i and i+1 so when i reaches it's length then i+1 will be greater 
then its length.we will get **ArrayIndexOutOfBoundException**. 

Final array for itration 1 will look like this:-

    Index:-     0     1     2    3    4      5     6    7 
    Ar:-       -272  -272  -45  176  -327  -945   176  269
    
    
 ## Step 4
 Now we will start again from inedx 1 and 2 [1,2].
 we will compare  <br>
 -272 > -45 false. <br>
 -45 > 176  false <br>
 176 > -327 true will swap the element. <br>
 
    Index:-     0     1     2    3    4     5     6    7 
    Ar:-       -272  -272  -45 -327  176  -945   176  269
   
 176 > -945 true will swap  <br>
 176 > 176 false no swap     <br>
 176 > 269 false no swap   <br>
 
 so with this our second largest element will come to its original place.
  
    Index:-     0     1     2    3    4     5     6    7 
    Ar:-       -272  -272  -45 -327 -945   176   176  269
    
 ## Step 5 
 Now we will start from 2 and 3 [2,3] and follow same step 3.
 by following these steps Array will be sorted.
 
 
 # Algorithm
 
 1. we will start from 0 index and compare to its next index.
 2. if our condition true then we will swap the Elements (j > j+1).
 3. we will repeat step 4 till n-1 (where n is length of array).

# Code

    
    import java.util.Arrays;

    public class BoubleSort {
        public static void sortingArray(){
	    	int[] ar = {176, -272, -272, -45, 269, -327, -945, 176};
	        int count = 0;
	        for(int ind = 0; ind<ar.length;ind++){
	            for(int j = 0; j<ar.length-1;j++){
	               if(ar[j] > ar[j+1]){
	                   int temp = ar[j];
	                   ar[j] = ar[j+1];
	                   ar[j+1] = temp;
	                   count++;   
	               }
	            }
	        }
	        System.out.println(count);
          System.out.println(Arrays.toString(ar));
	    }
    }
    
# Complexity:- O(n^2)

Worst case scenario array is in descending order.
Best case example array is in ascending order.
    
