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
      for (i=0; i<5; i++)
      for (j=0; j<5; j++)
      if (h.r[i][j].isVacant)
      cout <<h.r[i][j].num<<"\n";
      cout << "\n Enter any letter to proceed: ";
      cin >> trash;
      system ("cls");
    }
    
    else if (choice ==2){
       cout << "Input surname: ";
       cin >> n;
       cout << "Enter room number: ";
       cin >> RoomNum;
       cout << "Enter number of days: ";
       cin >> d;
       
       for (i=0; i<5; i++)
       for (j=0; j<5; j++)
       if (h.r[i][j].num == RoomNum && h.r[i][j].isVacant){
             h.r[i][j].isVacant = false;
             strcpy(h.r[i][j].name, n);
             h.r[i][j].days = d;
             h.r[i][j].bill = h.r[i][j].bill;
        }
        
        cout << "\nEnter any letter to proceed: ";
        cin >> trash;
        system ("cls");
    }
      
    


    



