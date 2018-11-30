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
#CNRE 43
#include <stdio.h>
#include <string.h>
#define   N   16
typedef  struct
{  char  num[10];
   int   s;
} STREC;
STREC  fun( STREC  *a, char *b )
{
	STREC c={"\0",-1};
int i;
for(i=0;i<N;i++)
if(strcmp(a[i].num,b)==0)
c=a[i];
return c;
}

void main()
{  STREC  s[N]={{"GA005",85},{"GA003",76},{"GA002",69},{"GA004",85},
		{"GA001",91},{"GA007",72},{"GA008",64},{"GA006",87},
		{"GA015",85},{"GA013",91},{"GA012",64},{"GA014",91},
		{"GA011",77},{"GA017",64},{"GA018",64},{"GA016",72}};
   STREC  h;
   char  m[10];
   int  i;FILE *out ;
   printf("The original data:\n");
   for(i=0; i<N; i++)
   {  if(i%4==0) printf("\n");
      printf("%s %3d  ",s[i].num,s[i].s);
   }
   printf("\n\nEnter the number:  ");gets(m);
   h=fun( s,m );
   printf("The data :  ");
   printf("\n%s  %4d\n",h.num,h.s);
   printf("\n");
   out = fopen("out.dat","w") ;
   h=fun(s,"GA013");
   fprintf(out,"%s  %4d\n",h.num,h.s);
   fclose(out);
}
