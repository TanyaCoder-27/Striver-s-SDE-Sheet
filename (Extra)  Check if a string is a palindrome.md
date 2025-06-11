```
//check if a string is palindrome

import java.util.*;
class StringPalindrome{
	public static void main(String args[]){
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter string:");
		String str = sc.nextLine();
		boolean res = checkPal(str);
		if(res)
			System.out.println("String Palindrome");
		else
			System.out.println("Not String Palindrome");

	}

	private static boolean checkPal(String s){
		
		int l =0 , r = s.length()-1;
		String s1 = s.toLowerCase();
		char[] car = s1.toCharArray();
		while(l<r){
			if(car[l] != car[r])
				return false;
			l++;
			r--;


		}
		return true;

	}



}

```

```
E:\JAVA FULLSTACK INTERNSHIP\Collections JAVA>java -cp . StringPalindrome
Enter string:
Madam
String Palindrome

E:\JAVA FULLSTACK INTERNSHIP\Collections JAVA>java -cp . StringPalindrome
Enter string:
Papa
Not String Palindrome

```
