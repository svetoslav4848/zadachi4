# zadachi4


using System;

namespace ConsoleApp5
{
    class Program
    {
        static void Main(string[] args)
        {
            double budget = double.Parse(Console.ReadLine());
            string category = Console.ReadLine();
            int peopleInGroup = int.Parse(Console.ReadLine());
            double transportBudget = 0;

            if(peopleInGroup >= 1 && peopleInGroup <= 4)
            {
                transportBudget = budget * 0.75;
            }
            else if(peopleInGroup >= 5 && peopleInGroup <= 9)
            {
                transportBudget = budget * 0.60;
            }
            else if(peopleInGroup >=10 && peopleInGroup <= 24)
            {
                transportBudget = budget * 0.50;
            }
            else if(peopleInGroup >=25 && peopleInGroup <= 49)
            {
                transportBudget = budget * 0.40;
            }
            else if (peopleInGroup >= 50)
            {
                transportBudget = budget * 0.25;
            }
            else
            {
                Console.WriteLine("People in group must be 1 or more");
                return;
            }
            double gameTicketsBudget = budget - transportBudget;
            double gameTicketsCost = peopleInGroup;

            switch (category)
            {
                case "VIP":
                    gameTicketsCost *= 499.99;
                    break;
                case "Normal":
                    gameTicketsCost *= 249.99;
                    break;
                default:
                    Console.WriteLine("Unknown category name.");
                    return;

            }
            double totalActualBudget = transportBudget + gameTicketsCost;
            if(budget >= totalActualBudget)
            {
                double levaleft = budget - totalActualBudget;
                Console.WriteLine($"Yes! You have {levaleft:f2} leva left.");
            }
            else
            {
                double insufficient = totalActualBudget - budget;
                Console.WriteLine($"Not enough money! You need {insufficient:f2} leva.");
            }


        }
    }
}
