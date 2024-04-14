namespace ConsoleApp45
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int qtdePequenos, qtdeGrandes ;
            double KmCaninoFeliz = 2, KmVaiRex = 1.7, KmChow = 0.8, totalCaninoFeliz, totalVaiRex, TotalChow, menor = double.MaxValue, distancia = double.MaxValue;
            string data, maior = "";
            bool isFinalDeSemana;

            Console.WriteLine("data: (dd/MM/aaaa)");
            data = Console.ReadLine();
            Console.WriteLine("Quantidade de caes pequenos:");
            qtdePequenos = int.Parse(Console.ReadLine());
            Console.WriteLine("Quantidade de caes grandes:");
            qtdeGrandes = int.Parse(Console.ReadLine());

            DateTime dt = DateTime.ParseExact(data, "dd/MM/yyyy", null);
            isFinalDeSemana = (dt.DayOfWeek == DayOfWeek.Saturday || dt.DayOfWeek == DayOfWeek.Sunday);

            if (isFinalDeSemana)
            {
                totalCaninoFeliz = (qtdePequenos * 24.00) + (qtdeGrandes * 48.00);
            }
            else
            {
                totalCaninoFeliz = (qtdePequenos * 20.00) + (qtdeGrandes * 40.00);
            }
          
            if (isFinalDeSemana)
            {
                totalVaiRex = (qtdePequenos * 20.00) + (qtdeGrandes * 55.00);
            }
            else
            {
                totalVaiRex = (qtdePequenos * 15.00) + (qtdeGrandes * 50.00);
            }

            TotalChow = (qtdePequenos * 30) + (qtdeGrandes * 45);

            if (totalCaninoFeliz < menor || (totalCaninoFeliz == menor && KmCaninoFeliz < distancia))
            {
                maior = "Meu Canino Feliz";
                menor = totalCaninoFeliz;
                distancia = KmCaninoFeliz;
            }
        
            if (totalVaiRex < menor || (totalVaiRex == menor && KmVaiRex < distancia))
            {
                maior = "Vai Rex";
                menor = totalVaiRex;
                distancia = KmVaiRex;
            }

            if (TotalChow < menor || (TotalChow == menor && KmChow < distancia))
            {
                maior = "ChowChawgas";
                menor = TotalChow;
                distancia = KmChow;
            }


            Console.WriteLine("Petshop ideal:" + maior);
            Console.WriteLine("Preço total dos banhos em R$:" + menor);
            Console.ReadLine();
        }
    }
}


*Projeto em C#
