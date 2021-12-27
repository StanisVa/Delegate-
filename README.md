using System;
using System.Collections.Generic;

namespace CSharpEssentials
{
    class Program
    {
        // делегат
        delegate bool Predicate(int year);

        // метод делегата
        private static bool IsAdult(int year)
        {
            return year >= 18;
        }
        private static List<int> GetAdults(List <int>
years, Predicate predicate)
        {
            int i = 0;
            List<int> adults = new List<int>();
            while (i< years.Count)
            { 
                if(predicate(years[i]))
                {
                    adults.Add(years[i]);
                }
                i++;
            }
            return adults;
        }
        // Здесь реализуйте метод GetAdults

        static void Main()
        {
            List<int> years = new List<int> { 13, 17, 18, 19, 20, 50 };

            List<int> adults = GetAdults(years, IsAdult);

            foreach (var adult in adults)
            {
                Console.WriteLine(adult);
            }
        }

        
    }
}
