# Punto 1

```c#
namespace Actividad1
{
    internal class Program
    {
        static void Main()
        {
            QuintoEjercicio();
        }

        static void primerEjercicio()
        {
            int[,] matriz = {
            { -1,  2, -3 },
            {  6, -8,  9 },
            { -3,  4, -5 }
            };

            Console.WriteLine("Matriz original:");
            ImprimirMatriz(matriz);

            for (int i = 0; i < matriz.GetLength(0); i++)
            {
                for (int j = 0; j < matriz.GetLength(1); j++)
                {
                    if (matriz[i, j] < 0)
                    {
                        matriz[i, j] = Math.Abs(matriz[i, j]);
                    }
                }
            }

            Console.WriteLine("\nMatriz con valores positivos:");
            ImprimirMatriz(matriz);
        }

        static void ImprimirMatriz(int[,] matriz)
        {
            for (int i = 0; i < matriz.GetLength(0); i++)
            {
                for (int j = 0; j < matriz.GetLength(1); j++)
                {
                    Console.Write(matriz[i, j] + " ");
                }
                Console.WriteLine();
            }
        }

        static void segundoEjercicio()
        {
            Console.WriteLine("Ingrese un numero n: ");
            int n = int.Parse(Console.ReadLine());

            int contador = 0;
            int numeroImp = 1;
            int suma = 0;

            do
            {
                suma += numeroImp;
                numeroImp += 2;
                contador++;
            }

            while (contador <= n);
            {
                Console.WriteLine("La suma impar es igual a:  " + suma);
            }
        }

        static void TercerEjercicio()
        {
            Console.WriteLine("Escriba una palabra");

            string palabraOg = Console.ReadLine();

            Console.WriteLine(palabraOg);
            string palabraReves = new string(palabraOg.Reverse().ToArray());
            Console.WriteLine(palabraReves);

            if (palabraOg == palabraReves)
            {
                Console.WriteLine("La palabra es palindroma");
            }
            else { Console.WriteLine("La palabra no es palindroma"); }
        }

        static void CuartoEjercicio()
        {
            Console.WriteLine("Escribe un numero de 8 digitos");
            double numeroOg = double.Parse(Console.ReadLine());
            string numero8dig = new string(numeroOg.ToString());

            int suma = 0;
            string numero;
            int resultado = 0;
            if (numero8dig.Length > 8)
            {
                Console.WriteLine("El numero tiene mas de 8 digitos " + "t");

                Console.WriteLine("Escribe de nuevo un numero de 8 digitos");
                numeroOg = double.Parse(Console.ReadLine());
            }
            else
            {
                foreach (char c in numero8dig)
                {

                    suma += int.Parse(c.ToString());
                }
                numero = suma.ToString();
                foreach (char c in numero)
                {
                    resultado += int.Parse(c.ToString());
                }
                Console.WriteLine("El resultado de la operacion es: " + resultado);
            }
        }
        static void QuintoEjercicio()
        {
            int[,] matriz = {
            { 1, 2, 3 },
            { 4, 5, 6 }
            };

            Console.WriteLine("Matriz original:");
            ImprimirMatriz(matriz);

            int[,] transpuesta = Transponer(matriz);

            Console.WriteLine("\nMatriz transpuesta:");
            ImprimirMatriz2(transpuesta);

        }
        static int[,] Transponer(int[,] matriz)
        {
            int filas = matriz.GetLength(0);
            int columnas = matriz.GetLength(1);
            int[,] transpuesta = new int[columnas, filas];

            for (int i = 0; i < filas; i++)
            {
                for (int j = 0; j < columnas; j++)
                {
                    transpuesta[j, i] = matriz[i, j];
                }
            }

            return transpuesta;
        }
        static void ImprimirMatriz2(int[,] matriz)
        {
            int filas = matriz.GetLength(0);
            int columnas = matriz.GetLength(1);

            for (int i = 0; i < filas; i++)
            {
                for (int j = 0; j < columnas; j++)
                {
                    Console.Write(matriz[i, j] + "\t");
                }
                Console.WriteLine();
            }
        }
    }
}
```

# Punto 2
## Actividad: “¡Soy una Función!”
### ⏱ Minuto 1: Introducción rápida
Digo:
> “En programación, usamos funciones para no repetir código. Una función es como una receta: cuando la llamo, sé exactamente qué va a hacer.”

Ejemplo breve:
> “Por ejemplo, una función puede ser ‘saludar(nombre)’. Si digo saludar(‘Juan’), responde ‘Hola Juan’.”

### ⏱ Minuto 2: Juego de simulación
Digo:
> “Vamos a hacer un juego: yo soy el programa principal, y ustedes son funciones. Cada uno tiene una tarea específica.”

Asigno 3 o 4 funciones a distintos estudiantes o equipos:
- saludar(): dice "Hola, ¿cómo estás?"
- sumar(): suma 2 + 3 y dice el resultado
- repetir(): dice una frase dos veces
- despedir(): dice "Adiós, hasta luego"

Yo como narrador:
- “Llamo a la función saludar()” → el estudiante actúa
- “Ahora llamo a la función sumar()”
Y así sucesivamente...

### ⏱ Minuto 3: Cierre rápido
Pregunta al grupo:
- “¿Qué ventaja tiene usar funciones?”
- (Guía hacia respuestas como: reutilización, orden, claridad)

Concluye con una frase como:
> “Así como ustedes actuaron tareas específicas cuando los llamé, así trabajan las funciones en un programa: se activan solo cuando las necesitamos.”

# Punto 3
1. Your first challenge is to print "hello world" on the terminal in a single command.
```Bash
echo "Hello World"
```
2. Print the current working directory
```Bash
pwd  
```
3. List names of all the files in the current directory, one file per line.
```Bash
ls -1 
```
4. There is a file named access.log in the current directory. Print the contents.
```Bash 
cat access.log 
```
5. Print the last 5 lines of "access.log".
```Bash
tail -n5 access.log
```
6. Create an empty file named take-the-command-challenge in the current working directory.
```Bash
touch take-the-command-challenge
```
7. Create a directory named tmp/files in the current working directory
```Bash
mkdir -p tmp/files
```
8. Copy the file named take-the-command-challenge to the directory tmp/files
```Bash
cp take-the-command-challenge tmp/files 
```
9. Move the file named take-the-command-challenge to the directory tmp/files
```Bash
mv take-the-command-challenge tmp/files 
```
10. A symbolic link is a type of file that is a reference to another file.

    Create a symbolic link named take-the-command-challenge that points to the file tmp/files/take-the-command-challenge.
```Bash
ln -s tmp/files/take-the-command-challenge take-the-command-challenge 
```
11. Delete all of the files in this challenge directory including all subdirectories and their contents.
```Bash
rm -r * .*  
```
12. There are files in this challenge with different file extensions. Remove all files with the .doc extension recursively in the current working directory.
```Bash
find . -name "*.doc" -delete
```
13. There is a file named access.log in the current working directory. Print all lines in this file that contains the string "GET".
```Bash
grep GET access.log
```
14. Print all files in the current directory, one per line (not the path, just the filename) that contain the string "500".
```Bash
grep -l 500 *
```
15. Print the relative file paths, one path per line for all filenames that start with "access.log" in the current directory.
```Bash
find . -name "access.log*"
```
16. Print all matching lines (without the filename or the file path) in all files under the current directory that start with "access.log" that contain the string "500".

    Note that there are no files named access.log in the current directory, you will need to search recursively.
```Bash
grep -r -h "500" --include "access.log*"
```
# Punto 4

1. Función sin parámetros y sin retorno
```c#
Static void Saludar()
{
    Console.WriteLine("¡Hola mundo!");
}

// Invocación
Saludar();
```

2. Función sin parámetros, con retorno
```C#
Static int ObtenerNumeroAleatorio()
{
    return new Random()
}

// Invocación
int numero = ObtenerNumeroAleatorio();
Console.WriteLine(numero);
```


3. Función con parámetros y sin retorno
```C#
Static void ImprimirMensaje(string mensaje)
{
    Console.WriteLine(mensaje);
}

// Invocación
ImprimirMensaje("Bienvenido a C#");
```
4. Función con parámetros y con retorno
```C#
Static double CalcularPromedio(double a, double b)
{
    return (a + b) / 2;
}

// Invocación
double promedio = CalcularPromedio(7.5, 8.0);
Console.WriteLine(promedio);
```
5. Función que recibe un arreglo
```C#
Static int SumarElementos(int[] numeros)
{
    int suma = 0;
    foreach (int n in numeros)
        suma += n;
    return suma;
}

// Invocación
int[] arreglo = { 1, 2, 3, 4 };
int total = SumarElementos(arreglo);
Console.WriteLine(total);
```

6. Función que devuelve una cadena construida
```C#
Static string CrearSaludo(string nombre)
{
    return “Hola” + nombre;
}

// Invocación
string saludo = CrearSaludo("Simón");
Console.WriteLine(saludo);
```
7. Función que trabaja con matrices (2D)
```C#
Static int[,] Transponer(int[,] matriz)
{
    int filas = matriz.GetLength(0);
    int columnas = matriz.GetLength(1);
    int[,] resultado = new int[columnas, filas];

    for (int i = 0; i < filas; i++)
        for (int j = 0; j < columnas; j++)
            resultado[j, i] = matriz[i, j];

    return resultado;
}

// Invocación
int[,] original = { { 1, 2 }, { 3, 4 } };
int[,] transpuesta = Transponer(original);
```
8. Función que recibe y devuelve un objeto de clase
```C#
class Persona
{
    public string Nombre;
    public int Edad;
}

Static Persona CumplirAños(Persona p)
{
    p.Edad += 1;
    return p;
}

// Invocación
Persona persona = new Persona { Nombre = "Alex", Edad = 20 };
Persona actualizada = CumplirAños(persona);
Console.WriteLine(actualizada.Edad);
```
9. Función con parámetros opcionales
```C#
Static void MostrarTitulo(string texto = "Sin título")
{
    Console.WriteLine(texto);
}

// Invocaciones
MostrarTitulo("Menú Principal");
```
10. Función que usa una lista genérica
```C#
Static void AgregarElemento(List<string> lista, string nuevo)
{
    lista.Add(nuevo);
}

// Invocación
List<string> nombres = new List<string> { "Ana", "Luis" };
AgregarElemento(nombres, "Carlos");
Console.WriteLine(nombres);
```
11. funcion que verifique si un numero es par
```C#
bool EsPar(int numero)
{
    return numero % 2 == 0;
}

Console.WriteLine(EsPar(4));
```
12. funcion que verifique si un numero es impar
```C#
bool EsImpar(int numero)
{
    return numero % 2 != 0;
}

Console.WriteLine(EsImpar(5));
``` 
13. funcion que devuelva los numeros desde n hasta m
```C#
int[] NumerosDesdeHasta(int n, int m)
{
    int[] resultado = new int[m - n + 1];
    for (int i = 0; i < resultado.Length; i++)
    {
        resultado[i] = n + i;
    }
    return resultado;
}

int[] numeros = NumerosDesdeHasta(3, 7);
```
14. funcion que devuelva el numero de vocales en una cadena
```C#
int ContarVocales(string cadena)
{
    int contador = 0;
    foreach (char c in cadena.ToLower())
    {
        if ("aeiou".Contains(c))
        {
            contador++;
        }
    }
    return contador;
}

int cantidad = ContarVocales("Hola Mundo");
```
15. funcion que añada un punto al final de una cadena
```C#
string AgregarPuntoFinal(string cadena)
{
    return cadena.EndsWith(".") ? cadena : cadena + ".";
}

string resultado = AgregarPuntoFinal("Hola mundo");
```
16. funcion que haga un barrel roll
```C#

```

17. funcion que regrese el menor de 2 numeros
```C#
int MenorDeDos(int a, int b)
{
    return a < b ? a : b;
}

int resultado = MenorDeDos(5, 8);
```
18. funcion que devuelva reciba un radio y devuelva el area de un circulo
```C#
double AreaCirculo(double radio)
{
    return Math.PI * radio * radio;
}

double resultado = AreaCirculo(3);

```
19. funcion que espere 5 segundos
```C#
void EsperarCincoSegundos()
{
    System.Threading.Thread.Sleep(5000);
}

EsperarCincoSegundos();

```
20. funcion que genere una contraseña
```C#
string GenerarContrasena(int longitud)
{
    string caracteres = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
    Random rand = new Random();
    char[] contrasena = new char[longitud];
    for (int i = 0; i < longitud; i++)
    {
        contrasena[i] = caracteres[rand.Next(caracteres.Length)];
    }
    return new string(contrasena);
}

string resultado = GenerarContrasena(10);
```
