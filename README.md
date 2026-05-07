# tharwat
task

using System;
using System.Linq;

class Program
{
    static void Main()
    {
        double[] data = {
            115, 182, 191, 31, 196, 1099, 5, 172, 10, 179,
            83, 21, 20, 21, 186, 177, 195, 193, 188, 199,
            62, 109, 105, 183, 110
        };

        Array.Sort(data);

        int n = data.Length;

        // Mean
        double mean = data.Average();

        // Median
        double median = data[n / 2];

        // Mode
        var mode = data.GroupBy(x => x)
                       .OrderByDescending(g => g.Count())
                       .First().Key;

        // Variance
        double variance = data.Sum(x => Math.Pow(x - mean, 2)) / n;

        // Standard Deviation
        double stdDev = Math.Sqrt(variance);

        // Range
        double range = data.Max() - data.Min();

        // Quartiles
        double q2 = median;
        double q1 = data[n / 4];
        double q3 = data[(3 * n) / 4];

        // IQR
        double iqr = q3 - q1;

        Console.WriteLine("Mean = " + mean);
        Console.WriteLine("Median = " + median);
        Console.WriteLine("Mode = " + mode);
        Console.WriteLine("Variance = " + variance);
        Console.WriteLine("Standard Deviation = " + stdDev);
        Console.WriteLine("Range = " + range);
        Console.WriteLine("Q1 = " + q1);
        Console.WriteLine("Q2 = " + q2);
        Console.WriteLine("Q3 = " + q3);
        Console.WriteLine("IQR = " + iqr);
    }
}
