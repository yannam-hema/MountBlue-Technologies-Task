📘 Problem
You are given an array of integers. Use the partition logic of QuickSort to rearrange the array:

Select the first element as the pivot.

All elements less than the pivot go to the left list.

All elements equal to the pivot go to the middle list.

All elements greater than the pivot go to the right list.

Return a new list with elements ordered as:
left + equal + right (no full sorting needed).

📥 Input
A list of integers: arr

📤 Output
A new list where all elements are arranged using the QuickSort partition logic

📌 Example
Input:
text
Copy
Edit
arr = [4, 5, 3, 7, 2]
Output:
text
Copy
Edit
[3, 2, 4, 5, 7]
Explanation:
Pivot = 4

Elements < 4 → [3, 2]

Elements = 4 → [4]

Elements > 4 → [5, 7]

Result = [3, 2, 4, 5, 7]

✅ Approach (Simple English)
I chose the first number in the list as the pivot.

I created three lists:

One for numbers less than the pivot.

One for numbers equal to the pivot.

One for numbers greater than the pivot.

Then, I added all elements from left + equal + right into one list.

That’s the output.

This is not full QuickSort recursion — just the partition logic for one step.

💻 Java Code
java
Copy
Edit
public static List<Integer> quickSort(List<Integer> arr) {
    List<Integer> left = new ArrayList<>();
    List<Integer> equal = new ArrayList<>();
    List<Integer> right = new ArrayList<>();

    int pivot = arr.get(0);

    for (int i : arr) {
        if (i > pivot) {
            right.add(i);
        } else if (i < pivot) {
            left.add(i);
        } else {
            equal.add(i);
        }
    }

    List<Integer> sorted = new ArrayList<>();
    sorted.addAll(left);
    sorted.addAll(equal);
    sorted.addAll(right);

    return sorted;
}