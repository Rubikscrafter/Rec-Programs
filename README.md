# Bases
import java.util.Scanner;

public class Bases2 {
  public static void main (String [] args) {
    Scanner keyboard = new Scanner(System.in);
   
    System.out.println("Enter a base followed by the number in said base.");
    int num = keyboard.nextInt();
    
    System.out.println("Enter a base that the number will be converted into.");
    int base = keyboard.nextInt();
    
    String bin = " ";
    String let = " ";
    int number = num;
    int space = num.indexOf(" ");
    int b = num.substring(0, space);
    
    
    
    if (base<10) { // Displays binary if the base is less than 10
      while (num != 0) {
        bin = (String.valueOf(num%base) + bin );
        num = num/base;
      }
      
      System.out.println("The number "+ number +" in base "+base+" is");
      System.out.println(bin);
      
    } else if (base>10) { // Displays binary if the base is greater than 10, includes letters
      while (num != 0) {
        if (num%base>=10) {
          if (num%base==10)
            let = "A";
          else if (num%base==11)
            let = "B";
          else if (num%base==12)
            let = "C";
          else if (num%base==13)
            let = "D";
          else if (num%base==14)
            let = "E";
          else if (num%base==15)
            let = "F";
          bin = let + bin;
          num = num/base;
        } else if (num%base<=10){
          bin = (String.valueOf(num%base) + bin);
          num = num/base;
        }
      }
      
      System.out.println("The number "+ number +" in base "+base+" is");
      System.out.println(bin);
      
    } else if (base == 10) { // Displays binary if the base is 10, which is the same as the original value
      System.out.println("The number "+ number +" in base "+base+" is");
      System.out.println(number);
    }  
  }
}

