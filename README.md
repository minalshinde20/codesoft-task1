# codesoft-task1

import java.util.Random;

import java.util.Scanner;

public class GN {
    public static void main(String args[]) {
        char res;
        int x;

        int c = 0;
        do {

            call();
            Scanner sc = new Scanner(System.in);
            System.out.println("Do you want to quit? Y/N");
            res = sc.next().charAt(0);
            c += 1;
        } while (res == 'y' || res == 'Y');

        // System.out.println("Number of round attempted = " + c);
        if (c == 1) {
            System.out.println("Score is 100");
        } else if (c > 1 && c <= 3) {
            System.out.println("Score is 70");
        } else {
            System.out.println("Score is 50");
        }

    }

    static void call() {
        int guess;
        int i;

        for (i = 0; i < 7; i++) {
            Scanner sc = new Scanner(System.in);
            System.out.println("Guess a number between 1 and 100: ");
            guess = sc.nextInt();

            // create random object
            Random ran = new Random();

            // get number between 0-99
            int num = ran.nextInt(100);

            System.out.println("Random number between 0 and 100: " + num);

            if (guess == num) {
                System.out.println(" Guessed Correctly");
                break;
            } else if ((num - guess) > 0) {
                System.out.println("guessed two low ");

            } else if ((num - guess) < 0) {
                System.out.println(" Guessed is two high");

            }

        }
        System.out.println("Number of attempt till the correct answer is = " + (i + 1));

    }
}
