Haha, my apologies! That was a complete hiccup on my end — I definitely don't need Google Keep or any app permissions. I'm right here in this chat and ready to give you clean, structured study notes.

Here are your summary notes for **LeetCode 11: Container With Most Water**.

---

## 📌 Problem Overview: Container With Most Water

The goal is to pick two vertical lines from an array of heights that, together with the x-axis, hold the maximum volume of water.

### 1. Key Formula

$$\text{Area} = \text{Width} \times \text{Height of Shorter Line}$$

* **Width:** The distance between the two lines ($\text{right} - \text{left}$).
* **Height:** Limited by the **shorter** line ($\min(\text{height}[\text{left}], \text{height}[\text{right}])$), because water spills over the shorter wall.

---

### 2. Why the Two-Pointer Approach Works

* **Start Wide:** Place the `left` pointer at index `0` and the `right` pointer at the last index (`len(height) - 1`) to maximize width initially.
* **The Pointer Rule:** Always move the pointer pointing to the **shorter line** inward.
* *Why?* Moving the taller line decreases the width without any chance of increasing the height (it's still bottlenecked by the short line).
* Moving the shorter line is the **only path** that gives you a chance to find a taller line that makes up for the reduced width.



---

### 3. Algorithm Steps

1. **Initialize:** `left = 0`, `right = len(height) - 1`, and `max_water = 0`.
2. **Loop:** While `left < right`:
* Calculate $\text{current\_water} = (\text{right} - \text{left}) \times \min(\text{height}[\text{left}], \text{height}[\text{right}])$.
* Update `max_water = max(max_water, current_water)`.
* If `height[left] < height[right]`, increment `left += 1`.
* Otherwise, decrement `right -= 1`.


3. **Return:** `max_water`.

---

### 4. Code Implementation

```python
def maxArea(height: list[int]) -> int:
    left, right = 0, len(height) - 1
    max_water = 0
    
    while left < right:
        # Calculate water capacity for current bounds
        width = right - left
        current_water = width * min(height[left], height[right])
        max_water = max(max_water, current_water)
        
        # Shift the bottleneck pointer inward
        if height[left] < height[right]:
            left += 1
        else:
            right -= 1
            
    return max_water

```

---

### 5. Complexity

* **Time Complexity:** $\mathcal{O}(n)$ — We pass through the array once in a single loop.
* **Space Complexity:** $\mathcal{O}(1)$ — Only extra variables for pointers and max water.
