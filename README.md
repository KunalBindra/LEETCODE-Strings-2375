# LEETCODE-Strings-2375
- **Stack is used** to store numbers temporarily.
- **Whenever an 'I' or end of pattern is reached**, numbers are popped from the stack and appended to the result.
- This ensures that **'D' forces numbers to be stored and reversed, while 'I' releases them immediately**.

---

### **Example Dry Run**
#### **Input:**  
`pattern = "IDID"`

#### **Steps:**
| Step | i | pattern[i] | count | Stack (`st`) | Result (`result`) |
|------|---|------------|-------|--------------|--------------------|
| 1    | 0 | I          | 1     | [1]          |                    |
| 2    |   |            | 2     | [1, 2]       |                    |
| 3    |   | 'I' found  |       | [] (pop 2,1) | "21"               |
| 4    | 1 | D          | 3     | [3]          | "21"               |
| 5    | 2 | I          | 4     | [3, 4]       | "21"               |
| 6    |   | 'I' found  |       | [] (pop 4,3) | "2143"             |
| 7    | 3 | D          | 5     | [5]          | "2143"             |
| 8    | 4 | End        | 6     | [5, 6]       | "2143"             |
| 9    |   | 'I' found  |       | [] (pop 6,5) | "214365"           |

#### **Final Output:**  
`"214365"`

---

### **Another Example**
#### **Input:**  
`pattern = "DDD"`

#### **Steps:**
| Step | i | pattern[i] | count | Stack (`st`) | Result (`result`) |
|------|---|------------|-------|--------------|--------------------|
| 1    | 0 | D          | 1     | [1]          |                    |
| 2    | 1 | D          | 2     | [1, 2]       |                    |
| 3    | 2 | D          | 3     | [1, 2, 3]    |                    |
| 4    | 3 | End        | 4     | [1, 2, 3, 4] |                    |
| 5    |   | 'I' found  |       | [] (pop 4,3,2,1) | "4321"       |

#### **Final Output:**  
`"4321"`

---

### **Time Complexity Analysis**
- The loop runs `n+1` times.
- Each element is pushed and popped exactly once.
- **Time Complexity: O(n)**
- **Space Complexity: O(n) (for stack usage)**
