# Lab Report 3: Bugs and Commands (week 6)
---
## Part 1: Bugs
Failure Inducing Input for the Array reverseInPlace method
  1. ```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}

@Test
public void testReverseInPlace1(){
  int[] inp1 = {0,2,4,6};
  ArrayExamples.reverseInPlace(inp1);
  assertArrayEquals(new int[]{6,4,2,0}, inp1);
}
```
Input which doesn't induce a failure
  2. ```
@Test
public testReversedMultple(){
  int[] input1 = {3};
  assertArrayEquals(new int[]{3}, ArrayExamples.reversed(input1);
}```
The Symptom as a result of running the two test above
  3. ![Image]()
  4. 
  5. 

---
## Part 2: Researching Commands
