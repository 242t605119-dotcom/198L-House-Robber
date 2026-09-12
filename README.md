# LeetCode 198 - House Robber

## Problem

You are a professional robber planning to rob houses along a street.

Each house contains a certain amount of money. However, adjacent houses have security systems connected to each other. If two adjacent houses are robbed on the same night, the police will be alerted.

Find the maximum amount of money that can be robbed without robbing two adjacent houses.

## Approach

This problem can be solved using **Dynamic Programming**.

For every house, there are two choices:

1. Skip the current house and keep the maximum money obtained so far.
2. Rob the current house and add its money to the maximum amount obtained before the previous house.

We keep only two previous values instead of using a complete DP array.

- `prev2` → maximum money before the previous house.
- `prev1` → maximum money up to the previous house.
- `current` → maximum money after considering the current house.

The formula is:

```text
current = max(prev1, prev2 + money)
