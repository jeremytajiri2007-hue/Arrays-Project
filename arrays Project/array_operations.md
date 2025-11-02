// Name: Jeremy Tajiri
// Course: CISC 192 - C++ Programming
// Date: 11/2/2025
// Assignment: Non-Duplicated Integer Array Operations

include <iostream>
include <array>
using namespace std;

int main() {
   const int SIZE = 5;
   array<int, SIZE> arr;
   int x;
   bool repeat;

   cout<<"Enter "<<SIZE<<" unique integers:"<<endl;

   for(int i=0;i<SIZE;i++){
      do{
         repeat=false;
         cout<<"Element "<<i+1<<": ";
         cin>>x;
         for(int j=0;j<i;j++){
            if(arrj==x){
               cout<<"Duplicate number, enter a new one.\n";
               repeat=true;
               break;
            }
         }
      }while(repeat);
      arri=x;
   }

   cout<<"\nPick one:\n";
   cout<<"1 - Ascending sort\n";
   cout<<"2 - Descending sort\n";
   cout<<"3 - Find max\n";
   cout<<"Choice: ";

   int c; 
   cin>>c;

   if(c==1){
      // ascending
      for(int i=0;i<SIZE-1;i++){
         for(int j=i+1;j<SIZE;j++){
            if(arri>arrj){
               int t=arri;
               arri=arrj;
               arrj=t;
            }
         }
      }
      cout<<"\nSorted ascending: ";
      for(int i=0;i<SIZE;i++) cout<<arri<<" ";
      cout<<endl;
   }
   else if(c==2){
      // descending
      for(int i=0;i<SIZE-1;i++){
         for(int j=i+1;j<SIZE;j++){
            if(arri<arrj){
               int t=arri;
               arri=arrj;
               arrj=t;
            }
         }
      }
      cout<<"\nSorted descending: ";
      for(int i=0;i<SIZE;i++) cout<<arri<<" ";
      cout<<endl;
   }
   else if(c==3){
      int biggest=arr0;
      for(int i=1;i<SIZE;i++){
         if(arri>biggest)
            biggest=arri;
      }
      cout<<"\nMax value is "<<biggest<<endl;
   }
   else{
      cout<<"\nInvalid option\n";
   }

   return 0;
}
