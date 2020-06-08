# codechef May -2020 long challenge 
Longest Palindrome 
#include <stdio.h>

int main(void) 
{
    int n,i,j,k,l,yn;
    int length=0,left,right;
    char word[5000];
    scanf("%d\n",&n);
    for(i=0;i<n;i++) 
    {
        scanf("%c",&word[i]);
    }
    for(i=0;i<n;i++)
    {
        for(j=n-1;j>=i+length;j--)
        {
            yn=1;
            if(word[i]==word[j])
            {
                yn=2;
                for(k=0;k<j-i;k++)
                {
                    if(word[k+i]!=word[j-k])
                    {
                        yn=0;
                        break;
                    }
                }
            }
            if(yn==2)
            {
                length=j-i+1;
                left=i;
                right=j;
            }
        }
    }
    printf("%d\n",length);
    for(i=left;i<=right;i++)
        printf("%c",word[i]);
	return 0;
}
