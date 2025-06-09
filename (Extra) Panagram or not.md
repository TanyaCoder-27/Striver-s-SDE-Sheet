# Panagram or not

## Implementing a Pangram Checker, which verifies whether a given string contains all 26 letters of the alphabet at least once. Let’s break down the logic and establish a strong memorization technique.

### 🔹 Explanation & Logic
A Pangram is a sentence that contains every letter from ‘a’ to ‘z’ at least once.
### 🚀 Step-by-Step Execution
1️⃣ Convert the string to lowercase (s1.toLowerCase())
- This ensures case insensitivity, meaning ‘A’ and ‘a’ are treated the same.
2️⃣ Convert the string to a character array (toCharArray())
- This makes it easier to iterate over each character efficiently.
3️⃣ Create a visited boolean array of size 26 (boolean[] visited)
- Each index represents a letter (visited[0] → ‘a’, visited[25] → ‘z’).
- Initially, all values are false.
4️⃣ Mark encountered letters (visited[ch_arr[i] - 'a'] = true)
- If a character is between ‘a’ and ‘z’, mark its presence in the visited array.
5️⃣ Check if all letters exist (if visited[i] == false return false)
- If any letter is missing, return false (not a pangram).
- If all are marked true, return true (pangram detected).

### 🧠 Memorization Trick
Use "Normalize → Mark → Verify" to remember the flow!
🔹 Normalize (toLowerCase()) → Convert everything to lowercase.
🔹 Mark (visited[ch_arr[i] - 'a'] = true) → Track encountered letters.
🔹 Verify (if visited[i] == false return false) → Ensure all are present.
💡 Think of it as an Attendance Sheet for Alphabets!
- Step 1: Lowercase the text → Just like standardizing student names.
- Step 2: Mark letters as "present" in visited[] → Like ticking names in attendance.
- Step 3: Check if all students attended → If anyone’s absent (false), return false.

### 📌 Why This Works?
✅ Single-pass O(n) traversal → Efficient character checking.
✅ Minimal space O(1) → Uses only a fixed 26-element boolean array.
✅ Handles edge cases efficiently (empty string, partial alphabets).

```
// User function template for JAVA

class Solution {
    // Function to check if a string is Pangram or not.
    public static boolean checkPangram(String s) {
        // your code here
        String s1 = s.toLowerCase();
        char[] ch_arr = s1.toCharArray();
        boolean[] visited = new boolean[26];
        for(int i=0;i<ch_arr.length;i++){
            if(ch_arr[i] >='a' && ch_arr[i]<='z'){
                visited[ch_arr[i] - 'a'] = true;
            }
        }
        
        for(int i=0;i<visited.length;i++){
            if(visited[i] == false){
                return false;
            }
        }
        
        return true;
    }
}


```

OR

```
import java.util.*;

class Pangram {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter a String:");
        String s = sc.nextLine();
        sc.close(); 
        
        boolean res = checkPangram(s);
        System.out.println(s + (res ? " is a pangram" : " is not a pangram"));
    }

    public static boolean checkPangram(String s) {
        s = s.toLowerCase();
        Set<Character> set = new HashSet<>(); 
        
        for (char ch : s.toCharArray()) {
            if (ch >= 'a' && ch <= 'z') {
                set.add(ch);
            }
        }
        
        return set.size() == 26; 
    }
}




```

Enter a String:
The quick brown fox jumps over the lazy dog
The quick brown fox jumps over the lazy dog is a panagram
