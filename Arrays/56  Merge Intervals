# 🧩 Merge Intervals — Full Explanation & Documentation

---

## 🧠 Logic Overview (Your Approach)

1. Sort all intervals by their start time (`interval[0]`).
2. Traverse the sorted list while maintaining a result list (`merged`).
3. For each interval:
   - If `merged` is empty or there’s **no overlap**, add it directly.
   - If it **overlaps**, merge it by updating the end (`interval[1]`) to the `max` of both ends.

---

## ⚙️ Why a Comparator Is Used

When sorting a **2D array**, Java doesn’t know which value inside each inner array to compare.  
Hence, we pass a **Comparator object** that defines our custom comparison rule.

```java
Arrays.sort(intervals, new Comparator<int[]>() {
    public int compare(int[] a, int[] b) {
        return Integer.compare(a[0], b[0]);
    }
});
```
➡️ Here, we’re comparing a[0] and b[0], i.e., the start times of intervals.

##💡 What Comparator Is
Comparator<T> is a functional interface in java.util.

It contains one abstract method:

```java

int compare(T o1, T o2);
```
This method defines how to order two objects during sorting.
You override it to specify your own logic (like sorting by start time).

##🔍 Why compare() Works
compare() is an inbuilt abstract method of the Comparator interface.

When you override it, you’re telling Java how to compare two elements.

Arrays.sort() internally calls this overridden compare() during sorting.

✅ So, Arrays.sort() + Comparator together allow custom sorting logic for complex types (like 2D arrays).

🧱 How Comparator Is Passed
The line below passes a Comparator object to the sort method:

```java

Arrays.sort(intervals, new Comparator<int[]>() { ... });
```
This object provides the comparison logic for sorting a 2D array by its first element.

🔁 Main Loop Explanation
```java

for (int[] interval : intervals) {
    if (merged.isEmpty() || merged.get(merged.size() - 1)[1] < interval[0]) {
        // No overlap → add directly
        merged.add(interval);
    } else {
        // Overlap → merge
        merged.get(merged.size() - 1)[1] =
            Math.max(merged.get(merged.size() - 1)[1], interval[1]);
    }
}
```
🔍 Step-by-Step:
Iterate through each interval in sorted order.

If merged is empty or lastEnd < currentStart → add interval (no overlap).

Else → update last interval’s end to

```java

Math.max(lastEnd, currentEnd)
```
(merging them into one continuous interval).

## ⚡ In Short

- **Condition:** `merged.isEmpty()` or `lastEnd < currentStart`  
  - **Action:** `merged.add(interval)`  
  - **Meaning:** No overlap → add new interval  

- **Condition:** `else`  
  - **Action:** `lastEnd = Math.max(lastEnd, currentEnd)`  
  - **Meaning:** Overlap → merge intervals  

---

## 🧭 Comparator Summary (Sorting Behavior)

- **Primitive Array**
  - **Example:** `int[] arr`
  - **Works Automatically?** ✅ Yes
  - **Why:** Has built-in comparison operators (`<`, `>`)
  - **Solution:** —  

- **Built-in Objects (String, Integer)**
  - **Example:** `String[] names`
  - **Works Automatically?** ✅ Yes
  - **Why:** They implement `Comparable`
  - **Solution:** —  

- **Custom Objects (Student, Interval)**
  - **Example:** `Student[] students`
  - **Works Automatically?** ❌ No
  - **Why:** No default order defined
  - **Solution:** Implement `Comparable` or use `Comparator`

- **2D Array (int[][])**
  - **Example:** `int[][] intervals`
  - **Works Automatically?** ❌ No
  - **Why:** Array itself isn’t `Comparable`
  - **Solution:** Pass a `Comparator` manually

🧾 TL;DR
Comparator is needed when sorting objects without natural order (like arrays of arrays).

compare() is inbuilt and abstract, you just override it to define your logic.

Java then uses this logic to sort your custom data correctly before merging.
