# 3. Code Block Labelling for Screen Reader Users

## Issue

The accessible website currently presents Python code blocks and their expected output without labels. A screen reader user cannot tell by ear whether the content being read is a code snippet, an expected output, or body text. This makes it difficult to follow along and replicate exercises in VS Code.

## Proposed Solution

Add a short plain-text label before and after every code block and every output block. The labels should be outside the code block so they are read as normal text by NVDA.

### Label convention

Before a code block:
```
The following is Python code:
```

After a code block:
```
End of code.
```

Before an expected output block:
```
The following is the expected output:
```

After an expected output block:
```
End of output.
```

---

## Example

### Current version (without labels)

A **list** is an ordered, mutable collection of items, written with square brackets like `['dog', 'cat', 'fish']`.

```python
l = ['dog', 'cat', 'fish']
print(type(l))
```

```
<class 'list'>
```

---

### Proposed version (with labels)

A **list** is an ordered, mutable collection of items, written with square brackets like `['dog', 'cat', 'fish']`.

The following is Python code:

```python
l = ['dog', 'cat', 'fish']
print(type(l))
```

End of code.

The following is the expected output:

```
<class 'list'>
```

End of output.
