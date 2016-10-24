# Logical Operators

[See Javascript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Short-Circuit_Evaluation)

Logical operators are typically used with Boolean (logical) values. When they are, they return a Boolean value. However, the && and || operators actually return the value of one of the specified operands, so if these operators are used with non-Boolean values, they may return a non-Boolean value.

Description
The logical operators are described in the following table:


		
		
		

| Operator | Usage | Description|
| -- | -- | -- |
| Logical AND (&&) | expr1 && expr2 | Returns expr1 if it can be converted to false; otherwise, returns expr2. Thus, when used with Boolean values, && returns true if both operands are true; otherwise, returns false. |
| Logical OR  | expr1 $$||$$ expr2  | Returns expr1 if it can be converted to true; otherwise, returns expr2. Thus, when used with Boolean values, OR returns true if either operand is true. |
| Logical NOT (!)| !expr| Returns false if its single operand can be converted to true; otherwise, returns true.|


If a value can be converted to true, the value is so-called truthy. If a value can be converted to false, the value is so-called falsy.