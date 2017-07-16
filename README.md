# Вторая задача 
---
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    namespace VLAD.TEST._2._2
    {
    class SquareEquation
    {
    private
    double a, b, c, d, root1,root2;
    public SquareEquation(double A, double B, double C)
    {
    this.a = A;
    this.b = B;
    this.c = C;
    discr();
    calcRoots();
    }
    private void error() {
    Console.WriteLine("Ошибка");
    Environment.Exit(1);
    }
    private bool check()
    {
    if (d < 0)
    {
    error();
    }
    else if (d == 0)
    {
    return true;
    }
    return false;
    }
    private void calcRoots()
    {
    if (check())
    this.root1 = -b / (2 * a);
    else
    this.root1 = (-b + Math.Sqrt(d)) / (2 * a);
    this.root2 = (-b - Math.Sqrt(d)) / (2 * a);
    }
    public void message()
    {
    if (check())
    Console.WriteLine("Корень: " + root1);
    else
    Console.WriteLine(" Корень 1: " + root1 +"\n корень 2: "+root2);
    }
    private void discr()
    {
    this.d= Math.Pow(b, 2) - 4 * a * c;
    }
    static void Main(string[] args)
    {
    Console.WriteLine("Введите коэф. квадратного ур-я A ");
    double A = double.Parse(Console.ReadLine());
    Console.WriteLine("Введите коэф. квадратного ур-я B ");
    double B = double.Parse(Console.ReadLine());
    Console.WriteLine("Введите коэф. квадратного ур-я C ");
    double C = double.Parse(Console.ReadLine());
    SquareEquation seq = new SquareEquation(A, B, C);
    seq.message();
    string key = Console.ReadLine();
    }
    }
    }
