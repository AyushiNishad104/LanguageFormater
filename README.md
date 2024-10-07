# LanguageFormater
A simple Java program that formats numbers and currency based on user-preferred language.
import java.text.NumberFormat;
import java.util.Locale;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Ask the user for their preferred language
        System.out.println("Choose your preferred language:");
        System.out.println("1. English");
        System.out.println("2. French");
        System.out.println("3. Italy");
        System.out.print("Enter the number corresponding to your choice: ");
        int choice = scanner.nextInt();

        Locale locale;

        // Set the locale based on user choice
        switch (choice) {
            case 1:
                locale = Locale.ENGLISH; // English
                break;
            case 2:
                locale = Locale.FRENCH; // French
                break;
            case 3:
                locale = Locale.ITALY; // Italy
                break;
            default:
                System.out.println("Invalid choice, defaulting to English.");
                locale = Locale.ENGLISH;
        }

        // Ask user for a number
        System.out.print("Enter a number to format: ");
        double number = scanner.nextDouble();

        // Format number based on the chosen locale
        NumberFormat numberFormat = NumberFormat.getInstance(locale);
        String formattedNumber = numberFormat.format(number);

        // Format currency based on the chosen locale
        NumberFormat currencyFormat = NumberFormat.getCurrencyInstance(locale);
        String formattedCurrency = currencyFormat.format(number);

        // Display the results
        System.out.println("Formatted Number: " + formattedNumber);
        System.out.println("Formatted Currency: " + formattedCurrency);

        // Close the scanner
        scanner.close();
    }
}


