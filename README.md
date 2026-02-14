import java.util.Scanner;
public class Calculator_Task1 {
	public static void main(String[] args) {
		Scanner scanner=new Scanner(System.in);
		boolean running=true;
		System.out.println("====Java Console Calculator====");
		
		while(running) {
			System.out.println("\nSelect an operation:");
			System.out.println("1. Add");
			System.out.println("2. Subtract");
			System.out.println("3. Multiply");
			System.out.println("4. Divide");
			System.out.println("5. Exit");
			System.out.println("Choice:");
			
			int choice=getIntInput(scanner);
			
			if(choice==5){
				running=false;
				System.out.println("Goodbye!!");
				break;
			}
			
			if(choice<1|| choice>5) {
				System.out.println("Invalid Choice. Please pick 1-5.");
				continue;
			}
			
			System.out.print("Enter first number:");
			double num1=getDoubleInput(scanner);
			
			System.out.print("Enter second number:");
			double num2=getDoubleInput(scanner);
			
			switch(choice) {
			case 1: add(num1, num2);
			break;
			
			case 2: subtract(num1,num2);
			break;
			
			case 3: multiple(num1,num2);
			break;
			
			case 4: divide(num1,num2);
			break;
			}
		}
		scanner.close();
	}

	private static void add(double a, double b) {
		System.out.printf("Result: %.2f + %.2f = %.2f\n",a,b,(a+b));
	}
	
	private static void subtract(double a, double b) {
		System.out.printf("Result: %.2f-%.2f = %.2f\n",a,b,(a-b));
	}
	
	private static void multiple(double a,double b) {
		System.out.printf("Result: %.2f * %.2f = %.2f\n",a,b,(a*b));
	}
	
	private static void divide(double a, double b) {
		if(b==0) {
			System.out.println("Error : Cannot divide by zero!");
		}else {
			System.out.printf("Result:%.2f/ %.2f = %.2f\n",a,b,(a/b));
		}
	}
	
	private static int getIntInput(Scanner scanner) {
		while(!scanner.hasNextInt()) {
			System.out.print("Please enter a valid number:");
			scanner.next();
		}
		return scanner.nextInt();
	}
	
	private static double getDoubleInput(Scanner scanner) {
		while(!scanner.hasNextDouble()) {
			System.out.print("Please enter a valid number:");
		}
		return scanner.nextDouble();
	}
	}

	


