📘 Problem
You are given an integer n, which represents the height of a staircase. Print a right-aligned staircase using the # symbol, where each level has one more # than the previous one.

The staircase should be:

Right-aligned

Height and base equal to n

📥 Input
A single integer n – the total number of stairs (1 ≤ n ≤ 100).

📤 Output
A staircase of height n, printed using # and spaces.

📌 Example
Input:
text
Copy
Edit
n = 4
Output:
text
Copy
Edit
   #
  ##
 ###
####
✅ Approach (Simple English)
I use two loops:

The first loop prints the required spaces before the #.

The second loop prints the # symbols.

For each row:

The number of spaces = n - row number

The number of # = row number

💻 Java Code
java
Copy
Edit
public static void staircase(int n) {
    int j = n;

    for (int inx = 1; inx <= n; inx++) {
        // Print spaces
        for (int k = 1; k < j; k++) {
            System.out.print(" ");
        }
        j--;

        // Print #
        for (int k = 1; k <= inx; k++) {
            System.out.print("#");
        }

        System.out.println(); // Move to the next line
    }
}