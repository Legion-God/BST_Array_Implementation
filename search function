#include <stdio.h>
#include <stdlib.h>
int lastIndex;
void insert(int val,int tree[],int t)
{

   /*while(1)        //Non Recursive version
   {
       if(tree[t]==0)
        {
            tree[t]=val;   //If node is empty then insert element and after insertion break out loop to main()
            break;
        }
        else if(tree[t]>val)
            t=(t*2);       //points to left child
        else if(tree[t]<val)
            t=(t*2)+1;     //Points to right child

   }
   */

                      //Recursive Version

                      if(tree[t]==0)                           //If child is empty then ,insert the val
                          tree[t]=val;

                    else if(val>tree[t])                        //If child is NOT empty then checks the position to insert val
                            insert(val,tree,t=(t*2)+1);      //Points to right child
                    else if(tree[t]>val)
                            insert(val,tree,t=(t*2));          //points to left child

}

void search(int tree[],int t,int key)    //Finds passed Key element in tree[]
{                                       //Returns 1 if the value is found else returns 0
int flag=0;
  while(flag!=1 && t<=lastIndex)    //If element is found loop breaks or if t goes over bound then the loop breaks
        {
            if(tree[t]==key)
            {
                printf("Element Found.\n");
                flag=1;

            }
            else
            {
                if(key>tree[t])
                {
                    t=(t*2)+1;
                }
                else if(key<tree[t])
                {
                    t=t*2;
                }
            }

        }
       if(flag==0)
            printf("Element Not Found.\n");


}

void preorder(int tree[],int t)
{

    if(tree[t]!=0)
    {
        printf("%d(%d)\t",tree[t],t);

        preorder(tree,t*2);     //Recurse Left tree
        preorder(tree,(t*2)+1);  //Recurse Right tree
    }

}

void inorder(int tree[],int t)
{
    if(tree[t]!=0)
    {
        inorder(tree,t*2);
          printf("%d(%d)\t",tree[t],t);
         inorder(tree,(t*2)+1);

    }
}

void postorder(int tree[],int t)
{
    if(tree[t]!=0)
    {
        postorder(tree,t*2);
        postorder(tree,(t*2)+1);
         printf("%d(%d)\t",tree[t],t);
    }
}

int main()
{
    register int i,t;
    int n,a[100],tree[250]={0},count;
    int choice;

    printf("Enter the number of elements\n");
    scanf("%d",&n);

    printf("Enter the elements\n");

    for(i=1;i<=n;i++)         //Array starts from 1
        scanf("%d",&a[i]);


                                //Making Binary tree

      for(i=1;i<=n;i++)
      {

          insert(a[i],tree,1); /*Search begins from root node*/
      }

      printf("Binary tree search is\n");
      i=1;
      count=0;
     while(count<n)     //For printing BST,while loop ends when count=n i.e when all non null elements of tree are printed
     {
         if(tree[i]!=0)
         {
             printf("%d(%d) \t",tree[i],i);
             count++;
             if(count==n)
                   lastIndex=i;       //Points where the last element in BST is stored.


         }
         i++;

    }
     printf("\n\n");
       printf("Choose from the options :\n");
       printf("(1) Preorder Traversal.\n");
       printf("(2) Postorder Traversal.\n");
       printf("(3) Inorder Traversal.\n");
       printf("(4) Search an Element.\n");
       printf("(5) Exit.\n");
       printf("Your Choice: ");

 while(choice!=5)
 {
       scanf("%d",&choice);
       switch(choice)
       {
            case 1:
            {
                printf("\n\n");
                printf("Preorder traversal for BST is \n ");
                preorder(tree,1);                        //Traversals begins from root
                 printf("\n\n");
                break;
            }
            case 2:
                {

                     printf("Postorder traversal for BST is \n");
                    postorder(tree,1);
                     printf("\n\n");
                    break;
                }
            case 3:
                {
                   printf("Inorder traversal for BST is \n");
                    inorder(tree,1);
                     printf("\n\n");
                    break;
                }
            case 4:             //Does the searching
                {
                    int key;
                    printf("Enter the number to search .\n");
                    scanf("%d",&key);
                    search(tree,1,key);
                        printf("\n");
                    break;
                }
       }

 }

    return 0;
}


