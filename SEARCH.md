# Search

## Stupid Search
This is simplest of searches for a sorted list. Loop through the list, and on every iteration, check if the current item 
is the item we are looking for. If it is, return the index, otherwise continue. Return `null` if nothing is found by the end.


```javascript
function stupidSearch (list, item) {
    for (let i = 0; i < list.length - 1; i++) {
        if (list[i] === item) {
            return i;
        }
    }

    return null;
}
```

```javascript
let list = [1, 2, 3, 4, 5, 6, 7, 8];
stupidSearch(list, 4);
```
`O(n)` - This is slow because the item we are looking for could be right at the end. 

## Binary Search
Binary search is a much smarter way to search a sorted list. 

You start by checking the mid value. If that value is the target value, 
then wow, we've finished already. If the mid value is greater than the target, we know that everything above the mid value can be discarded.
In this case, we now set the highest value to mid value - 1. However, if the mid value is less than the target, we know everything below
the mid value can be discarded. In this case, we now set the lowest value to mid value + 1. 

In the next iteration we do the same thing, halving the search every time until we find the value. If at the end, we don't find it, we return `null` as always.

```javascript
function binarySearch (list, item) {
    let low = 0;
    let high = list.length - 1;
    let currentItem;

    while (low <= high) {
        mid = ((low + high) / 2) | 0; // | 0 is a bitwise no-op, equivalent to Math.trunc()
        currentItem = list[mid];

        if (currentItem === item) {
            return mid;
        } else if (currentItem > item) {
            high = mid - 1;
        } else {
            low = mid + 1;
        }

    }

    return null;
}
```

```javascript
let list = [1, 2, 3, 4, 5, 6, 7, 8];
binarySearch(list, 9);
```
