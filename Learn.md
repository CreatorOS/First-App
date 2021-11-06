# First Application

In this Quest, we'll create an application to increment or decrement a simple counter and see it's value.

## Create a counter

Let's create an unsigned integer variable called `count` and set it as public.

```
    uint public count;
```

- `uint` is a primitive datatype for unsigned integers. This is a 256 bit number. The largest number it can store is `2^256 - 1`
- `count` is not initialized. But every variable is default initialized with a default value for that variable. In this case, it'd be `0`.

In next subquest, we will function to check its value.

## Getting counter value

Let's create a function called `get` that returns the value of `count`.

```
    function get() public view returns (uint) {
        return count;
    }
```

- `function get() public view returns (uint)` when returning, you must specify the return type under `returns`. If the function doesn't make any modification to any variables in the contract, you can add another modifier called `view`. `view` functions don't cost any eth to run - they're free of cost. 

Hit `Run` button to run the test and see the output of the count variable. You should see 0.

## Incrementing counter

Now, let's create a function called `inc` that increments the value of `count` by 1.

```
    function inc() public {
        count += 1;
    }
```

- `function inc() public` represents a function that is public and can be called from outside the contract - by other contracts or by users.
- Here we are using shorthand operator `+=` to increment the value of `count`.
- It can be written as follow as well:
  ```
      function inc() public {
          count = count + 1;
      }
  ```
  This function makes a change to a contract (state) variable. So this cannot be a `view` function. We will have to pay some eth to run this function! 
  Hit `Run` button to run the test and see the output of the count variable. You should see 1.

## Decrementing counter

Now, let's create a function called `dec` that decrements the value of `count` by 1.

```
    function dec() public {
        count -= 1;
    }
```

- Notice `inc()` and `dec()` update the variable inside their function body - hence don't have the `view` modifier

Hit `Run` button to run the test and see the output of the count variable after calling `dec()`. You should see 0. It was first incremented by 1 and then decremented by 1.
