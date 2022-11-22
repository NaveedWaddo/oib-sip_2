package oasis;

import java.util.Scanner;

public class GuessNumber {
        public static void main(String[] args){
        	Scanner input=new Scanner(System.in);
    		System.out.println("\t\t\t\t+-------------------------------+");
    		System.out.println("\t\t\t\t|  WELCOME TO Guess Gmae TASK-2 | ");
    		System.out.println("\t\t\t\t+-------------------------------+");
    		while(true) {
    			System.out.println();
    			System.out.println("+------+");
				System.out.println("| Menu |");
				System.out.println("+------+");
    			System.out.println("1.New Round\n2.Exit\n");
        		System.out.print("Enter choice: ");
        		int choice=input.nextInt();
        		if(choice==1) {
        			GenrateNumber obj=new GenrateNumber();
        			int chances=5;
        			int randomNumber=obj.getNumber();
        			System.out.println("\n!!!Game Started!!!");
        			System.out.println("Remember-->You have 5 chances to guess a number");
        			while(true) {
        				if(chances==0) {
        					System.out.println("!Sorry! You don't have enough chances better luck next time!");
        					break;
        				}else {
        					System.out.println("!!Number of chances left to guess: "+chances);
        					System.out.print("\nGuess a number: ");
        					int userNumber=input.nextInt();
        					if(randomNumber>userNumber){
                                if(randomNumber-userNumber>15){
                                    System.out.println("!Hint!-->Try for more bigger number");
                                    chances--;
                                }
                                else if(randomNumber - userNumber > 7 && randomNumber - userNumber < 15){
                                    System.out.println("!Hint!-->Entered number difference is between 7 and 15, try for a bigger one");
                                    chances--;
                                }
                                else {
                                    System.out.println("!Hint!-->You are too closer, try for bigger number");
                                    chances--;
                                }
                            }else if(randomNumber==userNumber) {
                            	System.out.println("\n!!Congratulations you guess the correct number!!");
                            	System.out.println("Your Score is "+chances+"/5");
                            	break;
                            }
        					else{
                                if(userNumber-randomNumber>15){
                                    System.out.println("!Hint!-->Try for more smaller number");
                                    chances--;
                                }
                                else if(userNumber - randomNumber > 7 && userNumber - randomNumber < 15){
                                    System.out.println("!Hint!-->Entered number difference is between 7 and 15, Try for smaller number");
                                    chances--;
                                }
                                else{
                                    System.out.println("!Hint!-->You are too closer, try for smaller number");
                                    chances--;
                                }
                            }
        				}
        			}
        			
        		}else {
        			System.out.println("\nThank you----Visit again----- :)");
        			System.exit(0);
        		}
    		}

        }

    }

class GenrateNumber{
	 public int getNumber() {
		 double r=Math.random()*100;
	      int x=(int)r;
	      System.out.println("Random number is: " + x);
	      return x;
	 }
}
