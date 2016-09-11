# Projects
My projects
import java.util.Random;
public class GuessingGame {

    public static void main(String[] args) throws java.io.IOException {
        System.out.println("Welcome to the guessing game!");
        System.out.println("Guess a number!");
        playGame();
    }

    public static void playGame()  throws java.io.IOException
    {
        int correctAnswer;
        Random rand = new Random();

        correctAnswer = rand.nextInt(10);
        System.out.println(correctAnswer);
        int chances = 3;
        while(chances != 0) {
            int guess = System.in.read();
            if (correctAnswer == guess) {
                System.out.println("You got it right!");
            }
            else if (correctAnswer < guess) {
                System.out.println("The correct number is lower.");
                chances--;
                guess = System.in.read();
            }
            else if (correctAnswer > guess) {

                System.out.println("The correct number is higher.");
                chances--;
                guess = System.in.read();
            }
        }
        //If chances are 0, you lose!
        if(chances == 0)
        {
            System.out.println("You lose!");
        }
    }
}
