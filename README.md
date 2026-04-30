#include <iostream>
using namespace std;

int searchList(const int [], int, int);
const int SIZE = 18;



int main()
{
	int accountNum[SIZE] = {1005231, 1250255, 1302850, 3852085, 4520125, 4562555, 4581002, 5050552,
	                        5552012, 5658845, 6545231, 7576651, 7825877, 7881200, 7895122, 8080152, 8451277, 8777541
	                       }; // The charge account numbers
	int results;
	int value; // Variables to be stored

	cout << "Enter an account number to search for: ";
	cin >> value; // Take use input

	results = searchList(accountNum, SIZE, value);
	if(results == -1) // Display if the account number exists
		cout << "This account number is not in this array \n";
	else  //True or False
	{
		cout << "The account number is found at element " << results;
		cout << " in the array.\n"; // Displays the position that the charge account number is found at in the array
	}
	return 0;
}

int searchList(const int list[], int accountNum, int value)
{
	int index = 0; // USed as a subsript tp search array
	int position = -1; // Brings the code back to -1 after finding the number
	bool found = false; // Flag to indicate if the value was found

	while (index < accountNum && !found)
	{
		if (list[index] == value) // If the value is found
		{
			found = true; // Set the flag
			position = index; // Recprd the value's subscript
		}
		index++; // Go to the next element
	}
	return position; // Return the position, or -1
}
