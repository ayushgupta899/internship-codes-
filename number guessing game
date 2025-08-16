#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main()
{
    int randomNumber;
    int guess;
    int chances = 0;
    srand(time(0));
    
    int upperValue,lowerValue;
    cout<<" enter the upper value upto which a random number can be "<<endl;
    cin>>upperValue;
    cout<<" enter the lower value down to which a random number can be "<<endl;
    cin>>lowerValue;
    
    randomNumber = (rand() % (upperValue-lowerValue) + 1);
 
    cout << " Welcome to guess the number game "<<endl<<endl;

    do
    {
        cout << "Enter your guess between "<<lowerValue<<" and "<<upperValue<<endl;
        cin >> guess;
        chances++;

        if (guess > randomNumber){
            cout << "The "<<guess<<" is too high "<<endl;
        }
        else if (guess < randomNumber){
            cout<<guess<<" is too low "<<endl;
        }
        else{
            cout <<" You got the right guess "<<guess <<" in "<< chances<<" tries "<<endl;
        }
    } 
        while (guess != randomNumber);

	return 0;
}
