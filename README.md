# postfix_evaluation
#include<stdio.h>
int stack[100],top=-1;
void push(int k)
{
        stack[++top]=k;
}
int pop()
{
        return stack[top--];
}
void main()
{
        char a[20],ch;
        int n1,n2,n3,n,i=0;
        printf("enter a:");
        scanf("%s",&a);
        while(a[i]!='\0')
        {
                if(isdigit(a[i]))
                {
                        n=a[i]-'0';
                        push(n);
                }
                else
                {
                        ch=a[i];
                        pop(n1);
                        pop(n2);
                        switch(ch)
                         {
                                case '+':
                                        n3=n2+n1;
                                        push(n3);
                                        break;
                                case '-':
                                        n3=n2-n1;
                                        push(n3);
                                        break;
                                case'*':
                                        n3=n2*n1;
                                        push(n3);
                                        break;
                                case '/':
                                        n3=n2/n1;
                                        push(n3);
                                        break;
                                case '^':
                                        n3=n2^n1;
                                        push(n3);
                                        break;
                        }
                }
                i++;
        }
        printf("%d",pop());
}

OUTPUT:
enter a: 245+*
18
