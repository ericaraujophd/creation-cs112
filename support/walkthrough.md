---
title: "Suggested In-Class Walkthrough"
subtitle: "Support Materials for Instructors"
date: 2025-10-28
---

This recommended walkthrough can be used to introduce the assignment. It takes about 30-45 minutes, depending on class discussion.

## Step 1: Warm-Up Analysis (10 min)

Use **bubble sort** as an example (familiar to all students).

**Show the code:**

```cpp
void bubble_sort(int arr[], int n) {
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                int temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
    }
}
```

**Ask:**

- What is this algorithm doing?
- How many comparisons and swaps does it make in the worst case for an array of size n? ($n^2$)
- Where is it doing unnecessary work?

**Point out the inefficiency:** Even if the array is already sorted after the first pass, bubble sort keeps comparing. It doesn't recognize the pattern that the data is ordered.

## Step 2: Introduce the Theological Frame (8 min)

Say something like:

> "From a Christian perspective, we believe God created the universe with wisdom and order. God's designs are elegant—they don't waste effort or resources. Think about photosynthesis, water cycles, or how your body processes oxygen. These are all remarkably efficient.
>
> When we design algorithms, we're participating in a kind of discovery. We're asking: 'What is the structure of this problem? What pattern can I align my solution with?' An efficient algorithm respects that structure. An inefficient algorithm fights against it, doing unnecessary work.
>
> More than that, we're called to be stewards. Stewardship isn't just about trees and soil—it's about all resources. When we waste computational resources through inefficient design, we're not being good stewards. We're being exploitative."

Pause. Let this sink in.

## Step 3: Make It Concrete (12 min)

**Ask students to calculate:**

If bubble sort runs on:

- A moderately sized dataset (n=1,000): ~1 million comparisons
- A larger dataset (n=1 million): ~1 trillion comparisons

**Each comparison uses energy.** Not much per comparison, but at scale?

- Cloud data centers use enormous amounts of electricity.
- If a company uses an inefficient sorting algorithm for a service that processes millions of queries per day, the waste adds up.
- That waste = higher operating costs passed to customers, more carbon emissions, faster device obsolescence.

**Now personalize it:**

> If you were designing the sorting function for a payment processing system that processes 100 million transactions per day, would you use bubble sort or merge sort? Why?

Students will say: "Merge sort, because it's faster."

**Follow-up:** "Right. And one reason is stewardship. It's about respecting the resources you're using and not wasting them."

## Step 4: Introduce the Assignment (5 min)

Walk through the three parts:

1. **Analyze an inefficient algorithm** - show how detailed the analysis should be
2. **Design an optimized version** - emphasize the "discovery" of pattern/structure
3. **Reflect theologically** - these are the hard questions; they require honesty
