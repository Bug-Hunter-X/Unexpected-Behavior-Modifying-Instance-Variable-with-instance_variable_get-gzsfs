# Ruby Instance Variable Modification Bug

This repository demonstrates a subtle bug in Ruby related to modifying instance variables using `instance_variable_get` and assignment.  The expected behavior is that modifying the value returned by `instance_variable_get` would change the instance variable itself. However, this is not the case.  The code showcases this unexpected behavior and provides a solution.

## Bug Description
The bug lies in the misuse of `instance_variable_get`.  While it retrieves the value of an instance variable, assigning a new value to the *returned* value does *not* update the instance variable itself.  This is because the assignment creates a new object in memory.

## Solution
The solution involves using `instance_variable_set` to directly update the instance variable. This method correctly modifies the internal state of the object.
