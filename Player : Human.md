```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace GuessMyNumberHumanPlays
{
    class Program
    {
        static void Main(string[] args)
        {
            //the computer randomly chooses a number between 1 and 1000
            //and then the human guesses the number
            Random rdm = new Random();
            int num = rdm.Next(1, 1001);

            Console.WriteLine("\n\t Can you guess my number? It's between 1 and 1000.");
            Guess(num);
        }

        private static void Guess(int num)
        {
            int guess = Convert.ToInt32(Console.ReadLine());
            if (guess > num)
            {
                Console.WriteLine("\n\t Too High! You suck. Try again.");
                Guess(num);
            }
            else if (guess < num)
            {
                Console.WriteLine("\n\t Too Low! You suck. Try again.");
                Guess(num);
            }
            else
            {
                Console.WriteLine("\n\t It's about time you got it!");
            }
        }
    }
}
```
