# Container With Most Water

## Step 1: Understanding how we calculate the water between two lines

Imagine we pick any two lines from the array. The amount of water they can hold depends on two things:

1. The distance between them (**the width**).
2. The height of the **shorter** line (because if we pour more water, it will just spill over the shorter side!).

So, the formula for the water area is:

> **Area = width × height of the shorter line**

### Why do we use the shorter line?

Imagine you have two walls holding water between them.

- One wall is **3 feet** tall.
- The other wall is **8 feet** tall.

If you start pouring water between them, what's the maximum height the water can reach before it starts spilling over?

Exactly, it can only go up to **3 feet** (the shorter wall). If you go any higher, it just leaks out the side.

So, the height of our water container is always limited by the **shorter wall**.

To find the total amount of water (the area), we just multiply that height by the distance (width) between the two walls.

> **Area = width × height of the shorter wall**

---

## Now that we have the formula down...

Let's look at how we can find the best pair of lines **without checking every single combination**.

Let's start with the **widest possible container**.

We can place:

- One pointer at the very beginning (**left**).
- One pointer at the very end (**right**).

This gives us the **maximum possible width**.

We calculate the water area for this pair and save it as our starting **maximum water**.

Now, to see if we can find a container that holds even more water, we have to shrink the width by moving one of our pointers inward (either **left moves right**, or **right moves left**).

To get a larger area with a smaller width, we need a taller height.

**Which pointer do you think we should move inward to try and find a taller line?**

---

Actually, it **does matter!** Let's think about why.

Remember, our water height is limited by the **shorter line**.

### If we move the taller line inward:

- The width gets smaller.
- The height of our container is still limited by that same short line (or an even shorter one).

Since both width and height either shrunk or stayed the same, the total water will **definitely be less**.

### But if we move the shorter line inward:

- Yes, the width gets smaller.
- But we **might find a much taller line** that makes up for the lost width and gives us more water!

So, we should **always move the pointer pointing to the shorter line.**

**Does this logic make sense? If so, we can move on to the next step and start building the algorithm.**

---

# Building the Algorithm

Awesome! Let's turn this logic into a step-by-step plan. 🚀

## Step 1: Initialize our pointers and max water tracker

We start by placing:

- A **left** pointer at the very beginning of the array (index `0`).
- A **right** pointer at the very end of the array (last index).
- A variable **max_water** set to `0` to keep track of the best container we've found so far.

**Ready to see how we loop through the array in the next step?**

---

## Step 2: Loop and calculate the water

We want to calculate the water capacity at each step **as long as our pointers haven't met yet** (`left < right`).

At each step, we do a quick calculation:

- **Width:** The distance between the pointers, which is `right - left`.
- **Height:** The shorter of the two lines, so `min(height[left], height[right])`.
- **Current Water:** `width × height`.
- **Update Max:** If this `current_water` is bigger than our `max_water`, we save it as our new maximum.

**Does this calculation step make sense to you? If so, we can move to the final step where we actually move the pointers.**

---

## Step 3: Moving the pointers

Now, how do we decide which pointer to move inward?

Since the amount of water is always limited by the **shorter line**, keeping the shorter line will never help us get a larger area as the width decreases.

So, we want to **discard the shorter line** and try to find a taller one.

- If `height[left]` is smaller than `height[right]`, we move the left pointer to the right:

  ```python
  left += 1
  ```

- Otherwise, we move the right pointer to the left:

  ```python
  right -= 1
  ```

We repeat this until the pointers meet, and then we simply return the `max_water` we found.

**Does this pointer-moving logic make sense? If you're ready, we can try putting it all together into code!**
