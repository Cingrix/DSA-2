#include<stdio.h>
#include<stdlib.h>

struct node
{   
    int coeff;
    int power;
    struct node *next;
};


struct node *addpoly(struct node *poly1, struct node *poly2) {
    struct node *head = NULL, *current = NULL;

    while (poly1 != NULL || poly2 != NULL) {
        struct node *newTerm = (struct node *)malloc(sizeof(struct node));
        newTerm->next = NULL;

        if (head == NULL) {
            head = newTerm;
            current = head;
        } else {
            current->next = newTerm;
            current = newTerm;
        }

        if (poly1 != NULL && poly2 != NULL) {
            if (poly1->power == poly2->power) {
                newTerm->power = poly1->power;
                newTerm->coeff = poly1->coeff + poly2->coeff;
                poly1 = poly1->next;
                poly2 = poly2->next;
            } else if (poly1->power < poly2->power) {
                newTerm->power = poly2->power;
                newTerm->coeff = poly2->coeff;
                poly2 = poly2->next;
            } else {
                newTerm->power = poly1->power;
                newTerm->coeff = poly1->coeff;
                poly1 = poly1->next;
            }
        } else if (poly1 != NULL && poly2 == NULL) {
            newTerm->power = poly1->power;
            newTerm->coeff = poly1->coeff;
            poly1 = poly1->next;
        } else if (poly1 == NULL && poly2 != NULL) {
            newTerm->power = poly2->power;
            newTerm->coeff = poly2->coeff;
            poly2 = poly2->next;
        }
    }

    return head;
}



struct node *create(struct node *head)
{
    int flag=1;
    struct node *temp,*newnode;
    temp=head;
    while(flag==1)
    {   
        newnode=(struct node *)malloc(sizeof(struct node));
        
        printf("Enter the coefficient of the current expression of the polynomial:\n");
        scanf("%d",&newnode->coeff);
        printf("Enter the power of the current expression of the polynomial:\n");
        scanf("%d",&newnode->power);

        if(head==NULL)
        {
            head=newnode;
            head->next=NULL;
            temp=head;
        }
        else
        {
            temp->next=newnode;
            temp=newnode;
            temp->next=NULL;
        }
        printf("Enter the 0 to terminate or 1 to continue entering input:\n");
        scanf("%d",&flag);
    }
    return head;
}

struct node display(struct node *head)
{
    struct node *temp;
    temp=head;
    while(temp!=NULL)
    {
        if(temp->next!=NULL)
        printf("%dx^%d+",temp->coeff,temp->power);     
        else
        printf("%dx^%d",temp->coeff,temp->power);
        temp=temp->next;
    }
    printf("\n");
}

int main()
{
    struct node *poly,*poly2,*result;
    poly=NULL;
    poly2=NULL;
    printf("Enter the first polynomial:\n");
    poly=create(poly);
    printf("Enter the second polynomial:\n");
    poly2=create(poly2);
    printf("The First polynomial is: \n");
    display(poly);
    printf("The Second polynomial is: \n");
    display(poly2);
    result=addpoly(poly,poly2);
    printf("The resultant polynomal is:\n");
    display(result);
}
