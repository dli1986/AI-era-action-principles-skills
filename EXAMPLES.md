# Examples

Concrete examples of the AI Era Action Principles skill in action.

Each example shows how a vague goal becomes an expert resource map, a gateway minimal action, and a persistent note.

---

## Example 1: Python Closures

> Trigger: "I want to understand Python closures"

---

# Action Card: Python Closures

## 1. Real Need
Understand how closures work under the hood, recognize the loop late-binding trap, and know when to use closures instead of classes.

## 2. Expert Resources

### Python Official Docs — Nested Scopes
- **Why experts check it:** Defines LEGB rules and the exact semantics of free variables
- **What to do:** Search `python reference expressions.html#resolution-of-names`, focus on "closure" and "free variable" definitions
- **What to extract:** Cell object lifecycle, scope of `nonlocal`
- **Common beginner miss:** Reading only tutorials — never discovering the `__closure__` attribute

### `inspect` module + `__closure__` attribute
- **Why experts check it:** Directly proves what variables a closure captured — most reliable for debugging
- **What to do:** Run `f.__closure__[0].cell_contents` to inspect captured value
- **What to extract:** Variables are captured by cell (reference), not copied by value
- **Common beginner miss:** Assuming the closure "snapshots" the value at definition time

### Loop + Closure Late Binding Example
- **Why experts check it:** Most common production bug source involving closures
- **What to do:** Deliberately write the broken version, then fix it two ways
- **What to extract:** A closure captures the variable name (cell), not the current value

## 3. Correct Path

```
Understand LEGB rules
→ Write a minimal closure (counter)
→ Use __closure__ to prove capture is a cell
→ Reproduce the loop late-binding bug
→ Fix with default argument
→ Fix with nonlocal
→ Decide: closure vs class — which is clearer?
```

## 4. Avoid

- Reading only blog definitions without writing the bug and fixing it
- Confusing `global` and `nonlocal` (`global` refers to module scope; `nonlocal` refers to the nearest enclosing function)
- Using closures to hold large amounts of state (use a class instead)

## 5. Gateway Minimal Action

**Goal:** Prove that closures capture by cell reference, not by value snapshot, and fix the loop trap.

```python
# 1. Minimal closure + cell verification
def make_counter(start=0):
    count = start
    def increment():
        nonlocal count
        count += 1
        return count
    return increment

c = make_counter()
print(c(), c(), c())                       # 1 2 3
print(c.__closure__[0].cell_contents)      # 3  ← captured by cell, not snapshot

# 2. Reproduce late-binding bug
funcs_bad = [lambda: i for i in range(3)]
print([f() for f in funcs_bad])            # [2, 2, 2]  ← all 2, bug!

# 3. Fix: default argument forces snapshot
funcs_good = [lambda i=i: i for i in range(3)]
print([f() for f in funcs_good])           # [0, 1, 2]  ← correct
```

**Evidence (success criteria):**
- `c.__closure__[0].cell_contents` returns `3` (proves cell reference capture)
- `funcs_bad` outputs `[2, 2, 2]` (you witnessed the bug firsthand)
- `funcs_good` outputs `[0, 1, 2]` (you fixed it)

## 6. Save This

```
Closure Cheatsheet:
- Closures capture variable names (cells), not values
- __closure__[i].cell_contents inspects captured values
- Loop late-binding bug: use lambda i=i: i to force snapshot
- nonlocal modifies the nearest enclosing function's variable
- global modifies module-level variable
- Rule of thumb: if state > 1-2 variables, prefer a class
```

## 7. Optional Retro Hooks

After running the gateway action, answer:
- Did `__closure__` output surprise you?
- Did you actually see `[2, 2, 2]` output before reading the fix?
- What constraint or edge case did the fix reveal?
- What would you add to a team onboarding doc about closures?
