import java.util.Scanner;

public class HaikyuQuizGame {
    public static void main(String[] args) {
        System.out.println("Welcome to the Haikyu quiz game!");
        System.out.println("Choose the letter of the correct answer only." + "\n");

        String[] questions = {
            "Who is known as the 'Little Giant' in Haikyu!!?",
            "Which team does Tobio Kageyama play for?",
            "What is the position of Shoyo Hinata in Karasuno High School volleyball team?",
            "Who is the captain of Aoba Johsai High School volleyball team?",
            "Which player is known for his 'Rolling Thunder' move in Haikyu!!"
        };

        String[] options = {
            "A. Tobio Kageyama  B. Shoyo Hinata  C. Kei Tsukishima  D. Yu Nishinoya",
            "A. Karasuno High School  B. Aoba Johsai High School  C. Nekoma High School  D. Fukurodani Academy",
            "A. Setter  B. Libero  C. Wing Spiker  D. Middle Blocker",
            "A. Tobio Kageyama  B. Kei Tsukishima  C. Toru Oikawa  D. Hajime Iwaizumi",
            "A. Tobio Kageyama  B. Shoyo Hinata  C. Kei Tsukishima  D. Tetsuro Kuroo"
        };

        String[] answers = {"A", "B", "A", "C", "D"};

        Scanner scanner = new Scanner(System.in);
        int score = 0;

        for (int i = 0; i < questions.length; i++) {
            System.out.println("Question " + (i + 1) + ": " + questions[i]);
            System.out.println(options[i]);
            //A do-while loop to validate the user's input. The loop continues until the user enters a letter from A to D.
            String userAnswer;
            do {
                System.out.print("Your answer: ");
                userAnswer = scanner.next().toUpperCase();
                if (!userAnswer.matches("[A-D]")) {
                    System.out.println("Invalid input. Please enter A, B, C, or D.");
                }
            } while (!userAnswer.matches("[A-D]"));

            if (userAnswer.equals(answers[i])) {
                System.out.println("    Correct!\n");
                score++;
            } else {
                System.out.println("    Incorrect. The correct answer is: " + answers[i] + "\n");
            }
        }

        System.out.println("Quiz completed! Your final score is: " + score + "/" + questions.length);
        scanner.close();
    }
}