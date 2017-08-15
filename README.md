#include <iostream>
#include <string.h>
#include <cstdlib>
#include <conio.h>

using namespace std;

stuct room {
    char name [10];
    int days;
    int num;
    float bill;
    bool isVacant;
};

struct hotel {
    struct room r[5][5];
};

do{
    cout << "Hotel Management\n";
    cout << "\n1. Available Rooms";
    cout << "\n2. Reserve Room";
    cout << "\n3. Check Out";
    cout << "\n4. Search Person";
    cout << "\n5. Display Rooms";
    cout << "\n6. Exit";
    cin >> choice;
    
    if (choice ==1){
      for(i=0; i<5; i++)
        for(j=0; j<5; j++)
          if (h.r[i][j].isVacant)
    


    



