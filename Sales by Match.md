🧦 Problem
We are given a pile of socks. Each sock has a color represented by an integer. The goal is to count how many pairs of socks with the same color exist in the pile.

📥 Input
n: the total number of socks

ar[]: a list of integers where each integer is a sock's color

📤 Output
An integer that represents the number of matching pairs.

📌 Example
Input:
ini
Copy
Edit
n = 7  
ar = [1, 2, 1, 2, 1, 3, 2]
Output:
Copy
Edit
2
Explanation:
Pairs: (1,1), (2,2)

One sock of color 1, one of color 3, and one of color 2 are left.

So, 2 pairs total.

✅ Approach (Simple English)
I used a HashMap to count how many socks there are for each color.

For each color, I counted how many full pairs can be made using:
count / 2

I added up all those pairs and returned the total.

This way, I don’t need to check every combination — just count and divide.

💻 Java Code
java
Copy
Edit
public static int sockMerchant(int n, List<Integer> ar) {
    HashMap<Integer, Integer> mp = new HashMap<>();
    
    // Count frequency of each sock color
    for (int i = 0; i < n; i++) {
        mp.put(ar.get(i), mp.getOrDefault(ar.get(i), 0) + 1);
    }

    int pairs = 0;
    
    // Count total pairs by dividing each frequency by 2
    for (int count : mp.values()) {
        pairs += count / 2;
    }

    return pairs;
}