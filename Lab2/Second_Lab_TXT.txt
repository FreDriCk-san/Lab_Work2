package com.company;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
	// write your code here
        System.out.println("Enter your space: ");
        Scanner input = new Scanner(System.in);
        int n = input.nextInt();
        int[] mass = new int[n];
        for (int i = 0; i < mass.length; i++)
        {
            mass[i] = input.nextInt();
        }
        int min = mass[0], max = mass[0];
        int sum = 0, average = 0, delta, median = 0;
        double multip = 1.0;
        for (int i = 0; i < mass.length; i++)
        {
            if (mass[i] < min)
            {
                min = mass[i];
            }
            if (mass[i] > max)
            {
                max = mass[i];
            }

            sum += mass[i];
            average = sum / n;
            delta = average / n;

            if (mass[i] < median)
            {
                median -= delta;
            }
            else
            {
                median += delta;
            }

            multip *= mass[i];

        }

        System.out.println(multip);
        System.out.println(Math.sqrt(multip));
        System.out.println("Min value is: " + min);
        System.out.println("Max value is: " + max);
        System.out.println("Average value is: " + average);
        System.out.println("Median value is: " + median);
        System.out.printf("Geometrical value is: %f \n", Math.pow(Math.sqrt(multip), n));
    }
}
