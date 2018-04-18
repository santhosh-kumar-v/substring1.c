# substring1.c
#include<stdio.h>
#include<string.h>
int main()
{
    char str[100];
    int l;
    scanf("%s",str);
    l=strlen(str);
    longuniquesubs(str,l);
}
int longuniquesubs(char str[],int l)
{
    int i,j,k=1;
    char b[100]="",c[100]="";
    for(i=0;i<l;i++)
    {
        b[0]=str[i];
        for(j=i+1;j<l;j++)
        {
            if(str[j]>str[i])
            {
               b[k++]=str[j]; 
            }
            else
            {
                break;
            }
        }
        if(strlen(b)>strlen(c))
        {
            strcpy(c,b);
            strcpy(b,"");
        }
        k=1;
    }
    printf("%s",c);
}
