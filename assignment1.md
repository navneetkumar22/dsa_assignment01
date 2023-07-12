# PPT - DSA Assignment 1

## Answer 1:
```js
const twoSum = (nums, target) => {
    for (let i = 0; i < nums.length; i++) {
        for (let j = i + 1; j < nums.length; j++) {
            if (nums[i] + nums[j] == target) {
                return [i, j]
            }
        }
    }
};
```
<br/>

## Answer 2:
```js
const countElements = (nums, val) => {

    let k = 0;
    for (let i = 0; i < nums.length; i++) {
        //if an array element not equal to val, we'll get it into nums and increase "k" by 1 
        if (nums[i] !== val) {
            nums[k++] = nums[i];
        }
    }
    return k;
};
```

<br/>

## Answer 3:
```js
const getIndex = (nums, val) => {

    for (let i = 0; i < nums.length; i++) {

        if (nums[i] === val)
            return i;

        else if (nums[i] > val)
            return i;
    }

    return nums.length;
};
```

<br/>

## Answer 4:
```js
const incrementNum = (digits) => {
    for (let i = digits.length - 1; i >= 0; i--) {

        if (digits[i] < 9) {
            digits[i] += 1;
            return digits;
        }
        else {
            digits[i] = 0;
        }
    }

    digits.unshift(1); //to put a 1 on unit place when every digit is 9
    return digits;
};
```

<br/>

## Answer 5:
```js
const mergeArrays = function(nums1, m, nums2, n) {
  m--;
  n--;
  let i = nums1.length - 1;
  while (i >= 0) {
    if (n > -1 && m > -1 && nums1[m] >= nums2[n]) {
      nums1[i] = nums1[m];
      nums1[m] = nums2[n];
      m--;
    }
    else if (n > -1) {
      nums1[i] = nums2[n--];
    }
    i--;
  }
};
```

<br/>

## Answer 6:
```js
const isDuplicate = (nums) => {
    // create an object to check if number is repeated
    let counts = {};

    for( let i =0; i < nums.length; i++){

      if( !counts[ nums[i] ] ){
        //if there is no key/value
        counts[ nums[i] ] = 1;
      } 
      else{
        //increase count if present
        counts[ nums[i] ] += 1;
      }

    }

    // if any object vals is 1 - return false, else return true
    return Math.max(...Object.values(counts)) > 1 ? true : false;

};
```

<br/>

## Answer 7:
```js
const moveAllZeroes = (nums) => {
    for (let i = nums.length - 1; i >= 0; i--) {

        //if zero is found at any place - splice it and push a zero into the array
        if (nums[i] === 0) {
            nums.push(0);
            nums.splice(i, 1);
        }
    }
    return nums;
};
```

<br/>

## Answer 8:
```js
const findNumbers = (nums) => {
    const newArr = [];

    for (let num of nums) {
        num = Math.abs(num);

        if (nums[num - 1] < 0) {
            newArr.push(num);
        }
        else {
            nums[num - 1] = -nums[num - 1];
        }
    }

    for (let i = 0; i < nums.length; i++) {
        if (nums[i] > 0) {
            newArr.push(i + 1);
        }
        if (newArr.length === 2)
            return newArr;
    }
};
```