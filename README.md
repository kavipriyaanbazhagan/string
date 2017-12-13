# string
/*
Author: KAVI
Date: 13.12.17

Handles string manipulation - 4 operations

*/#include<stdio.h>
#include<string.h>
#include<conio.h>
char str[100]; 		//declaration of global variable
/*********************************************

Var: void
Return type: void

Find frequency of character
*******************************************////
void frequency()	
{
char ch;
int i,frequency=0;
printf("\n Enter a character\t");
scanf(" %c",&ch);
for(i=1;str[i]!='\0';i++)
{
	if(ch==str[i])
		++frequency;
}
printf("\n The frequency of %c=%d",ch,frequency);
}
/*********************************************

Var: void
Return type: void

To check the palindrome for the given string

*******************************************////
void palindrome()      // function to check for palindrome
{
char cpy[100];
strcpy(cpy,str);
strrev(str);
if(strcmp(str,cpy)==0)
{
	printf("\n The given string is a palindrome");
}
else
{
	printf("\n The given string is not a palindrome");
}
}
/*********************************************

Var: void
Return type: void

Arrange the string in alphabetical order

*******************************************////
void arrange()
{
char ch1,output[100];
int no[26]={0},n,c,t,x;
n=strlen(str);
for(c=0;c<n;c++)
{
	ch1=str[c]-'a';
	no[ch1]++;
}
t=0;
for(ch1='a';ch1<='z';ch1++)
{
 x=ch1-'a';
  for(c=0;c<no[x];c++)
   {
    output[t]=ch1;
    t++;
   }
}
  output[t]='\0';
  printf("\n The arrangement of string in alphabetical order is %s",output);
}
/*********************************************

Var: void
Return type: void

reversing a string using recursion

*******************************************////
void reverse(char *str1)		
{
   if(*str1)
    {
     reverse(str1+1);
    }
    printf(" %c",*str1);
}
/****************************************
Calling of the function
*********************************//////
void main()
{
int choice;
clrscr();
printf("\n Enter the string");
scanf("%s",str);
	printf("\n The choices are \n1.frequency");
	printf("\n2.Palindrome");
	printf("\n3.Arrange the string in alphabetical order");
	printf("\n4.Reverse using recursion");
printf("\n Enter the choice");
scanf("%d",&choice);
switch(choice)
  {
	case 1: printf("\n 1.Frequency");
		frequency();
		break;
	case 2: printf("\n 2.Palindrome");
		palindrome();
		break;
	case 3: printf("\n 3. Arrangement");
		arrange();
		break;
	case 4: printf("\n 4.Reverse");
		printf("\n the reversed string is");
		reverse(str);
		break;
	default: printf("\n Wrong choice");
  }
getch();
}
