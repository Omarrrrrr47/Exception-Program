# Working with Exceptions: Try/catch.
The program is suppose to work like this the user enter number or (array index in this case). Then they enter a name to store in the index they first entered(in the array they take slots 0-5, so i subtracted 1 number each time the user inputs). I  need to then create exceptions in case the user inputs a number smaller than 1 or bigger then 6. Also i need to create an exception that doesn't let a user input his name into an array slot that has already been entered. to finish it needs to be a do-while loop that won't end until all six slots are taken. Please help, i've been working on this for a while, and i just can't seem to get it right. 





package edu.orangecoastcollege.cs170.oquinones1;

import java.lang.ArrayIndexOutOfBoundsException;
import java.util.Scanner;

public class AppointmentScheduler {

	public static void main(String[] args) {
		Scanner consoleScanner = new Scanner(System.in);
		int time = 0;
		String appName = "";
		boolean invalidTimes =false;
		String[] name = new String[6];

		do {
			System.out.println("Enter an appointment time between 1 & 6 ");
			try {
				time = consoleScanner.nextInt();
				invalidTimes = (time >= 7 || time <= 0);
				if (invalidTimes) {
					System.out.print("This time doesn't exist. You can come, but we will be close.");
					System.out.println("");
				}
				System.out.print("Enter a name");

				name[time-1] = consoleScanner.next();
			} catch (ArrayIndexOutOfBoundsException ex) {

				System.out.print("Error: Enter numbers between 1 and 6");

			}
		} while (name[time] != "");
	}

}
