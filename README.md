using System.Text.RegularExpressions;

namespace Car_Dealership_interface
{
    internal class Program
    {
        public abstract class exp
        {
            public String Name { get; set; }
            public abstract double monthlypay();
        }
        class fuel : exp
        {
            public double cost { get; set; }
            public fuel(double cost)
            {
                Name = "fuel";
                cost = cost;
            }
            public override double monthlypay()
            { return cost; }
        }
        class parking : exp
        {
            public double cost { get; set; }
            public parking(double cost)
            {
                Name = "park fee";
                cost = cost;
            }
            public override double monthlypay()
            { return cost; }
        }
        class maintenance : exp
        {
            public double cost { get; set; }
            public maintenance(double cost)
            {
                Name = "Maintenance";
                cost = cost;
            }
            public override double monthlypay()
            { return cost; }
        }
        abstract class vehicleloan : exp
        {
            public double purchasePrice { get; set; }
            public double deposit { get; set; }
            public double interestRate { get; set; }
            public int MonthsToRepay { get; set; }
        }


        static void Main(string[] args)
        {
            Console.WriteLine("AUTOTRADER DEALERSHIP");
            Console.ReadLine();

            Console.WriteLine("Please provide your details below to determine your elagibility for motor vihicle ");
            Console.ReadLine();
            Console.WriteLine("Determining your Minimum pay Required");

        


            Console.WriteLine("how much do you earn monthly?? ");

     

           int[] Exp = new int[5];
           Console.WriteLine("Fuel spend:");
           Exp[0] = int.Parse(Console.ReadLine());
           Console.WriteLine(Exp[0]);
           Console.WriteLine("Maintenance cost:");
           Exp[4] = int.Parse(Console.ReadLine());
           Console.WriteLine(Exp[4]);
           Console.WriteLine("Insurance premium:");
           Exp[1] = int.Parse(Console.ReadLine());
           Console.WriteLine(Exp[1]);
           Console.WriteLine("Hire cost:");
           Exp[2] = int.Parse(Console.ReadLine());
           Console.WriteLine(Exp[2]);
           Console.WriteLine("Parking fee:");
           Exp[3] = int.Parse(Console.ReadLine());
           Console.WriteLine(Exp[3]);
           int total = Exp[0] + Exp[1] + Exp[2] + Exp[3] + Exp[4];
           Console.WriteLine("Your calculated expenditure sits at: ");
           Console.WriteLine(total);

           //this is how we conv 'int' to 'double'/ada datatype


           Console.ReadLine();
           Console.WriteLine("How much do you earn monthly?");
            double GROSSsalary = double.Parse(Console.ReadLine());
            Console.ReadLine();
            double taxed = GROSSsalary * 0.14;
            Console.WriteLine("Monthly tax is calculated at: ");
            Console.WriteLine(taxed);
            Console.ReadLine();
            Console.WriteLine("Amoun after tax: ");
            double NetIncome = GROSSsalary - taxed;


            Console.WriteLine("To what value is the vehicle want?LOAN AMOUNT REQUIRED");
           int Pricetag = int.Parse(Console.ReadLine());
           Console.ReadLine();
           Console.WriteLine("Deposit you'd like to take out:");
           int deposit = int.Parse(Console.ReadLine());
           Console.WriteLine("deposit you wanna take out: ");
           Console.WriteLine(deposit);
           Console.WriteLine("Repayment period:");
           int LoanPeriodMonths = int.Parse(Console.ReadLine());
           Console.WriteLine("Loan repayment time: ");

           int postDeposite = Pricetag - deposit;
           Console.WriteLine("car price after Downpayment is made=");
           Console.WriteLine(postDeposite);

           int Installment = postDeposite / LoanPeriodMonths;
           Console.WriteLine("Your repaymet amount without interest is:");
           Console.WriteLine(Installment);
           Console.ReadLine();
         
            Console.WriteLine("Your repaymet amount with interest is:");
            double Installment_With_Interest = Installment / (14/100);
            Console.WriteLine(Installment_With_Interest);
            Console.ReadLine();


            double  GROSS = GROSSsalary * 12;
            Console.WriteLine("Annual GROSS salary is: ");
           Console.WriteLine(GROSS);
           if (postDeposite >= (GROSS / 3))
           {
               Console.WriteLine("Bank approval Unlikely!");
           }
           else
           {
               if (postDeposite <= (GROSS / 3))
               {
                   Console.WriteLine("APPROVAL GURANTEED!!!");
               }
           }

                                         
           Console.ReadLine();


        }
    }
}
