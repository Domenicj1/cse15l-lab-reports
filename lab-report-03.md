# Lab Report 3: Bugs and Commands (week 6)
---
## Part 1: Bugs

1. Failure Inducing Input for the Array reverseInPlace method
```
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

2. Input which doesn't induce a failure
```
@Test
public testReversedMultple(){
  int[] input1 = {3};
  assertArrayEquals(new int[]{3}, ArrayExamples.reversed(input1);
}
```

3. The Symptom as a result of running the two test above
 ![Image](https://github.com/Domenicj1/cse15l-lab-reports/assets/146692334/763c3f81-93cc-4501-924c-10977c520488)

4. Before then After code changes to fix the buggy behavior
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
Corrected Method
```
static void reverseInPlace(int[] arr) {
  if(arr.length > 0){
  for(int i = 0; i < arr.length; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
    }
  }
}
```

5. The fixed implementation correctly swaps elements in the array by iterating only halfway and swapping elements from opposite ends, ensuring that each element is moved to its correct position exactly once. The buggy implementation, however, overwrites the elements of the array without preserving their original values, resulting in an incorrect final state where only the elements from the second half of the array are correctly reversed.

---
## Part 2: Researching Commands
