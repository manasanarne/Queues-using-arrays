# Queues-using-arrays
#include<stdio.h>
#include<stdlib.h>
#define MAX 20
int a[MAX],front=-1,rear=-1;
void enque(int x)
{
    if(rear==MAX-1)
    {
        printf("Queue is overflown");
    }
    else
    {
        if(front==-1)
        {
            front=rear=0;
        }
        else
        {
            ++rear;
        }
        a[rear]=x;
    }
}
int deque()
{
    int x;
    if(front==-1)
    {
        printf("Queue is underflown");
    }
    else
    {
        x=a[front];
        if(front==rear)
        {
            front=rear=-1;
        }
        else
        {
            ++front;
        }
        return x;
    }
}
void display()
{
    int i;
    if(front==-1)
    {
        printf("No element is in queue");
    }
    else
    {
        for(i=front;i<=rear;i++)
        {
            printf("%d\t",a[i]);
        }
    }
}
void main()
{
    int ch,x;
    while(1)
    {
        printf("\n1.Insert\n2.Delete\n3.Display\n4.Exit");
        printf("\nEnter your choice");
        scanf("%d",&ch);
        switch(ch)
        {
            case 1: printf("\nEnter the element to insert");
                    scanf("%d",&x);
                    enque(x);
                    break;
            case 2: x=deque();
                    if(x==-1)
                    {
                        printf("Queue is underflown");
                    }
                    else
                    {
                        printf("Queue element deleted %d",x);
                    }
                    break;
            case 3: printf("\nThe elements in queue are ");
                    display();
                    break;
            case 4: exit(0);
        }
    }
}

OUTPUT:

1.Insert
2.Delete
3.Display
4.Exit
Enter your choice1

Enter the element to insert5

1.Insert
2.Delete
3.Display
4.Exit
Enter your choice1

Enter the element to insert1

1.Insert
2.Delete
3.Display
4.Exit
Enter your choice1

Enter the element to insert9

1.Insert
2.Delete
3.Display
4.Exit
Enter your choice1

Enter the element to insert4

1.Insert
2.Delete
3.Display
4.Exit
Enter your choice3

The elements in queue are 5	1	9	4	
1.Insert
2.Delete
3.Display
4.Exit
Enter your choice2
Queue element deleted 5
1.Insert
2.Delete
3.Display
4.Exit
Enter your choice3

The elements in queue are 1	9	4	
1.Insert
2.Delete
3.Display
4.Exit
Enter your choice4
