
---

## 1. Fixed Stack Dynamic Arrays

- **Definition**: Size is determined at runtime, allocated on stack, cannot be changed after allocation.

| Python                             | JavaScript                  |
|------------------------------------|------------------------------|
| Uses `array.array` (fixed type and size at creation). | Uses `Int32Array` (typed array with fixed size). |
| Stack-allocated in concept, though Python internally abstracts memory. | Behaves like stack in the sense of fixed size, though stored on heap. |
| No resizing allowed.               | No resizing allowed.         |

Example:
- Python: `array.array('i', [0]*5)`
- JavaScript: `new Int32Array(5)`

---

## 2. Stack Dynamic Arrays

- **Definition**: Size can grow/shrink dynamically, allocated on stack.

| Python                             | JavaScript                  |
|------------------------------------|------------------------------|
| Lists (`list`) automatically expand in memory as elements are added. | Arrays (`Array`) automatically expand as elements are added. |
| Elements can be appended, removed without manual memory handling. | Same dynamic behavior; handled internally by JavaScript engine. |
| Under the hood, Python uses a dynamic array strategy with reallocations. | Under the hood, JavaScript arrays can become sparse or dense based on usage. |

Example:
- Python: `list.append()`
- JavaScript: `array.push()`

---

## 3. Fixed Heap Dynamic Arrays

- **Definition**: Size fixed after runtime allocation, stored on heap memory.

| Python                             | JavaScript                  |
|------------------------------------|------------------------------|
| Use `numpy.zeros(N)` to create fixed-size heap-allocated arrays. | Use `ArrayBuffer` and views like `Int32Array`. |
| Cannot change the size after creation. | Cannot change the size of the buffer after allocation. |
| Good for numerical computation.    | Good for binary data or memory efficiency. |

Example:
- Python: `numpy.zeros(5)`
- JavaScript: `new ArrayBuffer(20)` + `new Int32Array(buffer)`

---

## 4. Heap Dynamic Arrays

- **Definition**: Size can change dynamically at runtime, stored on heap memory.

| Python                             | JavaScript                  |
|------------------------------------|------------------------------|
| Lists (`list`) are heap-allocated and grow as needed. | Arrays (`Array`) are heap-allocated and grow as needed. |
| Memory reallocated and managed automatically. | Memory reallocated and managed automatically. |
| Provides flexible data structure.  | Provides flexible data structure. |

Example:
- Python: `list.append()` and `list.pop()`
- JavaScript: `array.push()` and `array.pop()`

---

## Summary Table

| Category              | Python Structure          | JavaScript Structure     |
|------------------------|----------------------------|---------------------------|
| Fixed Stack Dynamic    | `array.array`              | `Int32Array`              |
| Stack Dynamic          | `list`                     | `Array`                   |
| Fixed Heap Dynamic     | `numpy.ndarray`            | `ArrayBuffer` + `TypedArray` |
| Heap Dynamic           | `list`                     | `Array`                   |

---

# How to Run

### Python
```bash
cd arrays/python
python fixed_stack_dynamic.py
python stack_dynamic.py
python fixed_heap_dynamic.py
python heap_dynamic.py
