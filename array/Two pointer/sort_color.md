Here are the comprehensive notes on the video **"Sort Colors | Brute Force to Dutch National Flag Algorithm (Optimal O(N))"** by RisingBrain:

---

# 📌 Notes: Sort Colors (LeetCode #75)

**Video Link:** [Sort Colors Tutorial](https://youtu.be/E-txNhS9TnI?si=WgTJSW9TkCepyHgP)

---

## 1. Problem Statement [[00:50](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D50)]

* **Task:** Given an array `nums` containing `n` objects colored Red (`0`), White (`1`), and Blue (`2`), sort them **in-place** so that elements of the same color are adjacent in the order `0`, `1`, `2`.
* **Constraints:**
* Cannot use inbuilt library sorting functions [[01:22](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D82)].
* Target: Single-pass algorithm with **$O(1)$** constant extra space [[08:31](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D511)].



---

## 2. Approach 1: Counting / Brute Force (Two-Pass) [[02:40](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D160)]

### **Logic:**

1. **First Pass:** Iterate through the array once to count the frequency of `0`s (`count0`), `1`s (`count1`), and `2`s (`count2`) [[03:08](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D188)].
2. **Second Pass:** Overwrite the array sequentially:
* Fill `count0` zeros [[04:46](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D286)].
* Fill `count1` ones [[07:06](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D426)].
* Fill `count2` twos [[07:34](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D454)].



### **Complexity:**

* **Time Complexity:** $O(N) + O(N) = O(2N) \approx O(N)$ [[08:15](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D495)]
* **Space Complexity:** $O(1)$ constant space.
* **Limitation:** Requires **two passes** through the array.

---

## 3. Approach 2: Dutch National Flag (DNF) Algorithm (Optimal) [[09:12](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D552)]

The **Dutch National Flag Algorithm** solves the problem in a **single pass** using three pointers [[10:45](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D645)].

### **Pointers & Invariants:**

Initialize 3 pointers:

* `low = 0`
* `mid = 0`
* `high = n - 1`

Throughout execution, the array is partitioned into four zones [[11:15](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D675)]:

| Index Range | Contains |
| --- | --- |
| `0` to `low - 1` | All `0`s |
| `low` to `mid - 1` | All `1`s |
| `mid` to `high` | **Unsorted elements** |
| `high + 1` to `n - 1` | All `2`s |

---

### **Algorithm Rules (`while (mid <= high)`) [[13:00](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D780)]:**

1. **If `nums[mid] == 0` [[16:00](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D960)]:**
* Swap `nums[low]` and `nums[mid]`.
* Increment both: `low++` and `mid++`.


2. **If `nums[mid] == 1` [[15:18](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D918)]:**
* Leave it in place and increment: `mid++`.


3. **If `nums[mid] == 2` [[19:20](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D1160)]:**
* Swap `nums[mid]` and `nums[high]`.
* Decrement: `high--`.
* *Note:* Do **not** increment `mid` here because the element swapped into `mid` from `high` hasn't been evaluated yet.



---

## 4. Code Implementation


When presenting this in an interview, readability, clear variable names, and structured comments matter just as much as optimal code.

Here is the exact code structure and communication strategy to use in a technical interview:

```python
class Solution:
    def sortColors(self, nums: list[int]) -> None:
        """
        Sorts an array containing 0s, 1s, and 2s in-place in a single pass.
        Uses the Dutch National Flag (DNF) Algorithm.
        
        Time Complexity: O(N) - Single pass through the array.
        Space Complexity: O(1) - Constant auxiliary space.
        """
        low, mid, high = 0, 0, len(nums) - 1

        # Process the unsorted region [mid ... high]
        while mid <= high:
            if nums[mid] == 0:
                # Place 0 at the low region
                nums[low], nums[mid] = nums[mid], nums[low]
                low += 1
                mid += 1
                
            elif nums[mid] == 1:
                # 1 is already in the middle region
                mid += 1
                
            else:  # nums[mid] == 2
                # Place 2 at the high region
                nums[mid], nums[high] = nums[high], nums[mid]
                high -= 1

```

---

### How to Explain This to Your Interviewer

When writing this code, state your **invariants** aloud to demonstrate deep algorithmic understanding:

1. **State the visual boundaries:**
> *"I'll divide the array into four conceptual regions using three pointers:*
> * `[0 ... low - 1]` contains all `0`s
> * `[low ... mid - 1]` contains all `1`s
> * `[mid ... high]` is the **unsorted zone**
> * `[high + 1 ... n - 1]` contains all `2`s"*
> 
> 


2. **Explain the key edge case (Why `mid` doesn't increment when `nums[mid] == 2`):**
> *"When `nums[mid] == 2`, I swap it with `nums[high]` and decrement `high`. I do **not** increment `mid` here because the element swapped from `high` into `mid` hasn't been evaluated yet. It could be `0`, `1`, or `2`, so we need to process it on the next loop iteration."*

---

## 5. Complexity Analysis [[23:28](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D1408)]

* **Time Complexity:** **$O(N)$** — Processed in a single pass as `mid` and `high` converge [[24:20](https://www.google.com/search?q=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DE-txNhS9TnI%26t%3D1460)].
* **Space Complexity:** **$O(1)$** — In-place array operations with no additional memory allocation.

---
