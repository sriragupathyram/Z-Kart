#include <stdio.h>
#include <string.h> 
int main() {
    char mailid[15];
    char password[12];
    printf("***WELCOME TO Z-KART***\nEnter your mailid:\n"); 
    scanf("%s",&mailid); 
    printf("Enter your password:\n"); 
    scanf("%s",&password); 
    if(strcmp(mailid,"abc@zoho.com")==0)
    { 
        if(strcmp(password,"ApipNbjm")==0)
        { 
        printf("Name: RAHUL\n");
        printf("Mobile: 9922992299\n");
        }
    }
    else if(strcmp(mailid,"123@zoho.com")==0)
    { 
        if(strcmp(password,"Cboljoh")==0)
        { 
        printf("Name: ANITHA\n");
        printf("Mobile: 8564119904\n");
        }
    }
    else if(strcmp(mailid,"user@zoho.com")==0)
    { 
        if(strcmp(password,"kbwb22")==0)
        { 
        printf("Name: ARPAN\n");
        printf("Mobile: 9872345693\n");
        }
    }
    else
    { 
        printf("\n***User doesn't exist***"); 
        return 0;
    }
    {
 static int totalCost;
 int i,j,choice,c=1,a[9],cost[9];
 for(i=0;i<9;i++)
 a[i]=0;
 char str[100];
 char items[9][100]={"Apple","Motorola","HP","Google"};
 gets(str);
 printf("Hello %s, Welcome to our Z-Kart Online Shopping.\n",str);
 do{
  //C is 1 by default
  if(c==1){
  printf("Enter\n1 - Mobile\n2 - Laptop\n3 - Tablet\nAny other number to exit\n");
  scanf("%d",&choice);
  switch(choice)
  {
   case 1:
   {
    int Mobile;
    printf("Enter\n1 - Apple6s - Rs.60000\n2 - MotorolaG- Rs.12000\nAny other number to exit\n");
    scanf("%d",&Mobile);
    cost[0]=60000;
    cost[1]=12000;
    switch(Mobile)
    {
     case 1:
     {
      int num;
      printf("You chose Apple6s with Rs.60000.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[0]++;
       totalCost+=60000;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 2:
     {
      int num;
      printf("You chose MotorolaG with Rs.12000.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[1]++;
       totalCost+=12000;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     default:{
      printf("Exit from Mobile Category\n");
      break;
     }
    }
    break;
   }
   case 2:
   {
    int Laptop;
    printf("Enter\n1 - HP Elite - Rs.50000\nAny other number to exit\n");
    scanf("%d",&Laptop);
    cost[2]=50000;
    switch(Laptop)
    {
     case 1:
     {
      int num;
      printf("You chose HP Elite for Rs.50000.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[2]++;
       totalCost+=50000;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     default:{
      printf("Exit from Shoes Category\n");
      break;
     }
    }
    break;
   }
   case 3:
   {
    int Tablet;
    printf("Enter\n1 - Google ChromeBook - Rs.8000\nAny other number to exit\n");
    scanf("%d",&Tablet);
    cost[3]=8000;
    switch(Tablet)
    {
     case 1:
     {
      int num;
      printf("You chose to buy Google ChromeBook for Rs.8000.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[3]++;
       totalCost+=8000;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     default:{
      printf("Exit from Tablet Category\n");
      break;
     }
    }
    break;
   }
   default:
   {
    printf("Enter Valid Categories Choice\n");
    break;
   }
  }
  printf("%s's cart\n",str);
  printf("Id\tItems\t\tQuantity\tCost\n");
  for(i=0;i<9;i++)
  {
   if(a[i]!=0)
   {
    printf("%d\t%s\t\t%d\t\t\t%d\n",i,items[i],a[i],(cost[i]*a[i]));
   }
  }
  printf("Total Cost\t\t\t\t\t%d\n",totalCost);
  printf("If you wish to buy anything more Enter\n1 to Add Item\n2 to Delete Items\n3 to Change Quantity \nAny other number to Exit\n");
  scanf("%d",&c);
 }
  if(c==2)
  {
   int id;
   printf("Enter id to delete item\n");
   scanf("%d",&id);
   if(id<9&&id>0){
   totalCost=totalCost-(cost[id]*a[id]);
   a[id]=0;
   }
   else{
    printf("Enter Valid id\n");
   }
       printf("Revised Items \n");
       printf("Id\tItems\t\tQuantity\tCost\n");
            for(i=0;i<9;i++)
      {
     if(a[i]!=0)
      {
    printf("%d\t%s\t%d\t\t%d\n",i,items[i],a[i],(cost[i]*a[i]));
      }
     }
        printf("Total Cost\t\t\t\t\t%d\n",totalCost);
        printf("If you wish to buy anything more Enter\n1 to Add Item\n2 to Delete Items\n3 to Change Quantity \nAny other number to Exit\n");
     scanf("%d",&c);
  }
  if(c==3)
  {
   int id,quantity;
   printf("Enter id to Change quantity of an item\n");
   scanf("%d",&id);
   printf("Enter quantity to be changed of an item\n");
   scanf("%d",&quantity);
   if(id<9&&id>0){
    if(quantity>0 && a[id]>0){  
        if(quantity<a[id]) 
     {
      int dec=a[id]-quantity;
      a[id]=quantity;
       totalCost=totalCost-(cost[id]*dec); 
     }
     if(quantity>a[id]) 
     {
      int inc=quantity-a[id];
      a[id]=quantity;
       totalCost=totalCost+(cost[id]*inc); 
     }
     if(quantity==a[id]) 
     {
      a[id]=quantity;
       totalCost=totalCost+0; 
     }   
    }
    else{
       printf("Item has no Quantity.Please Try again\n");
    }
     }
     else{
    printf("Enter Valid id\n");
   }
       printf("Revised Items \n");
       printf("Id\tItems\t\tQuantity\tCost\n");
            for(i=0;i<9;i++)
      {
     if(a[i]!=0)
      {
    printf("%d\t%s\t%d\t\t%d\n",i,items[i],a[i],(cost[i]*a[i]));
      }
     }
        printf("Total Cost\t\t\t\t\t%d\n",totalCost);
        printf("If you wish to buy anything more Enter\n1 to Add Item\n2 to Delete Items\n3 to Change Quantity \nAny other number to Exit\n");
     scanf("%d",&c);
  }
 }while(c==1 || c==2 ||c==3);
 printf("Your Final Cost is %d\n",totalCost);
 printf("Thanks %s for Choosing Us and Visit us again.\n",str);
}
    return 0;
}
