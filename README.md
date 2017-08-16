#include <iostream>
#include <string.h>
#include <cstdlib>
#include <conio.h>

using namespace std;

struct room {
    char name [10];
    int days;
    int num;
    float bill;
    bool isVacant;
};

struct hotel {
    struct room r[5][5];
};

int SearchPerson(char n[], struct hotel h){
	int i, j;
	
	for(i=0; i<5; i++)
		for(j=0; j<5; j++)
			if(strcmp(h.r[i][j].name, n)==0){
				return h.r[i][j].num;
				break;
			}
			return 0;
}

int main(){
	int choice=0;
	struct hotel h;
	int i, d;
	int j;
	char n[10];
	int RoomNum;
	char trash;
	
	for (i=0;i<5;i++)
		for(j=0;j<5;j++){
			h.r[i][j].num = 100 + i * 100 +j + 1;
			h.r[i][j].isVacant = true;
		}

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
      
    
    else if(choice == 3){
	cout<<"Enter Room number: ";
	cin >> RoomNum;			
		
	if(h.r[i][j].num = RoomNum && h.r[i][j].isVacant == false){
		h.r[i][j].isVacant = true;
		strcpy(h.r[i][j].name, " ");
		h.r[i][j].days = 0;
		h.r[i][j].bill = 0;			
	}
	
	else
		cout<< "Invalid Command";
		cout<< "\nEnter any letter to proceed: ";
		cin>> trash;
		system("cls");
	}
		
	else if(choice == 4){
		cout << "Enter surname of person: ";
		cin >> n;
		
		if(SearchPerson(n, h) != 0)
			cout<< SearchPerson(n, h);
		else 
			cout<< "Person cannot be found";
			
			cout<< "\nEnter any letter to proceed: ";
			cin>> trash;
			system("cls");
	}
	
	else if(choice==5){
		for(i=0; i<5; i++)
			for(j=0; j<5; j++){
			cout<< "\nRoom: " << h.r[i][j].num;
			
			if(!h.r[i][j].isVacant){
				cout<< "\nVacant: False";
				cout<< "\nTenant: "<<h.r[i][j].name;
				cout<< "\nDays: "<<h.r[i][j].days;
				cout<< "\nBill: "<<h.r[i][j].bill;
			}
			if(h.r[i][j].isVacant)
				cout<< "\nVacant = True";
			}
			cout<< "\nEnter any letter to proceed: ";
			cin>>trash;
			system("cls");
	}
	
	else if(choice == 6){
		system("cls");
		cout<< "Program is shutting down. Thank You!";
	}


    }while(choice != 6);
}



