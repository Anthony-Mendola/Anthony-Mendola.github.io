---
layout: post
title:      "JavaScript Unary (+) Operator"
date:       2018-10-16 02:34:53 +0000
permalink:  javascript_unary_operator
---

The unary plus operator is something I rarely see used but is very useful in place of parseInt(x) or Number(x) in most cases.

What's a unary operator? 
A unary operator is one that takes a single operand/argument and performs an operation. A unary operation is an operation with only one operand. This operand comes either before or after the operator. Unary operators are more efficient than standard JavaScript function calls. Additionally, unary operators can not be overridden, therefore their functionality is guaranteed.

![](https://scotch-res.cloudinary.com/image/upload/dpr_1,w_800,q_auto:good,f_auto/media/14604/EOsYiNm9TS6iit5j04dY_Screen%20Shot%202017-02-03%20at%205.30.44%20PM.png)


What is the unary plus (+)? 
This operator precedes the operand and tries to convert it to a number.

```
var positiveOne = +1
```

The Unary (+) can convert string representations of integers and floats, as well as the non-string values true, false, and null. Integers in both decimal and hexadecimal formats are supported. Negative numbers are supported (though not for hex). If it cannot parse a particular value, it will evaluate to NaN.No need to parseInt or parseFloat everything. And you sure don’t need to use Number()!

There are some cases where unary (+) may not work as expected, see this chart below:
![](https://i.stack.imgur.com/gRf2B.png)

