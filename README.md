# Simple-Dice-Game
This code consist of a main file that has one class. It is a simple dice roller that rolls five random dice out of seven options.
## The Main File
```
public class NewJavaLab4 {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        Random rand = new Random();
        
        Die[] dice = new Die[7];
        dice[0] = new Die("d4", 4);
        dice[1] = new Die("d6", 6);
        dice[2] = new Die("d8", 8);
        dice[3] = new Die("d10", 10);
        dice[4] = new Die("d12", 12);
        dice[5] = new Die("d20", 20);
        dice[6] = new Die("d100", 100);
        
        for (int i = 0; i < 5; i++){
            int x = rand.nextInt(dice.length);
            System.out.print(dice[x]);
        }
   }
```
This code makes a total of seven new dice into an array called Die.
The first part of the dice is the name of the dice (Example being "d4").
The second part is the amount of sides that each dice has ranging from four to one-hundred.
The for loop is then choosing five dice randomly and printing out which dice is rolled followed by the number that was rolled.

## The Die Class
```
public class Die {
    private final String dice; //Which dice is chosen
    private final int sides; //The sides on that dice
    
    public Die(String d, int s){
        dice = d;
        sides = s;
    }
    
    public int roll(){
        Random rand = new Random();
        int value = sides;
        
        value = (rand.nextInt(value + 1));
        
        return value;

    }
    
    public int getFaceValue(){
        int facevalue = sides;
        return facevalue;
    }
    
    public int getNumFace(){
        int numface = sides;
        return numface;
    }
    
    public String toString(){
        return (dice + " = " + roll() + ", ");
    } 
}
```
This class sets the Die Array up. It then rolls the dice based on how many sides the dice has.
It also has a toString() method that formats the System.out.print used in the main file.
