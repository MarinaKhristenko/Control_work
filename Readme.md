# Описание решения задачи

## Создание метода *string[] GetArrayStringConsole*

создаем метод для разделения строки из консоли в массив по знаку “,”

```sh 
string[] GetArrayStringConsole (string inConsolSimvol)
{
    string[] arraySimvol = new string[inConsolSimvol.Length];
    arraySimvol = inConsolSimvol.Split(",");
    return arraySimvol;
}
```
## Создание метода *string[] GetArrayThreeSimvol*

создаем метод сортирующий символы из массива. сначала отсчитываем количество, удовлетворяющих требований, для определения длинны нового массива. создаем массив по выясненому количествуи заносим туда символы удовлетворяющие требованиям.

```sh
string[] GetArrayThreeSimvol (string[] array)
{
    int count = 0;
    for (int i = 0; i < array.Length; i++)
    {
        string simvol = array[i];
        if (simvol.Length <= 3)
        {
            count++;
        }
    }
    string[] arrayThreeSimvol = new string[count];
    for (int i = 0, j = 0; i < array.Length; i++)
    {
        string simvol = array[i];
        if (simvol.Length <= 3)
        {
            arrayThreeSimvol[j] = simvol;
            j++;
        }
    }
    return arrayThreeSimvol;
}
```
## Создание метода *void Print*

создаем метод для вывода информации из массивов с использованием цеклического вывода каждого элемента массива.

```sh
void Print (string[] array)
{
    for (int i = 0; i < array.Length; i++)
    {
        Console.Write($"{array[i]}, ");
    }
    Console.WriteLine();
}
```
## Создаем **"клентский код"** для вызова методов и обработки информации через консоль.
Выводим поясняющую информационную строку для пользователя в консоле: *"Введите набор символов через знак (,) - ""Введите набор символов через знак (,) - "*

Присваиваем введенное в консоле от пользователя символы *string inStringSimvol = console.ReadLine()*

Присваиваем массиву преобразованную строку через метод *string[] arraySimvol = GetArrayStringConsole(inStringSimvol)*

*Console.WriteLine(); 
Console.Write("Введенные символы - "); 
Print(GetArrayStringConsole(inStringSimvol)); 
Console.WriteLine(); 
Console.Write("Введенные символы длинной меньше либо равны 3 - "); Print(GetArrayThreeSimvol(arraySimvol)); 
Console.WriteLine();*

```sh
Console.Write("Введите набор символов через знак (,) - ");
string inStringSimvol = Console.ReadLine();
string[] arraySimvol = GetArrayStringConsole(inStringSimvol);
Console.WriteLine();
Console.Write("Введенные символы - ");
Print(GetArrayStringConsole(inStringSimvol));
Console.WriteLine();
Console.Write("Введенные символы длинной меньше либо равны 3 - ");
Print(GetArrayThreeSimvol(arraySimvol));
Console.WriteLine();
```