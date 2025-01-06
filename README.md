# Inconsistent Collision Detection with hitTestObject() in ActionScript 3

This repository demonstrates a bug in ActionScript 3's `hitTestObject()` function where collision detection becomes unreliable under certain circumstances. This often happens with complex MovieClips, those that have been heavily scaled or rotated. The issue manifests as inconsistent or inaccurate collision detection.

## Bug Description
The `hitTestObject()` function, while generally reliable, may produce unexpected results if either object involved in the collision detection has a complex geometry, has been significantly scaled or rotated, or has unusual transformations applied.

## How to Reproduce
1. Clone this repository.
2. Open the `bug.as` file in an ActionScript 3 IDE (like FlashDevelop).
3. Run the application.
4. Observe that the collision detection is not always accurate.

## Solution
The solution file, `bugSolution.as`, demonstrates a potential workaround using the more robust `getBounds()` method to directly compare the bounding boxes of the objects. This method offers more predictable results.

## Note
While the `getBounds()` method is generally more reliable than `hitTestObject()` for complex shapes and transformations, it might still introduce minor discrepancies for extremely complex shapes.