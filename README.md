# number-guessing-game
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main()
{
    int number, guess;
    int attempts;
    char choice;

    // Seed random number generator
    srand(time(0));

    cout << "=================================\n";
    cout << "       NUMBER GUESSING GAME\n";
    cout << "=================================\n";

    do
    {
        // Generate random number between 1 and 100
        number = rand() % 100 + 1;
        attempts = 0;

        cout << "\nI have selected a number between 1 and 100.";
        cout << "\nTry to guess the number!\n";

        // Guessing loop
        do
        {
            cout << "\nEnter your guess: ";
            cin >> guess;

            attempts++;

            if (guess > number)
            {
                cout << "Too High! Try again.\n";
            }
            else if (guess < number)
            {
                cout << "Too Low! Try again.\n";
            }
            else
            {
                cout << "\nCongratulations! You guessed correctly!";
                cout << "\nThe correct number is: " << number;
                cout << "\nTotal Attempts: " << attempts;
            }

        } while (guess != number);

        // Display final score
        cout << "\n\nYour Final Score: " << attempts << " attempts";

        // Replay option
        cout << "\n\nDo you want to play again? (Y/N): ";
        cin >> choice;

    } while (choice == 'Y' || choice == 'y');

    cout << "\nThank you for playing!";
    cout << "\nGame Over!\n";

    return 0;
}