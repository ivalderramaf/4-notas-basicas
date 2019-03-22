metodo shell
c#
int n = 0;
            Console.WriteLine("Ingrese el tamaño del vector");
            n = int.Parse(Console.ReadLine());

            int[] Vector = new int[n];
            /// Asiganar vlores aleatoreos al vector;
            Random r = new Random();

            for (int a = 0; a < Vector.Length; a++)
            {
                Vector[a] = r.Next(1, Vector.Length * Vector.Length);
                Console.Write("[" + Vector[a] + "]");
            }
            Console.WriteLine("");
            //Metodo de ordenacion SHELL
            int intervalo = Vector.Length / 2, i, j, k;
            while (intervalo > 0)
            {
                for (i = intervalo; i < Vector.Length; i++)
                {
                    j = i - intervalo;
                    while (j >= 0)
                    {
                        k = j + intervalo;
                        if (Vector[j] <= Vector[k])
                            j = -1;
                        else
                        {
                            int temp;
                            temp = Vector[j];
                            Vector[j] = Vector[k];
                            Vector[k] = temp;
                            j -= intervalo;


                        }
                    }
                }
                intervalo = intervalo / 2;
            }
            Console.WriteLine("Lista ordenada");
            for (int a = 0; a < Vector.Length; a++)
            {

                Console.Write("[" + Vector[a] + "]");
            }
            Console.WriteLine();
            //Metodo busqueda binaria
            Console.WriteLine("Ingrese el dato que desea buscar: ");
            int buscar;
            buscar = int.Parse(Console.ReadLine());
            int Li, Ls, Centro = 0, recorrido = 0;
            for (int a = 0; a < Vector.Length; a++)
            {

                if (Vector[a] != 0)
                {
                    recorrido++;
                }
            }
            Ls = recorrido;
            Li = 0;
            bool Interruptor = false;
            while ((Interruptor == false) && (Li <= Ls))
            {
                Centro = (Li + Ls) / 2;

                if (buscar == Vector[Centro])
                {
                    Interruptor = true;

                }
                else
                {
                    if (buscar > Vector[Centro])
                    {

                        Li = Centro + 1;


                    }
                    else
                    {
                        Ls = Centro - 1;

                    }

                }

            }
            //break;
            if (Interruptor == true)
            {
                Centro = Centro + 1;
                Console.WriteLine("El Nombre se encuentra en la posicion [" + Centro + "]");
            }
            else
            {
                Console.WriteLine("El Nombre NO SE ENCUENTRA");
            }
            Console.ReadKey();
        }
    }
}
