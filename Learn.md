# First Application

We'll create an application to increment or decrement a simple counter and see it's value.

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.3;

contract Counter {
    uint public count;

    // Function to get the current count
    function get() public view returns (uint) {
        return count;
    }

    // Function to increment count by 1
    function inc() public {
        count += 1;
    }

    // Function to decrement count by 1
    function dec() public {
        count -= 1;
    }
}
```

- `uint` is a primitive datatype for unsigned integers. This is a 256 bit number. The largest number it can store is `2^256 - 1`
- `count` is not initialized. But every variable is default initialized with a default value for that variable. In this case, it'd be `0`.
- `function inc() public` represents a function that is public and can be called from outside the contract - by other contracts or by users.
- `function get() public view returns (uint)` when returning, you must specify the return type under `returns`. If the function doesn't make any modification to any variables in the contract, you can add another modifier called `view`. Notice `inc()` and `dec()` update the variable inside their function body - hence don't have the `view` modifier

```
  run testcases 02.sh
```