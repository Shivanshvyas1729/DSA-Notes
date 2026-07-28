# LeetCode 42: Trapping Rain Water — Study Notes

---

# 1. Problem Overview & Core Intuition

Given `n` non-negative integers representing an elevation map where the width of each bar is `1`, compute how much water it can trap after raining.

## Fundamental Rule

Water sits on top of any block at index `i` only if there are taller boundaries to both its left and its right.

The water level is constrained by the **shorter** of the tallest boundaries on either side.

\[
\text{Water Level}(i) = \min(\text{left\_max}_i,\ \text{right\_max}_i)
\]

\[
\text{Trapped Water}(i)=\max(0,\ \text{Water Level}(i)-\text{height}[i])
\]

### Why "Anywhere" Works

The left/right tall boundaries do **not** need to be adjacent to index `i`.

Taller peaks farther away act as the outer containment walls for the entire valley between them.

---

# 2. Visual Conceptual Diagrams

## Concept 1: Valley Held by Distant Peaks

Even if there are smaller hills inside a valley, water pools up to the level dictated by the tall outer mountains.

```text
Height

  4 |                   █  <-- Peak Right (4)
  3 | █ ~~~~~~~~~~~~~~~ █  <-- Water Level = min(3,4)=3
  2 | █       █         █
  1 | █       █         █  <-- Current index (height = 0)
  0 | █   .   █   .     █
----+---------------------
Idx:  0   1   2   3   4
```

---

## Concept 2: Standing on a High Peak

If the current block is taller than the surrounding water level, water runs off both sides.

```text
  5 |         █            <-- High Peak (5)
  2 | █       █       █
  0 | █   .   █   .   █
----+-------------------
Idx:  0   1   2   3   4
```

Water:

\[
\max(0,\min(2,2)-5)=0
\]

---

# 3. Two-Pointer Solution

## Why Two Pointers?

- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---

## Algorithm

### Initialization

```text
left  = 0
right = n - 1

left_max  = height[left]
right_max = height[right]

total_water = 0
```

---

### While `left < right`

Compare the two boundary heights.

### Case 1

If

```text
left_max < right_max
```

then the **left side** is guaranteed to be the limiting wall.

Steps:

1. Move left pointer

```text
left += 1
```

2. Update left maximum

```text
left_max = max(left_max, height[left])
```

3. Water trapped

```text
total_water += left_max - height[left]
```

---

### Case 2

Otherwise,

```text
right_max <= left_max
```

the **right side** is guaranteed to be the limiting wall.

Steps:

1. Move right pointer

```text
right -= 1
```

2. Update right maximum

```text
right_max = max(right_max, height[right])
```

3. Water trapped

```text
total_water += right_max - height[right]
```

---

Return

```text
total_water
```

---

# 4. Step-by-Step Execution

## Input

```python
height = [3, 0, 2, 0, 4]
```

---

## Step 1 — Initial Setup

Pointers

```text
L = 0 (3)
R = 4 (4)

left_max = 3
right_max = 4

water = 0
```

```text
Height

  4 |                              +---+ (4)
  3 | +---+ (3)                    |   |
  2 | |   |              +---+ (2) |   |
  1 | |   |              |   |     |   |
  0 | +---+----+---+-----+---+---+-+---+

Index:  0    1    2    3    4
        L                   R
```

Since

```text
left_max < right_max
```

move the left pointer.

---

## Step 2 — Process Index 1

Pointers

```text
L = 1
R = 4
```

Update

```text
left_max = max(3,0)=3
```

Water

```text
3 - 0 = 3
```

Total

```text
0 + 3 = 3
```

```text
Height

  4 |                              +---+ (4)
  3 | +---+ (3)                    |   |
  2 | |   |  ~~~~~       +---+ (2) |   |
  1 | |   |  ~~~~~       |   |     |   |
  0 | +---+--+---+-------+---+---+-+---+

Index:  0      1      2      3      4
               L                    R
```

---

## Step 3 — Process Index 2

Pointers

```text
L = 2
R = 4
```

Update

```text
left_max = max(3,2)=3
```

Water

```text
3 - 2 = 1
```

Total

```text
3 + 1 = 4
```

```text
Height

  4 |                              +---+ (4)
  3 | +---+ (3)                    |   |
  2 | |   |  ~~~~~       +---+ (2) |   |
  1 | |   |  ~~~~~  ~~~  |   |     |   |
  0 | +---+--+---+--+---+--+---+---+---+

Index:  0      1      2      3      4
                      L             R
```

---

## Step 4 — Process Index 3

Pointers

```text
L = 3
R = 4
```

Update

```text
left_max = max(3,0)=3
```

Water

```text
3 - 0 = 3
```

Total

```text
4 + 3 = 7
```

```text
Height

  4 |                              +---+ (4)
  3 | +---+ (3)                    |   |
  2 | |   |  ~~~~~       +---+ (2) |   |
  1 | |   |  ~~~~~  ~~~  |   |  ~~~~~  |
  0 | +---+--+---+--+---+--+---+--+----+---+

Index:  0      1      2      3      4
                             L      R
```

Next move:

```text
L == R
```

Loop ends.

Final answer:

```text
7 units
```

---

# 5. Edge Cases

| Edge Case | Example | Output | Reason |
|-----------|---------|--------|--------|
| Length < 3 | `[]`, `[5]`, `[3,2]` | `0` | Need at least 3 bars |
| Increasing | `[1,2,3,4]` | `0` | No valley |
| Decreasing | `[4,3,2,1]` | `0` | Water slides off |
| Flat | `[3,3,3,3]` | `0` | Water level equals height |
| Single Peak | `[1,2,5,2,1]` | `0` | Peak blocks accumulation |

---

# 6. Python Implementation

```python
def trap(height: list[int]) -> int:
    """
    Calculates total trapped rain water using the Two-Pointer approach.

    Time Complexity: O(N)
    Space Complexity: O(1)
    """

    # Edge case
    if not height or len(height) < 3:
        return 0

    left, right = 0, len(height) - 1

    left_max = height[left]
    right_max = height[right]

    total_water = 0

    while left < right:

        if left_max < right_max:
            left += 1
            left_max = max(left_max, height[left])
            total_water += left_max - height[left]

        else:
            right -= 1
            right_max = max(right_max, height[right])
            total_water += right_max - height[right]

    return total_water


if __name__ == "__main__":
    test_map = [3, 0, 2, 0, 4]
    print(trap(test_map))   # Expected: 7
```

---

# Complexity Analysis

| Metric | Value |
|---------|-------|
| Time | **O(N)** |
| Space | **O(1)** |

---

# Key Takeaways

- Water at each index depends on the **minimum** of the tallest walls on both sides.
- Outer distant walls are sufficient to trap water.
- The shorter boundary always determines the maximum possible water level.
- The two-pointer solution avoids extra arrays while maintaining linear time.
- Each pointer moves at most once across the array, giving an **O(N)** algorithm with **O(1)** extra space.
