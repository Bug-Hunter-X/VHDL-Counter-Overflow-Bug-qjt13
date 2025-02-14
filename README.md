# VHDL Counter Overflow Bug

This repository demonstrates a common error in VHDL code: an integer counter that can overflow without explicit bounds checking. The `buggy_counter.vhd` file contains the buggy code, while `fixed_counter.vhd` provides a corrected version.

## Bug Description
The `buggy_counter` entity uses an integer signal `internal_count` to represent the counter value.  When the counter reaches its maximum value (15), the next increment will result in an overflow, wrapping around to 0 or potentially causing simulation errors. This behavior is undefined in the VHDL standard.

## Solution
The `fixed_counter` entity addresses this issue by adding a check within the `if rising_edge(clk)` section. It ensures that the counter value remains within the valid range (0 to 15).