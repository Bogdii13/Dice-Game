# Dice-Game
Dice Game
import java.util.Random;
import java.util.Scanner;

public class JocZaruri {
    public static void main(String[] args) {

        int zar1;
        int zar2;
        int zar1Adversar;
        int zar2Adversar;

        int victoriileMele = 0;
        int victoriileAdversar = 0;

        Scanner cititor = new Scanner(System.in);
        Scanner cititorText = new Scanner(System.in);
        Random generator = new Random();

        while (true) {
            System.out.println("Doriti sa jucati? Scorul meu " + victoriileMele + "/ Scorul adversarului " + victoriileAdversar);
            String raspuns = cititorText.nextLine();
            if (raspuns.equalsIgnoreCase("da")) {
                zar1 = generator.nextInt(6) + 1;
                zar2 = generator.nextInt(6) + 1;
                zar1Adversar = generator.nextInt(6) + 1;
                zar2Adversar = generator.nextInt(6) + 1;

                System.out.println("Ai dat " + zar1 + " " + zar2);
                System.out.println("Oponentul a dat " + zar1Adversar + " " + zar2Adversar);

                int scorulMeu = zar1 + zar2;
                int scorulAdversar = zar1Adversar + zar2Adversar;

                if (scorulMeu > scorulAdversar) {
                    victoriileMele++;
                    System.out.println("Am castigat runda");
                } else if (scorulAdversar > scorulMeu) {
                    victoriileAdversar++;
                    System.out.println("Am pierdut runda");
                } else {
                    System.out.println("REMIZA");
                }

                if (victoriileMele==6){
                    System.out.println("Ai castigat jocul");
                    break;
                }else if (victoriileAdversar==6){
                    System.out.println("Am pierdut jocul");
                    break;
                }

            } else if (raspuns.equalsIgnoreCase("nu")) {
                System.out.println("PACAT");
                break;
            } else {
                System.out.println("nu ai introdus un raspuns valabil");
            }
        }
    }
}
