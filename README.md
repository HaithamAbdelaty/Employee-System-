#include <iostream>
using namespace std; 
int main()
{
	const int num=10000;

	int age[num] , salary[num];
	char gender[num]; string name[num]; 
	int added = 0; 
	while (true)
	{
		int choice = -1; 
		cout << "Enter your choice : " << endl;
		cout << "1)Add new employee " << endl;
		cout << "2)Print all employees" << endl;
		cout << "3)Delete by age " << endl;
		cout << "4)Update salare by name" << endl;
		cin >> choice; 

		if (1 < choice || choice > 4)
			cout << "Invalid choice. Try again \n \n";

		if (choice == 1) {
			cout << "please Enter the information of the Employee \n";
			cout << "name :";  cin >> name[added];    cout << "\n";
			cout << "Gender :";  cin >> gender[added];   cout << "\n";
			cout << "Age :";       cin >> age[added];          cout << "\n";
			cout << "Salary :";      cin >> salary[added];         cout << "\n";
			added++; 
		}
		if (choice == 2) {
			for (int i = 0; i < added; i++)
				cout << name[i] << "  " << gender[i] << "  " << age[i] << "  " << salary[i] << endl;	
		}
		 
		if (choice == 3)
		{
			int st, en; 
			cout << "Please Enter the range age for the employees" << endl;
			cin >> st >> en;
			for (int i = 0; i < added; i++)
			{
				if (st <= age[i] && en >= age[i])
					age[i] = -1; 
			}
		}
		if (choice == 4)
		{
			string Name;
				int  Salary; 
			cin >> Name >> Salary;

				bool is_found = false;
				for (int i = 0; i < added; i++)
				{
					if (name[i] == Name && age[i] != -1)
					{
						is_found = true;
						salary[i] = Salary;
					}
					if (!is_found)
						cout << "No employee with this name!\n";
				}


		}


	}

}
