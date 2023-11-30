# C-Program-to-sort-First-half-in-Ascending-order-and-Second-Descending-order

Sort First half in Ascending and Second half in descending order in C
Here, in this page we will discuss the program to sort first half in ascending and second half in descending order in C programming language. We are given with an array and need to print the required sorted array in the desired way.

Sort First half in Ascending and Second half in descending order in C
Methods Discussed in this page :
Method 1 : Using bubble sort
Method 2 : Sort the entire array then, print first half in ascending and second half in descending.
Example :
Input : arr[6] = [1, 90, 34, 89, 7, 9]
Output : 1 7 9 90 89 34
Method 1 :
This program takes a lot of inspiration from the bubble sort.

Apart from the fact that we divide the array into two halves. In the first half we sort in ascending order and in the second we sort in descending order.

Sort first half in ascending and second half in descending
Code in C
Run
#include<stdio.h>

void ascDecFunc(int a[], int n)
{
    int temp;
    for(int i=0;i < n-1;i++)
    {
        for(int j = 0;j < n/2; j++) { if(a[j]>a[j+1])
            {
                temp=a[j];
                a[j]=a[j+1];
                a[j+1]=temp;
            }
        }
        
        for(int j = n/2;j < n-1; j++)
        {
            if(a[j] < a[j+1])
            {
                temp=a[j];
                a[j]=a[j+1];
                a[j+1]=temp;
            }
        }
    }
	
	for(int i = 0; i < n; i++)
	    printf("%d ", a[i]);
}
 
int main()
{
    int arr[] = {3, 2, 4, 1, 10, 30, 40, 20};
    int len = sizeof(arr) / sizeof(arr[0]);
    ascDecFunc(arr, len);
 
    return 0;
}
Output
1 2 3 4 40 30 20 10 
Related Pages
Calculate the sum of elements in an array

Reverse an Array

Sort the elements of an array

Finding the frequency of elements in an array

Sorting elements of an array by frequency

Method 2 :
Sort the given array.
Run a loop up to half the length of the array and print the elements of the sorted array.
Run a loop from the last index of the array to the middle of the array and print the elements in reverse order.
Code in C
Run
#include<stdio.h>

void ascDecFunc(int a[], int n)
{
  int temp;
  for(int i=0;i < n-1;i++){
      for(int j = i+1;j < n; j++) { if(a[i]>a[j]){
            temp=a[i];
            a[i]=a[j];
            a[j]=temp;
         }
      }
   }
   // printing first half in ascending order
  for (int i = 0; i < n / 2; i++) 
         printf("%d ", a[i]); 
// printing second half in descending order 
   for (int j = n - 1; j >= n / 2; j--)
      printf("%d ", a[j]);

}

int main()
{
   int arr[] = {3, 2, 4, 1, 10, 30, 40, 20};
   int len = sizeof(arr) / sizeof(arr[0]);
   ascDecFunc(arr, len);

   return 0;
}
Output
1 2 3 4 40 30 20 10 
