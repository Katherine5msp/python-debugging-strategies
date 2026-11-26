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

## Task 3 - Following the Data

- Used pdb from the command line.
- Traced data across multiple functions.
- Inspected subtotal and discount rate.
- Identified incorrect percentage conversion.
- Distinguished the root cause from the visible symptom.
- Corrected the discount rate by dividing by 100.
- Verified the final total: 28.62.

## Task 4 - Debugging with logging

- Configured logging using logging.basicConfig().
- Used DEBUG, INFO, and WARNING severity levels.
- Analyzed logs to identify a counting bug.
- Moved the counter inside the validation condition.
- Corrected the average from 15.0 to 20.0.
- Verified syntax and edge case behavior.

Lesson learned: Logging provides structured visibility
into program behavior and helps identify logic errors.

## Task 5: Defensive Debugging

**File:** `defensive.py`

### Objective
Improve program reliability by validating assumptions and detecting
invalid inputs before they cause unexpected behavior.

### Root Cause
The original program assumed that every comma-separated value was a
valid integer. It did not handle empty inputs or scores outside the
expected range of 0 to 100.

### Solution
- Added input type validation.
- Rejected empty input and missing scores.
- Added clear error messages for non-numeric values.
- Restricted scores to the range 0–100.
- Preserved average calculations and grade classification.

### Testing
Tested seven scenarios covering valid scores, invalid text, empty
input, missing values, and out-of-range scores.

All seven functional tests passed.

### Lesson Learned
Defensive debugging helps identify problems at their source.
Validating assumptions early makes errors easier to understand,
diagnose, and correct.
