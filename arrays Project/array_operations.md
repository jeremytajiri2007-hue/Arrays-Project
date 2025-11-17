// Name: Jeremy Tajiri
// Course: CISC 192 - C++ Programming
// Date: 11/02/2025
// Assignment: Non-Duplicated Integer Array Operations

#include <iostream>
#include <array>
using namespace std;

int main() {

   const int SIZE = 5;
   array<int, SIZE> arr;
   int n;
   bool repeat;

   cout << "Enter " << SIZE << " numbers (no repeats):" << endl;

   for (int i = 0; i < SIZE; i++) {
      do {
         repeat = false;
         cout << "Value " << i+1 << ": ";
         cin >> n;

         for (int j = 0; j < i; j++) {
            if (arr[j] == n) {
               cout << "Duplicate, pick another.\n";
               repeat = true;
               break;
            }
         }
      } while (repeat);
      arr[i] = n;
   }

   cout << "\n1) Sort ascending\n";
   cout << "2) Sort descending\n";
   cout << "3) Show biggest\n";
   cout << "Pick: ";
   int c;
   cin >> c;

   if (c == 1) {
      for (int i=0; i<SIZE-1; i++) {
         for (int j=i+1; j<SIZE; j++) {
            if (arr[i] > arr[j]) {
               int t = arr[i];
               arr[i] = arr[j];
               arr[j] = t;
            }
         }
      }
      cout << "\nSorted (low to high): ";
      for (int i=0; i<SIZE; i++) cout << arr[i] << " ";
      cout << endl;
   }

   else if (c == 2) {
      for (int i=0; i<SIZE-1; i++) {
         for (int j=i+1; j<SIZE; j++) {
            if (arr[i] < arr[j]) {
               int tmp = arr[i];
               arr[i] = arr[j];
               arr[j] = tmp;
            }
         }
      }
      cout << "\nSorted (high to low): ";
      for (int i=0; i<SIZE; i++) cout << arr[i] << " ";
      cout << endl;
   }

   else if (c == 3) {
      int maxVal = arr[0];
      for (int i=1; i<SIZE; i++) {
         if (arr[i] > maxVal)
            maxVal = arr[i];
      }
      cout << "\nThe max one is " << maxVal << endl;
   }

   else {
      cout << "\nInvalid choice entered.\n";
   }

   return 0;
}
