# Dental Cost Estimator

## Description
This program estimates the total cost of dental care based on procedure type, duration, materials needed, and senior citizen discounts.

## Used to Create:

- **Visual Studio**
- **C# (Console Application)**

## Procedure for Estimating the Total Cost:
- Consultation fee of $100
- Doctor's charge of $50 per hour
- Additional staff charge of $25 per hour
- Material cost of $0.10 per ounce
- 10% discount for senior citizens



## Code:

```csharp
using System;

namespace DentalCostEstimator
{
    class Program
    {
        static void Main(string[] args)
        {
            double consultationFee = 100; // Consultation Fee
            double dentistFee = 50; // Dentist's Fee per Hour
            double staffFee = 25; // Staff's Fee per Hour
            double materialCost = 0.10; // Material Cost per Ounce
            double discount = 0.10; // Senior Citizen Discount

            // Collect user input
            Console.WriteLine("Enter the client's name:");
            string clientName = Console.ReadLine();

            Console.WriteLine("Enter the type of procedure (e.g., cleaning, filling, etc.):");
            string procedureType = Console.ReadLine();

            Console.WriteLine("Enter the duration of the procedure (hours):");
            double duration = double.Parse(Console.ReadLine());

            Console.WriteLine("Enter the amount of material needed (ounces):");
            double materialAmount = double.Parse(Console.ReadLine());

            Console.WriteLine("Enter the number of additional staff needed:");
            int additionalStaff = int.Parse(Console.ReadLine());

            Console.WriteLine("Is the client a senior citizen? (Enter 1 for yes, 0 for no):");
            int isSenior = int.Parse(Console.ReadLine());

            // Calculate the total cost without discount
            double totalCost = consultationFee + (duration * dentistFee) + (duration * additionalStaff * staffFee) + (materialAmount * materialCost);

            // Apply discount if senior citizen
            if (isSenior == 1)
            {
                totalCost -= totalCost * discount;
            }

            // Output the result
            Console.WriteLine($"\nClient: {clientName}");
            Console.WriteLine($"Procedure: {procedureType}");
            Console.WriteLine($"Duration: {duration} hours");
            Console.WriteLine($"Material: {materialAmount} ounces");
            Console.WriteLine($"Additional Staff: {additionalStaff}");
            Console.WriteLine($"Senior Citizen Discount: {(isSenior == 1 ? "Applied" : "Not Applied")}");
            Console.WriteLine($"Total Cost: ${totalCost:F2}");

            // Wait for user to close the application
            Console.ReadLine();
        }
    }
}
