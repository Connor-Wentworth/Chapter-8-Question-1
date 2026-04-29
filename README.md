#include <iostream>
using namespace std;

int searchList(const int [], int, int);
const int SIZE = 18;



int main()
{
	int accountNum[SIZE] = {1005231, 1250255, 1302850, 3852085, 4520125, 4562555, 4581002, 5050552,
	                        5552012, 5658845, 6545231, 7576651, 7825877, 7881200, 7895122, 8080152, 8451277, 8777541
	                       };
	int results;
	int value;

	cout << "Enter an account number to search for: ";
	cin >> value;
	
	results = searchList(accountNum, SIZE, value);
	if(results == -1)
		cout << "This account number is not in this array \n";
	else
	{
		cout << "The account number is found at element " << results;
		cout << " in the array.\n";
	}
	return 0;
}

int searchList(const int list[], int accountNum, int value)
{
	int index = 0;
	int position = -1;
	bool found = false;

	while (index < accountNum && !found)
	{
		if (list[index] == value)
		{
			found = true;
			position = index;
		}
		index++;
	}
	return position;
}
