#include<stdio.h>
#include<string.h>
main()
{
 static int totalCost;
 int i,j,choice,c=1,a[9],cost[9];
 for(i=0;i<9;i++)
 a[i]=0;
 
 char str[100];
 char items[9][100]={"chicken","mutton","salomon","crab","pork","peru","prawn","cutla","rohu" 
 };
 printf("Please Enter Your Name\n");
 gets(str);
 printf("Hello %s, Welcome to T meat Shop.\n",str);
 do{
  //C is 1 by default
  if(c==1){
  printf("Enter\n1 - meat\n2 - Fishes\n3 - shellfishesAny other number to exit\n");
  scanf("%d",&choice);
  switch(choice)
  {
   case 1:
   {
    int meatChoice;
    printf("Enter\n1 - chicken- Rs.155/kg\n2 - mutton- Rs.500/kg\n3 - pork - Rs.550/kg\nAny other number to exit\n");
    scanf("%d",&meatChoice);
    cost[0]=155;
    cost[1]=500;
    cost[2]=550;
    switch(meatChoice)
    {
     case 1:
     {
      int num;
      printf("You chose chicken nwith Rs.355.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[0]++;
       totalCost+=355;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 2:
     {
      int num;
      printf("You chose mutton 500rs/kg Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[1]++;
       totalCost+=500;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 3:
     {
      int num;
      printf("You chose Pork with Rs.550.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[2]++;
       totalCost+=550;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     default:{
      printf("Exit meat section\n");
      break;
     }
    }
    break;
   }
   case 2:
   {
    int fishchoice;
    printf("Enter\n1 -cutla- 250/kg\n2 - salamon - Rs.500/kg\n3 - peru - Rs.280/kg\nAny other number to exit\n");
    scanf("%d",&fishchoice);
    cost[3]=250;
    cost[4]=500;
    cost[5]=280;
    switch(fishchoice)
    {
     case 1:
     {
      int num;
      printf("You chose cutla pricin 250/kg Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[3]++;
       totalCost+=3550;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 2:
     {
      int num;
      printf("You chose salmon Rs.500.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[4]++;
       totalCost+=5000;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 3:
     {
      int num;
      printf("You chose peru for Rs.280.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[5]++;
       totalCost+=2800;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     default:{
      printf("Exit from Fish Category\n");
      break;
     }
    }
    break;
   }
   case 3:
   {
    int shellfishChoice;
    printf("Enter\n1 - crab - Rs.110/kg\n2 - prawn - Rs.900/kg\n3 - Squid- Rs.128/kg\nAny other number to exit\n");
    scanf("%d",&shellfishChoice);
    cost[6]=11000;
    cost[7]=9866;
    cost[8]=12800;
    switch(shellfishChoice)
    {
     case 1:
     {
      int num;
      printf("You chose to buy crab -110rs/kg.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[6]++;
       totalCost+=110;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 2:
     {
      int num;
      printf("You chose to buy prawn for Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[7]++;
       totalCost+=9866;
      }
      printf("Your Cost in Cart is %d\n",totalCost);
      break;
     }
     case 3:
     {
      int num;
      printf("You chose to buy Samsung for Rs.12800.Are you sure to buy.If 'Yes' Enter 1 else any number\n");
      scanf("%d",&num);
      if(num==1)
      {
       a[8]++;
       totalCost+=12800;
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
   default:
   {
    printf("Enter Valid Categories Choice\n");
    break;
   }
  }
  printf("%s's cart\n",str);
  printf("Id\tItems\t\t\tQuantity\t\t\tCost\n");
  for(i=0;i<9;i++)
  {
   if(a[i]!=0)
   {
    printf("%d\t%s\t\t%d\t\t\t%d\n",i,items[i],a[i],(cost[i]*a[i]));
   }
  }
  printf("Total Cost\t\t\t\t\t%d\n",totalCost);
  printf("If you wish to buy anything more Enter\n1 to Add Item\n2 to Delete Items \nAny other number to Exit\n");
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
       printf("Id\tItems\t\t\tQuantity\t\tCost\n");
            for(i=0;i<9;i++)
      {
     if(a[i]!=0)
      {
    printf("%d\t%s\t\t%d\t\t%d\n",i,items[i],a[i],(cost[i]*a[i]));
      }
     }
        printf("Total Cost\t\t\t\t\t%d\n",totalCost);
        printf("If you wish to buy anything more Enter\n1 to Add Item\n2 to Delete Items \nAny other number to Exit\n");
     scanf("%d",&c);
  }
  
 }while(c==1 || c==2);
 printf("Your Final Cost is %d\n",totalCost);
 printf("Thanks %s for Choosing Us and Visit us again.\n",str);
 
}
