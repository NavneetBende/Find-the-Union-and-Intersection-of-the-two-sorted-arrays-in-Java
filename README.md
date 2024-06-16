Find the Union & Interaction of the two sorted arrays
Here, in this page we will discuss the program to find the union and interaction of two sorted arrays in Java . We are given with two sorted arrays and we have to find the union and interaction of the given two arrays

Find the Union & Interaction of the two sorted arrays
Algorithm to find Union :
Use two index variables i and j, initial values i = 0, j = 0
If arr1[i] is smaller than arr2[j] then print arr1[i] and increment i.
If arr1[i] is greater than arr2[j] then print arr2[j] and increment j. 
If both are same then print any of them and increment both i and j.
Print remaining elements of the larger array.
Algorithm to find Interaction :
Use two index variables i and j, initial values i = 0, j = 0.
If arr1[i] is smaller than arr2[j] then increment i.
If arr1[i] is greater than arr2[j] then increment j.
If both are same then print any of them and increment both i and j.
Java Code
Run

import java.util.*;
public
class Main {
    public
    static void Union(int[] arr1, int[] arr2) {
        int i = 0;
        int j = 0;

        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] < arr2[j]) {
                System.out.print(arr1[i] + " ");
                i++;
            } 
           else if (arr2[j] < arr1[i]) {
                System.out.print(arr2[j] + " ");
                j++;
            } else {
                System.out.print(arr1[i] + " ");

                i++;
                j++;
            }

        }
        while (i < arr1.length) {
            System.out.print(arr1[i] + " ");
            i++;
        }
        while (j < arr2.length) {
            System.out.print(arr2[j] + " ");
            j++;
        }
    }
    public
    static void Intersection(int[] arr1, int[] arr2) {
        int i = 0;
        int j = 0;
        while (i < arr1.length && j < arr2.length) {
            if (arr1[i] < arr2[j]) {
                i++;
            } else if (arr1[i] > arr2[j]) {
                j++;
            } else {
                System.out.print(arr1[i] + " ");
                i++;
                j++;
            }
        }
    }
    public
    static void main(String[] args) throws Exception {
        Scanner scn = new Scanner(System.in);
       
        int n1 = 3;
         System.out.println("The size of the array 1:- "+n1);
         int[] arr1 = new int[]{ 1,2,3}; 
        System.out.println("The Elements of array 1");
        for (int i = 0; i < n1; i++) {
            System.out.print(arr1[i] + " ");
        }
        System.out.println();

       
        int n2 = 4;
         System.out.println("The size of the array 2:- "+n2);

         int[] arr2 = new int[]{4,5,6,7}; 
        System.out.println("The Elements of array 2");
        

        for (int i = 0; i < n2; i++) {
            System.out.print(arr2[i] + " ");
        }
        System.out.println();
        System.out.println("The Union of the two array is ");
        Union(arr1, arr2);
        System.out.println();
        Intersection(arr1, arr2);
    }
}
Output:-
The size of the array 1:- 3
The Elements of array 1
1 2 3 
The size of the array 2:- 4
The Elements of array 2
4 5 6 7 
The Union of the two array is 
1 2 3 4 5 6 7 
