# Operators Overview

OmniFabric supports a comprehensive set of operators for performing various operations on data. This page provides an overview of all available operators organized by category.

## Operator Categories

### Arithmetic Operators
Perform mathematical calculations on numeric values.

| Operator | Description | Link |
|----------|-------------|------|
| `+` | Addition | [Addition](operators/arithmetic-operators/addition.md) |
| `-` | Subtraction | [Minus](operators/arithmetic-operators/minus.md) |
| `-` | Unary minus (negation) | [Unary Minus](operators/arithmetic-operators/unary-minus.md) |
| `*` | Multiplication | [Multiplication](operators/arithmetic-operators/multiplication.md) |
| `/` | Division | [Division](operators/arithmetic-operators/division.md) |
| `DIV` | Integer division | [DIV](operators/arithmetic-operators/div.md) |
| `%`, `MOD` | Modulo (remainder) | [MOD](operators/arithmetic-operators/mod.md) |

### Comparison Operators
Compare values and return boolean results.

| Operator | Description | Link |
|----------|-------------|------|
| `=` | Equal to | [Equal](operators/comparison-functions-and-operators/assign-equal.md) |
| `<>`, `!=` | Not equal to | [Not Equal](operators/comparison-functions-and-operators/not-equal.md) |
| `<` | Less than | [Less Than](operators/comparison-functions-and-operators/less-than.md) |
| `<=` | Less than or equal | [Less Than or Equal](operators/comparison-functions-and-operators/less-than-or-equal.md) |
| `>` | Greater than | [Greater Than](operators/comparison-functions-and-operators/greater-than.md) |
| `>=` | Greater than or equal | [Greater Than or Equal](operators/comparison-functions-and-operators/greater-than-or-equal.md) |
| `BETWEEN ... AND ...` | Value within range | [BETWEEN](operators/comparison-functions-and-operators/between.md) |
| `NOT BETWEEN ... AND ...` | Value outside range | [NOT BETWEEN](operators/comparison-functions-and-operators/not-between.md) |
| `IN` | Value in list | [IN](operators/comparison-functions-and-operators/in.md) |
| `NOT IN` | Value not in list | [NOT IN](operators/comparison-functions-and-operators/not-in.md) |
| `LIKE` | Pattern matching | [LIKE](operators/comparison-functions-and-operators/like.md) |
| `NOT LIKE` | Pattern not matching | [NOT LIKE](operators/comparison-functions-and-operators/not-like.md) |
| `ILIKE` | Case-insensitive pattern matching | [ILIKE](operators/comparison-functions-and-operators/ilike.md) |
| `IS` | Test for specific values | [IS](operators/comparison-functions-and-operators/is.md) |
| `IS NOT` | Test for not specific values | [IS NOT](operators/comparison-functions-and-operators/is-not.md) |
| `IS NULL` | Test for NULL values | [IS NULL](operators/comparison-functions-and-operators/is-null.md) |
| `IS NOT NULL` | Test for non-NULL values | [IS NOT NULL](operators/comparison-functions-and-operators/is-not-null.md) |

### Logical Operators
Combine or modify boolean expressions.

| Operator | Description | Link |
|----------|-------------|------|
| `AND` | Logical AND | [AND](operators/logical-operators/and.md) |
| `OR` | Logical OR | [OR](operators/logical-operators/or.md) |
| `NOT` | Logical NOT | [NOT](operators/logical-operators/not.md) |
| `XOR` | Logical exclusive OR | [XOR](operators/logical-operators/xor.md) |

### Bitwise Operators
Perform bit-level operations on integer values.

| Operator | Description | Link |
|----------|-------------|------|
| `&` | Bitwise AND | [Bitwise AND](operators/bit-functions-and-operators/bitwise-and.md) |
| `\|` | Bitwise OR | [Bitwise OR](operators/bit-functions-and-operators/bitwise-or.md) |
| `^` | Bitwise XOR | [Bitwise XOR](operators/bit-functions-and-operators/bitwise-xor.md) |
| `~` | Bitwise inversion (NOT) | [Bitwise Inversion](operators/bit-functions-and-operators/bitwise-inversion.md) |
| `<<` | Left shift | [Left Shift](operators/bit-functions-and-operators/left-shift.md) |
| `>>` | Right shift | [Right Shift](operators/bit-functions-and-operators/right-shift.md) |

### Assignment Operators
Assign values to variables or columns.

| Operator | Description | Link |
|----------|-------------|------|
| `=` | Assignment | [Equal](operators/assignment-operators/equal.md) |

### Cast and Conversion Operators
Convert data between different types.

| Operator/Function | Description | Link |
|-------------------|-------------|------|
| `CAST` | Convert data type | [CAST](operators/cast-functions-and-operators/cast.md) |
| `CONVERT` | Convert data type with format | [CONVERT](operators/cast-functions-and-operators/convert.md) |
| `BINARY` | Convert to binary string | [BINARY](operators/cast-functions-and-operators/binary.md) |
| `ENCODE` | Encode data | [ENCODE](operators/cast-functions-and-operators/encode.md) |
| `DECODE` | Decode data | [DECODE](operators/cast-functions-and-operators/decode.md) |
| `SERIAL` | Serialize data | [SERIAL](operators/cast-functions-and-operators/serial.md) |
| `SERIAL_FULL` | Full serialization | [SERIAL_FULL](operators/cast-functions-and-operators/serial_full.md) |

### Flow Control Functions
Control program flow based on conditions.

| Function | Description | Link |
|----------|-------------|------|
| `CASE WHEN` | Conditional expressions | [CASE WHEN](operators/flow-control-functions/case-when.md) |
| `IF` | Simple conditional | [IF](operators/flow-control-functions/function_if.md) |
| `IFNULL` | Handle NULL values | [IFNULL](operators/flow-control-functions/function_ifnull.md) |
| `NULLIF` | Return NULL if equal | [NULLIF](operators/flow-control-functions/function_nullif.md) |

### Special Comparison Functions

| Function | Description | Link |
|----------|-------------|------|
| `COALESCE` | Return first non-NULL value | [COALESCE](operators/comparison-functions-and-operators/coalesce.md) |
| `ISNULL` | Test for NULL | [ISNULL](operators/comparison-functions-and-operators/function_isnull.md) |

| `STRCMP` | String comparison | [STRCMP](operators/comparison-functions-and-operators/function_strcmp.md) |
| `INTERVAL` | Time interval operations | [INTERVAL](operators/comparison-functions-and-operators/function_interval.md) |

### Other Operators

| Operator | Description | Link |
|----------|-------------|------|
| `INTERVAL` | Time and date intervals | [INTERVAL](interval.md) |

## Operator Precedence

Understanding operator precedence is crucial for writing correct expressions. See the [Operator Precedence](operators/operator-precedence.md) guide for detailed information about the order of operations.

## Usage Guidelines

### Arithmetic Operations
- Use parentheses to control evaluation order
- Be aware of integer vs. decimal division
- Handle division by zero appropriately

### Comparison Operations
- Use appropriate operators for data types
- Consider NULL handling in comparisons
- Use LIKE for pattern matching with wildcards

### Logical Operations
- Use parentheses to group complex conditions
- Understand short-circuit evaluation behavior
- Consider NULL values in logical expressions

### Bitwise Operations
- Primarily used with integer data types
- Useful for flag operations and bit manipulation
- Consider signed vs. unsigned integer behavior

### Type Conversions
- Use explicit CAST when needed
- Be aware of implicit type conversions
- Handle conversion errors appropriately

## Performance Considerations

1. **Index Usage**: Some operators can prevent index usage
2. **Type Matching**: Avoid unnecessary type conversions
3. **Complex Expressions**: Break down complex expressions for readability
4. **NULL Handling**: Consider performance impact of NULL checks

For detailed syntax and examples of each operator, click on the individual links above.
