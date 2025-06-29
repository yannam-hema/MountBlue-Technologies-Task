📘 Problem
Maria plays basketball and wants to track how many times she breaks her season high score or season low score. The score from the first game is considered both the initial high and low record. From there, she compares each new game score:

If the new score is higher than the current high, it breaks the max record.

If the new score is lower than the current low, it breaks the min record.

📥 Input
A list of integers: scores, where each element is the score from one game.

📤 Output
A list of two integers:

First: how many times she broke her highest score

Second: how many times she broke her lowest score

📌 Example
Input:
text
Copy
Edit
scores = [12, 24, 10, 24]
Output:
text
Copy
Edit
[1, 1]
Explanation:
Starts with 12 → no record broken

24 is higher → max record broken (count = 1)

10 is lower → min record broken (count = 1)

24 is not higher or lower → no change

✅ Approach (Simple English)
Assume the first score is both the max and min.

Loop through the rest of the scores:

If score is greater than max, update max and count it.

If score is less than min, update min and count it.

Return the counts as a list [max_count, min_count].

💻 Java Code
java
Copy
Edit
public static List<Integer> breakingRecords(List<Integer> scores) {
    int maximum_record = scores.get(0);
    int minimum_record = scores.get(0);
    int max_record_break_count = 0;
    int min_record_break_count = 0;

    for (int i : scores) {
        if (i > maximum_record) {
            max_record_break_count++;
            maximum_record = i;
        }
        if (i < minimum_record) {
            min_record_break_count++;
            minimum_record = i;
        }
    }

    List<Integer> record_results = new ArrayList<>();
    record_results.add(max_record_break_count);
    record_results.add(min_record_break_count);

    return record_results;
}