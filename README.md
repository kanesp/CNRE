# CNRE 91set 41
#include    <stdio.h>
void fun(int  a[], int  n)
{  int  i,t;
   for (i=0; i<strlen(a); i++)
   {
      t=a[i];
      a[i] = a[n-1-i];
      a[n-1-i]= t;
   }
}
void main()
{  int  b[9]={1,2,3,4,5,6,7,8,9}, i;
   printf("\nThe original data  :\n");
   for (i=0; i<9; i++)
      printf("%4d ", b[i]);
   printf("\n");
   fun(b, 9);
   printf("\nThe data after invert  :\n");
   for (i=0; i<9; i++)
      printf("%4d ", b[i]);
   printf("\n");
}
