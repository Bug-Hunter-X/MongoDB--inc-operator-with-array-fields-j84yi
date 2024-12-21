# MongoDB $inc operator with array fields

This repository demonstrates a common error when using the `$inc` operator in MongoDB with array fields. The `$inc` operator is intended for incrementing numeric fields, but using it with dot notation on array elements can lead to unexpected results.

## Bug

The original code attempts to increment the first element of an array field (`arrayField.0`).  This is incorrect. `$inc` will not work in this way.

## Solution

The correct way to achieve this would be to use the `$` positional operator or to modify the whole array. This example demonstrates using the `$` operator to modify the element at the given index.  For more complex array operations, you should use array filters and other array operators.