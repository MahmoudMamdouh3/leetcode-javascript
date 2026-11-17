# JavaScript Algorithms & Data Structures (LeetCode / NeetCode)

![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-Runtime-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![Roadmap](https://img.shields.io/badge/Roadmap-NeetCode%20250-blue?style=flat-square)

I built this repository to track my progress in algorithmic problem-solving, document time and space complexity trade-offs, and keep personal notes and resources as I master JavaScript from the ground up.

---

## Repository Structure

Solutions are grouped by core algorithmic pattern rather than problem number to build pattern-recognition habits:

```text
leetcode-js/
├── 01-arrays-and-hashing/
├── 02-two-pointers/
├── 03-sliding-window/
├── 04-stack/
├── 05-binary-search/
└── README.md
```

---

## Progress & Problem Log

### 01. Arrays & Hashing
| # | Problem | Difficulty | Solution | Time | Space | Personal Notes / Key Takeaway |
|---|---|---|---|---|---|---|
| 217 | [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/) | Easy | [JS](./01-arrays-and-hashing/01-contains-duplicate.js) | $O(n)$ | $O(n)$ | `Set.has()` is $O(1)$ average lookup; early return on match |
| 242 | [Valid Anagram](https://leetcode.com/problems/valid-anagram/) | Easy | [JS](./01-arrays-and-hashing/02-valid-anagram.js) | $O(n)$ | $O(1)$ | Fixed 26-char frequency array beats sorting ($O(n \log n)$) |
| 1 | [Two Sum](https://leetcode.com/problems/two-sum/) | Easy | [JS](./01-arrays-and-hashing/03-two-sum.js) | $O(n)$ | $O(n)$ | Store `target - num` in a `Map` (`value -> index`) in a single pass |

### 02. Two Pointers
| # | Problem | Difficulty | Solution | Time | Space | Personal Notes / Key Takeaway |
|---|---|---|---|---|---|---|
| 125 | [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/) | Easy | [JS](./02-two-pointers/01-valid-palindrome.js) | $O(n)$ | $O(1)$ | Compare ASCII codes in-place to avoid regex string allocation |

---

## Personal JavaScript DSA Notes & Gotchas

A running cheat sheet of JavaScript quirks and standard library patterns learned while solving problems:

* **Number Sorting Trap:** `Array.prototype.sort()` converts elements to strings by default (`[1, 10, 2]` stays `[1, 10, 2]`). Always pass a comparator:
  * Ascending: `nums.sort((a, b) => a - b)`
  * Descending: `nums.sort((a, b) => b - a)`
* **Integer Division:** JavaScript uses 64-bit floats for all numbers (`5 / 2 === 2.5`). For binary search midpoints or index math, use `Math.floor(left + (right - left) / 2)` or bitwise `>> 1`.
* **Map vs. Plain Object (`{}`):** Prefer `new Map()` for dynamic hash tables—it preserves insertion order, supports non-string keys, and provides an $O(1)$ `.size` property.
* **ASCII Character Math:** Use `'a'.charCodeAt(0)` (97) to map lowercase letters to `0–25` array indices: `char.charCodeAt(0) - 97`.
* **Queue / Deque Operations:** `Array.push()` and `Array.pop()` are $O(1)$, but `Array.shift()` (removing from the front) is $O(n)$ because it re-indexes the array. For large BFS queues, use an index pointer instead of `.shift()`.

---

## Curated Resources

* **[NeetCode Roadmap](https://neetcode.io/roadmap):** Topic-by-topic progression and visual pattern breakdowns.
* **[MDN JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects):** Official documentation for built-in objects (`Map`, `Set`, `Array`, `String`).
* **[Big-O Cheat Sheet](https://www.bigocheatsheet.com/):** Time and space complexity reference for common data structures and sorting algorithms.
* **[VisuAlgo](https://visualgo.net/en):** Interactive step-by-step animations for trees, graphs, and sorting.

---

## Getting Started & Running Solutions

Each solution file is self-contained with sample test cases at the bottom. You can run them locally using **Node.js** or test them in a browser with zero setup.

### Option 1: Run Locally with Node.js (Recommended)

1. **Install Node.js:** Download and install the LTS version from [nodejs.org](https://nodejs.org/) (or via terminal on Windows using `winget install OpenJS.NodeJS.LTS`).
2. **Clone this repository:**
   ```bash
   git clone [https://github.com/MahmoudMamdouh3/leetcode-js.git](https://github.com/MahmoudMamdouh3/leetcode-js.git)
   cd leetcode-js
   ```
3. **Execute any solution file:**
   ```bash
   node 01-arrays-and-hashing/01-contains-duplicate.js
   ```
4. **Optional VS Code Extensions:** If opening this folder in [VS Code](https://code.visualstudio.com/), install **Code Runner** (for one-click file execution) or **Quokka.js** (for real-time inline `console.log` evaluation).

### Option 2: Run Without Installing Anything (Zero Setup)

* **Browser Console:** Press `F12` (or `Ctrl+Shift+J`) in any web browser to open Developer Tools, switch to the **Console** tab, and paste the contents of any `.js` file.
* **Online Judges:** Copy the function directly into the linked problem editor on [LeetCode](https://leetcode.com/) or [NeetCode](https://neetcode.io/).