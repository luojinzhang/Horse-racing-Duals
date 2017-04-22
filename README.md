# Horse-racing-Duals

using linq to calculate the min delta of a list of integer
using System;
using System.Linq;
using System.IO;
using System.Text;
using System.Collections;
using System.Collections.Generic;


class Solution
{
    static void Main(string[] args)
    {
        int N = int.Parse(Console.ReadLine());
        List <int> horses = new List<int> ();
        for (int i = 0; i < N; i++)
        {
            horses.Add(int.Parse(Console.ReadLine()));
        }
        horses.Sort();
        horses.Reverse();
        
      /*  int lastDifferent = new int();
        int currentDifferent = new int();
        int lastInt = new int();
        
       for (int i = 0; i < N; i++)
        {
            if (i == 0)
            {
                lastInt = horses[i];
                continue;
            }
           
                currentDifferent = horses[i] - lastInt;
               // Console.Error.WriteLine(i + " " + currentDifferent);
                lastInt = horses[i];
                if ( i == 1 || lastDifferent > currentDifferent)
                {
                    lastDifferent = currentDifferent;
                    
                }
                else if (lastDifferent < currentDifferent)
                {
                    continue;
                }
        }
        Console.WriteLine(lastDifferent);
        */
        
        int minDelta = horses.Select(x=>x).Zip(horses.Select(x=>x).Skip(1),(current,next)=>current - next).Min();
        Console.WriteLine(minDelta);
        
        // Write an action using Console.WriteLine()
        // To debug: Console.Error.WriteLine("Debug messages...");
    }
}
