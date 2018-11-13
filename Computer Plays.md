```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GuessMyNumberComputerPlays
{
    class Program
    {
        static void Main(string[] args)
        {
            //the human chooses a number between 1 and 100
            //and then the computer guesses the number
            int start = 1;
            int end = 100;
            int guess = (end + start) / 2;

            Guess(guess, start, end);
        }

        private static void Guess(int guess, int start, int end)
        {
            Console.WriteLine("\n\t Hello Friend!");
            Console.WriteLine("\t Pick a number between 1-100 and I will guess what it is.");
            Console.WriteLine("\t Please respond with one of the following: " +
                "\n\t\t\t Too high \n\t\t\t Too low \n\t\t\t You got it");
            Console.WriteLine("\t------------------------------------------------------------");
            Console.WriteLine($"\n\t I guess the number {guess}. Am I right?");

            string resp = Console.ReadLine();
            
            if (resp.ToLower() == "too high")
            {
                end = guess - 1;
                guess = (end + start) / 2;
                Guess(guess, start, end);
            }
            else if (resp.ToLower() == "too low")
            {
                start = guess + 1;
                guess = (end + start) / 2;
                Guess(guess, start, end);
            }
            else if (resp.ToLower() == "you got it")
            {
                Console.WriteLine("\n\t WTF!! ==> Wow That's Fun!");
            }
        }
    }
}
```
