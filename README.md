package Java;

import java.util.Scanner;

public class Reverse_String {
	
	public static void main(String[] args) {

		System.out.print("Enter the String::");
		
		Scanner sc =  new Scanner(System.in);
		String name = sc.next();//ABCD
		//String name = "ABCDE";//
		
		int leng = name.length();//4
		System.out.println("The length of string is::"+leng);//4
		
		String rev = "";//d
		for(int i=leng-1;i>=0;i--) {//i=  
			rev=rev+name.charAt(i);//dcba
			
		}
		
		
		System.out.println("Reverse of string is::"+rev);
	}
	
