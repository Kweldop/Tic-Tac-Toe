import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.Random;
import java.util.Scanner;

public class TicTacToe2 {
	static ArrayList<Integer>playerPosition=new ArrayList<>();
	static ArrayList<Integer>cpuPosition=new ArrayList<>();
	private static int i;

	public static void main(String[] args) {
		
		char[] [] gameBoard= {{' ','|',' ','|',' '},
				              {'-','+','-','+','-'},
				              {' ','|',' ','|',' '},
				              {'-','+','-','+','-'},
				              {' ','|',' ','|',' '}};
		Scanner scanner=new Scanner(System.in);
		Random random=new Random();		
	   	printGameBoard(gameBoard);
		for(int j=0;j<=0;) {
			System.out.print("Player enter your position:");
			int playerPos =scanner.nextInt();
			while(playerPosition.contains(playerPos)||cpuPosition.contains(playerPos)) {
				System.out.println("Position is already aquired! enter different position");
				playerPos=scanner.nextInt();
			}
			System.out.println("Your position is "+playerPos);
			placePosition(gameBoard, playerPos,"Player");
			int cpuPos=random.nextInt(9)+1;
			while(playerPosition.contains(cpuPos)||cpuPosition.contains(cpuPos)) {
				System.out.println("Position is already aquired! enter different position");
				 cpuPos=random.nextInt(9)+1;
			}
			placePosition(gameBoard,cpuPos,"CPU");
			String winner=checkWinner();
			System.out.println(winner);
			if(i==1) {
				j=i;
			}
		}
		scanner.close();
	}
/*--------------------------------------------------------------------------------------------------------------------------------------*/
	
	private static char[][] placePosition(char[][] gameBoard, int position,String user) {
		char symbol = ' ';
		if(user.equals("Player") ) {
			 symbol='X';
			 playerPosition.add(position);
		}if(user.equals("CPU")) {
			symbol='O';
			cpuPosition.add(position);
		}
		switch(position){
		case 1: gameBoard[0][0]=symbol;break;
		case 2: gameBoard[0][2]=symbol;break;
		case 3: gameBoard[0][4]=symbol;break;
		case 4: gameBoard[2][0]=symbol;break;
		case 5: gameBoard[2][2]=symbol;break;
		case 6: gameBoard[2][4]=symbol;break;
		case 7: gameBoard[4][0]=symbol;break;
		case 8: gameBoard[4][2]=symbol;break;
		case 9: gameBoard[4][4]=symbol;break;
		default:;break;
		} 	   	printGameBoard(gameBoard);
		return gameBoard;
	}
		private static void printGameBoard(char[][] gameBoard) {
			for(char[] row:gameBoard) {
				for(char c:row) {
					System.out.print(c);
				}
				System.out.println();
			}
	}
		public static String checkWinner() {
			List topRow=Arrays.asList(1, 2, 3);
			List middleRow=Arrays.asList(4, 5, 6);
			List bottomRow=Arrays.asList(7, 8, 9);
			List Col1=Arrays.asList(1, 4, 7);
			List Col2=Arrays.asList(2, 5, 8);
			List Col3=Arrays.asList(3, 6, 9);
			List diag1=Arrays.asList(1, 5, 9);
			List diag2=Arrays.asList(7, 5, 3);
			
			List<List>winning=new ArrayList<>();
			
			winning.add(topRow);
			winning.add(middleRow);
		    winning.add(bottomRow);
			winning.add(Col1);
			winning.add(Col2);
			winning.add(Col3);
			winning.add(diag1);
			winning.add(diag2);
			
			for(List l: winning) {
				if(playerPosition.containsAll(l)) { 
					i=1;
					return "Player has won!!!";
				}else if(cpuPosition.containsAll(l)) {
					i=1;
					return "CPU has won!!!";
				}else if(playerPosition.size()+cpuPosition.size()==9){
					i=1;
					return"Draw!!!";
				} 
			}
				return "";
		}
}
