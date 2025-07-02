📘 Problem
Alice and Bob each have a list of 3 scores for different challenges. You need to compare the scores for each challenge and award points:

If Alice's score is higher, she gets 1 point.

If Bob's score is higher, he gets 1 point.

If the scores are equal, no points are awarded.

📥 Input
Two lists of 3 integers each:

a: Alice’s scores

b: Bob’s scores

📤 Output
A list with 2 integers:

First is Alice’s total score

Second is Bob’s total score

📌 Example
Input:
text
Copy
Edit
a = [5, 6, 7]
b = [3, 6, 10]
Output:
text
Copy
Edit
[1, 1]
Explanation:
5 > 3 → Alice gets 1 point

6 = 6 → no points

7 < 10 → Bob gets 1 point

So the result is [1, 1].

✅ Approach (Simple English)
I used two variables, one for Alice's score and one for Bob's score.

I loop through the lists, comparing the elements at each index:

If Alice’s score is higher → increase her count.

If Bob’s score is higher → increase his count.

At the end, I return both scores in a list.

💻 Java Code
java
Copy
Edit
public static List<Integer> compareTriplets(List<Integer> a, List<Integer> b) {
    ArrayList<Integer> scores = new ArrayList<>();
    int alice = 0;
    int bob = 0;

    for (int i = 0; i < a.size(); i++) {
        if (a.get(i) > b.get(i)) {
            alice++;
        } else if (a.get(i) < b.get(i)) {
            bob++;
        }
    }

    scores.add(alice);
    scores.add(bob);

    return scores;
}