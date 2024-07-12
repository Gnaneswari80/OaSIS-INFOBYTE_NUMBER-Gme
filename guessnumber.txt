package javaproject;
//import java.util.Scanner;
//import java.util.Random;
import java.util.*;//ecllipsecode
public class game {//class start

	public static void main(String[] args) {

		Scanner sc=new Scanner(System.in);
		Random ran=new Random();
		int choice=0;
		int score=0;
		System.out.println("Welome to NUMBER GAME");
		while(true)
		{//true while block
			System.out.println(" Choose any option!!");
			System.out.println("1.play Game      2.Total score");
			System.out.println("3.Exit");
			 
			choice=sc.nextInt();
			switch(choice)
			{
			case 1:
				     score=score+playgame();
				     break;
			case 2:totalscore(score);
			        break;
			case 3:System.exit(0);
				    break;
			default:System.out.println("Invalid option");
			
			}
			
			
		}//true while end block
	  
		

	}
	
	
	public static int playgame()
	{
		int count=0,rand=0,guess;
		int again=0;
		Scanner sc=new Scanner(System.in);
		Random ran=new Random();
		int max=100,min=1;
		rand=ran.nextInt(max-min+1)+min;
		while(count<5)
		{//while start
			
			System.out.println("Guess a number ");
			guess=sc.nextInt();
			if(rand<guess)
			{
				System.out.println(guess+" number is to High");
			}
			else if(rand>guess)
			{
				System.out.println(guess+" number is to Low ");
			}
			else
			{
				System.out.println("Congrats! You won the game!!! ");
				return(10);
			
			}
			
			
			count++;//to count attempts			
			if(count==4)
				System.out.println("You have last attempt to play... ");
			if(count==5)
			{
				System.out.println("Sorry You Lost The Game ..");						
				System.out.println("Do you want to replay these Level(press 1) or Next Level(press 0)  <-- press 1 or 0");
				 again=9;//we can take any value either 1 or 0
				 while(again!=1&&again!=0) {
				again=sc.nextInt();
				if(again!=1&&again!=0)//loop will terminate when user give 1 or 0 otherwise infinite
					System.out.println("Invalid option..please enter valid number 1 or 0");
				 }
				if(again==1)
				{
				count=0;//to replay the game
				
				}
				else if(again==0)
				return(0);//don't replay the game, options(menu) will display
				
			}
			
			
		}//while end
		return(0);
			
		
	}
	public static void totalscore(int score)
	{
		System.out.println("Your Total Score "+score);
		
	}

}//// class end
