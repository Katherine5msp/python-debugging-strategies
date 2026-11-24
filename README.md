# Python - Debugging Strategies

## Task 0 - Reading the Bug

### Investigation
- Exception: TypeError.
- Failure location: line 13.
- Root cause: line 20 returned strings instead of integers.

### Resolution
Replaced ["12", "5", "7"] with [12, 5, 7].

### Verification
Total readings: 24

### Lesson Learned
Tracebacks help distinguish the symptom of a bug
from its root cause.

## Task 1 - Debugging with print()

### Investigation
- Error type: Logical error.
- Expected result: 3.
- Original result: 2.
- Technique: Temporary print() statements.
- Root cause: Incorrect comparison operator on line 18.

### Resolution
Replaced the less-than operator with the
greater-than-or-equal-to operator.

### Verification
OK readings: 3

### Lesson Learned
Successful execution does not guarantee correct results.
Print debugging reveals variable states and logical errors.

## Task 2 - First Steps with pdb

- Used breakpoint() to pause execution.
- Inspected variables using the p command.
- Navigated execution using n, s, and r.
- Identified a logic bug in score accumulation.
- Replaced raw_sum += raw with raw_sum += adjusted.
- Removed the temporary breakpoint.
- Verified the adjusted average: 70.0.
