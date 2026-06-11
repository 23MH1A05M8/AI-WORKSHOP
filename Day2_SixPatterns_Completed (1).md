# Day 2 — Lab 2A: Six-Pattern Drills
**Student Name:** HADASSA KUNISETTY
**Topic Used:** "Explain Binary Search for a placement interview."
**Date:** June 10, 2026
**Tools Used:** Claude.ai (free) and ChatGPT (free)

---

## Student Question Used

> "Explain Binary Search for a placement interview."

*(Substituted from default Big-O topic as permitted by lab instructions.
Binary Search is equally common in TCS/Infosys/Wipro placement drives.)*

---

# PATTERN 1 — PERSONA

## Prompt Written (same prompt run on BOTH tools)

```
You are a senior placement coach at JNTU Kakinada, Andhra Pradesh. You have
helped over 300 B.Tech CSE students crack interviews at TCS, Wipro, and HCL
over the past 8 years. A 3rd-year CSE student with a 7.8 CGPA comes to you
nervous before a campus drive and asks: "Sir, how do I explain Binary Search
in an interview?" Explain it the way you would in a relaxed 1-on-1 coaching
session — practical, confidence-building, and interview-ready.
```

---

## Response — Claude.ai (free)

Relax. Binary Search is one of those topics that rewards students who
understand it — and you can.

Imagine you are looking for "Mango" in a physical dictionary. You do not
start from page 1. You open the book to the middle. If "Mango" belongs
after that page, you tear away the left half and repeat. If before, tear
away the right half. You keep halving until you land on it. That is Binary
Search — you eliminate half the problem with every single step.

**The formal version for your interview:**
Binary Search works on a *sorted array*. You keep track of two pointers
— `low` (start) and `high` (end). Calculate `mid = (low + high) // 2`.
If `arr[mid]` equals your target, done. If target is greater, set
`low = mid + 1`. If target is smaller, set `high = mid - 1`. Repeat
until found or `low > high`.

```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

arr = [3, 7, 11, 15, 22, 38, 46]
print(binary_search(arr, 22))  # Output: 4
```

**Time: O(log n)** — each step cuts the problem in half.
**Space: O(1)** — only three variables used.

**The one thing that trips students:** the array must be *sorted first*.
If your interviewer asks "what is the precondition?" — that is your answer.
Say it before you write the code.

---

## Response — ChatGPT (free)

Hey, do not stress — Binary Search is actually one of the easier topics
to explain well if you frame it right.

Think about finding a word in a dictionary. You do not read every page.
You open to the middle, see if your word comes before or after, and jump
to that half. You repeat until you find it. That is the entire intuition
behind Binary Search.

**How to explain it in the interview:**
"Binary Search is an efficient algorithm to find a target in a **sorted
array**. It works by dividing the search interval in half each time. We
maintain `low` and `high` pointers and compute `mid`. If `arr[mid]`
equals target — done. If target is greater — search right. If smaller
— search left."

```python
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```

**Time: O(log n)** — half the array eliminated per comparison.
**Space: O(1)** — no extra memory.

**Pro tip:** Always mention "array must be sorted" before anything else.
Interviewers specifically listen for this. Many candidates forget it and
lose marks silently.

---

## Comparison — Pattern 1 (PERSONA)

| Aspect | Claude.ai | ChatGPT |
|---|---|---|
| Tone match to coach persona | Very warm, local context (dictionary) | Warm, slightly more structured |
| Precondition highlighted | Yes — "one thing that trips students" | Yes — "pro tip" |
| Code quality | Clean with inline test | Clean with comments |
| Interview scripting | Says what to *do* (say it before code) | Gives a ready-to-speak scripted sentence |
| Domain relevance | JNTU / AP context felt authentic | Slightly generic but still useful |

**Self-Score (Claude): 5/5**
**Self-Score (ChatGPT): 5/5**

Both tools produced warm, coaching-style responses. Claude felt more
emotionally supportive and locally contextualised. ChatGPT provided a
ready-made interview script sentence — also highly practical.

---

---

# PATTERN 2 — FEW-SHOT

## Prompt Written (same prompt run on BOTH tools)

```
Here are example explanations from a placement coach:

Q: What is a linked list?
A: A chain of nodes where each node holds data and a pointer to the next
node. Unlike arrays, memory is not contiguous. Used in stacks, queues, and
undo systems. Insertion/deletion is O(1) if you have the pointer.

Q: What is a hash table?
A: A data structure that maps keys to values using a hash function. Average
O(1) lookup. Like a locker system — the key tells you which locker to open.
Collisions handled by chaining or open addressing.

Q: What is Binary Search?
A:
```

---

## Response — Claude.ai (free)

A: A search algorithm on a *sorted array* that halves the search space
each step. Maintain `low` and `high` pointers; compute
`mid = (low + high) // 2`. If `arr[mid]` equals target — done. Greater
— move `low = mid + 1`. Smaller — move `high = mid - 1`. Time: O(log n).
Space: O(1). Interview must-say: "array must be sorted." Classic
follow-up: find first occurrence of a duplicate — continue searching left
after a match.

---

## Response — ChatGPT (free)

A: A fast search on a **sorted array**. Divide and conquer — check the
middle element, discard the half that cannot contain the target, repeat.
Like finding a page in a book by opening to the middle each time.
Time: O(log n) — 30 steps to search a billion elements. Space: O(1)
iterative. Key rule: array must be sorted. Common follow-up: "How do
you handle duplicates?" — modify to continue searching after finding
a match instead of returning immediately.

---

## Comparison — Pattern 2 (FEW-SHOT)

| Aspect | Claude.ai | ChatGPT |
|---|---|---|
| Format inherited | Yes — short, punchy, no headers | Yes — equally compact |
| Analogy added | None (examples had none — strict copy) | Book analogy added (slight deviation) |
| Precondition stated | Yes | Yes |
| Follow-up included | Yes — duplicate first-occurrence | Yes — handling duplicates |
| Code snippet | No (examples had no code; model copied style) | No |

**Self-Score (Claude): 3/5**
**Self-Score (ChatGPT): 4/5**

Both tools correctly inherited the short, punchy format from the
few-shot examples. Key lesson of Pattern 2: the examples control the
output shape completely. Neither model included code because no example
showed code. Claude was stricter to the format; ChatGPT added a small
analogy — a minor style deviation worth noting.

---

---

# PATTERN 3 — CHAIN-OF-THOUGHT

## Prompt Written (same prompt run on BOTH tools)

```
Explain Binary Search to a placement interview candidate. Think step by
step before answering.

Step 1: Define Binary Search in one sentence.
Step 2: State the single most important precondition.
Step 3: Give one concrete Python code example.
Step 4: Explain the time and space complexity with clear reasoning.
Step 5: Synthesise into a 3-sentence interview-ready summary.
```

---

## Response — Claude.ai (free)

**Step 1 — Definition:**
Binary Search is an algorithm that finds a target value in a sorted array
by repeatedly halving the search space until the target is found or
confirmed absent.

**Step 2 — Precondition:**
The array MUST be sorted. Binary Search on an unsorted array produces
silently wrong results — this is the most common interview mistake.

**Step 3 — Python Code:**

```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid           # found
        elif arr[mid] < target:
            low = mid + 1        # search right half
        else:
            high = mid - 1       # search left half
    return -1                    # not in array

arr = [2, 5, 8, 12, 16, 23, 38, 45]
print(binary_search(arr, 23))    # Output: 5
```

**Step 4 — Complexity:**
- **Time: O(log n)** — each step discards half the remaining elements.
  1 million elements = at most 20 comparisons (log₂ 1,000,000 ≈ 20).
  1 billion elements = at most 30 comparisons.
- **Space: O(1)** iterative — only `low`, `high`, `mid` stored.
  Recursive version uses O(log n) call-stack space.

**Step 5 — Interview Summary:**
Binary Search finds a target in a sorted array in O(log n) time by
repeatedly halving the search space using low, high, and mid pointers.
The critical precondition is a sorted array — violating this produces
wrong results without any error. Common follow-ups: finding first/last
occurrence of duplicates, or applying Binary Search on an answer range
(e.g., square root, minimum in rotated array).

---

## Response — ChatGPT (free)

**Step 1 — One-sentence definition:**
Binary Search efficiently locates a target in a sorted array by halving
the search range with each comparison.

**Step 2 — Most important precondition:**
The input array must be sorted. Binary Search relies on sorted order to
decide which half to eliminate — without it the algorithm breaks entirely.

**Step 3 — Python code:**

```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

arr = [1, 4, 7, 10, 15, 20, 30]
print(binary_search(arr, 15))  # Output: 4
```

**Step 4 — Complexity:**
- **Time: O(log n)** — each step eliminates half the array. n = 8 needs
  at most 3 steps (log₂8 = 3). A million elements needs only ~20 steps.
- **Space: O(1)** iterative. Recursive uses O(log n) stack frames —
  one per recursive call.

**Step 5 — 3-sentence summary:**
Binary Search is a divide-and-conquer algorithm that searches a sorted
array in O(log n) time by narrowing the window using low, mid, and high
pointers. Always state the sorted precondition first — interviewers
specifically test for this. Prepare for follow-ups on duplicates,
rotated arrays, and answer-space Binary Search problems.

---

## Comparison — Pattern 3 (CHAIN-OF-THOUGHT)

| Aspect | Claude.ai | ChatGPT |
|---|---|---|
| All 5 steps followed | Yes | Yes |
| Complexity reasoning depth | 1M and 1B element examples | 8-element log₂8 = 3 example |
| Code comments | Inline comments explaining each branch | Minimal, clean |
| Follow-up variants in summary | 3 variants named | 3 variants named |
| Tone | More detailed and thorough | Slightly more concise |

**Self-Score (Claude): 5/5**
**Self-Score (ChatGPT): 5/5**

Chain-of-thought produced the most complete responses from both tools.
Both followed all 5 explicit steps and showed reasoning transparently.
Key teaching observation: CoT is a reliable pattern that levels up both
tools equally — the step-by-step instruction removes ambiguity about
what the output should contain.

---

---

# PATTERN 4 — STRUCTURED OUTPUT

## Prompt Written (same prompt run on BOTH tools)

```
Explain Binary Search for a placement interview. Return ONLY valid JSON
with this exact shape — no markdown fences, no commentary:

{
  "definition": "one-sentence definition",
  "precondition": "the one condition that must be true",
  "intuition": "a concrete real-world analogy",
  "code_example": "Python snippet showing iterative binary search",
  "time_complexity": "complexity class with one-line reasoning",
  "space_complexity": "complexity class with one-line reasoning",
  "common_pitfall": "what students most often get wrong",
  "interview_follow_up": "a follow-up question an interviewer will likely ask"
}
```

---

## Response — Claude.ai (free)

> **Lab Note:** Claude.ai added ```json fences despite being told not to.
> Content inside fences is shown. This is the known fence-compliance bug
> flagged in the trainer notes — to be fixed with response_schema + Pydantic in Lab 2B.

```json
{
  "definition": "Binary Search finds a target value in a sorted array by repeatedly halving the search space.",
  "precondition": "The array must be sorted in ascending order before Binary Search can be applied.",
  "intuition": "Like finding a word in a dictionary — open to the middle, decide which half the word is in, discard the other, repeat.",
  "code_example": "def binary_search(arr, target):\n    low, high = 0, len(arr) - 1\n    while low <= high:\n        mid = (low + high) // 2\n        if arr[mid] == target:\n            return mid\n        elif arr[mid] < target:\n            low = mid + 1\n        else:\n            high = mid - 1\n    return -1",
  "time_complexity": "O(log n) — each iteration eliminates half the remaining elements.",
  "space_complexity": "O(1) — only three integer variables (low, high, mid) are used.",
  "common_pitfall": "Forgetting to verify the array is sorted, or applying Binary Search on an unsorted array which produces silently incorrect results.",
  "interview_follow_up": "How would you modify Binary Search to find the first occurrence of a duplicate element in a sorted array?"
}
```

---

## Response — ChatGPT (free)

> **Lab Note:** ChatGPT also added ```json fences despite the same instruction.
> Consistent behaviour across both free-tier tools — confirms this cannot
> be fixed by prompt text alone.

```json
{
  "definition": "Binary Search is an algorithm that locates a target in a sorted array by halving the search space at each step.",
  "precondition": "The array must be sorted in ascending (or descending) order before applying Binary Search.",
  "intuition": "Like guessing a number between 1 and 100 — always guess the midpoint, and the other person says higher or lower, eliminating half the range each time.",
  "code_example": "def binary_search(arr, target):\n    low, high = 0, len(arr) - 1\n    while low <= high:\n        mid = (low + high) // 2\n        if arr[mid] == target:\n            return mid\n        elif arr[mid] < target:\n            low = mid + 1\n        else:\n            high = mid - 1\n    return -1",
  "time_complexity": "O(log n) — with each comparison the problem size is cut in half.",
  "space_complexity": "O(1) — iterative approach uses constant extra memory.",
  "common_pitfall": "Using Binary Search on an unsorted array, or computing mid as (low + high) / 2 in languages where integer overflow can occur — use low + (high - low) // 2 instead.",
  "interview_follow_up": "Can you implement Binary Search recursively and compare the space complexity of recursive vs iterative versions?"
}
```

---

## Comparison — Pattern 4 (STRUCTURED OUTPUT)

| Aspect | Claude.ai | ChatGPT |
|---|---|---|
| All 8 JSON fields present | Yes | Yes |
| "No fences" instruction obeyed | No — fences added anyway | No — fences added anyway |
| Intuition analogy | Dictionary | Guessing game (higher/lower) |
| Common pitfall depth | Unsorted array risk | Unsorted array + integer overflow risk |
| Follow-up question | Duplicate first-occurrence variant | Recursive vs iterative space complexity |

**Self-Score (Claude): 4/5**
**Self-Score (ChatGPT): 4/5**

Both tools produced valid, complete JSON. Both ignored the "no fences"
instruction — a consistent free-tier limitation confirmed across tools.
ChatGPT's pitfall answer flagged integer overflow in mid calculation, a
senior-level insight the prompt did not ask for. Both scores docked 1
point for fence non-compliance, which must be fixed programmatically
in Lab 2B.

---

---

# PATTERN 5 — SYSTEM PROMPT

## System Prompt (set in Custom Instructions on BOTH tools)

```
You are a senior placement coach for B.Tech CSE students at an engineering
college in Andhra Pradesh. You prepare students specifically for TCS,
Infosys, Wipro, and HCL campus drives. You explain every technical concept
in 60-80 words maximum, conversational tone, with one concrete code snippet
and one interview tip. Never exceed 80 words in your explanation paragraph.
```

## User Prompt (minimal — same on both tools, new chat)

```
Explain Binary Search.
```

---

## Response — Claude.ai (free)

Binary Search finds a target in a **sorted array** by halving the search
space each step. Compare the middle — go right if target is bigger, left
if smaller.

```python
mid = (low + high) // 2
if arr[mid] == target: return mid
elif arr[mid] < target: low = mid + 1
else: high = mid - 1
```

**Time: O(log n) | Space: O(1)**

**Interview tip:** Say "array must be sorted" before writing any code —
interviewers dock marks if you skip the precondition.

*(~68 words — within limit)*

---

## Response — ChatGPT (free)

Binary Search works on a **sorted array**. Check the middle element —
match means done, larger target means search right, smaller means
search left. Repeat until found.

```python
mid = (low + high) // 2
if arr[mid] == target: return mid
elif arr[mid] < target: low = mid + 1
else: high = mid - 1
```

**Time: O(log n) | Space: O(1)**

**Interview tip:** Always state the sorted precondition upfront — it is
the first thing your interviewer listens for before letting you write code.

*(~65 words — within limit)*

---

## Comparison — Pattern 5 (SYSTEM PROMPT)

| Aspect | Claude.ai | ChatGPT |
|---|---|---|
| Word limit respected (60-80) | Yes (~68 words) | Yes (~65 words) |
| Conversational tone | Yes | Yes |
| Code snippet included | Yes | Yes |
| Interview tip included | Yes | Yes |
| Domain-awareness | "Dock marks" framing shows placement context | "First thing interviewer listens for" — equally domain-aware |

**Self-Score (Claude): 4/5**
**Self-Score (ChatGPT): 4/5**

The system prompt pattern produced identical quality from both tools
with just a 3-word user message. This is the most efficient daily-use
pattern for a mentor — set context once in Custom Instructions, then
ask any topic. Both tools respected the word limit, included the code
snippet and interview tip exactly as the system prompt specified.

---

---

# PATTERN 6 — PROMPT CHAINING

*3 separate conversations on BOTH tools — 6 conversations total*

---

## CLAUDE — Conversation 1 (Extract)

**Prompt:**
```
List the 5 most important sub-concepts a B.Tech student must understand
about Binary Search for a placement interview. Just the list, no explanation.
```

**Output saved (Claude):**
1. Precondition: array must be sorted
2. Core logic: low / high / mid pointer mechanics
3. Time complexity: O(log n) and why
4. Space complexity: O(1) iterative vs O(log n) recursive
5. Variants: first/last occurrence of a duplicate in sorted array

---

## CLAUDE — Conversation 2 (Expand)

**Prompt:**
```
For each of these 5 sub-concepts of Binary Search, write a 1-paragraph
explanation tailored to a 3rd-year B.Tech CSE student preparing for
TCS, Infosys, or Wipro placement interviews:

1. Precondition: array must be sorted
2. Core logic: low / high / mid pointer mechanics
3. Time complexity: O(log n) and why
4. Space complexity: O(1) iterative vs O(log n) recursive
5. Variants: first/last occurrence of a duplicate in sorted array
```

**Output saved (Claude):**

**1. Precondition:**
Binary Search has exactly one hard requirement: the input array must be
sorted. If unsorted, the algorithm may eliminate the half that contains
the target and return -1 even when the element exists. In your interview,
state this precondition before touching the code — TCS and Infosys
interviewers specifically watch for this to filter prepared candidates
from those who have just memorised a template.

**2. Core Logic:**
The algorithm uses three variables — `low` (start index), `high` (end
index), and `mid = (low + high) // 2`. At each step, compare `arr[mid]`
with the target. If equal, return `mid`. If target is greater, set
`low = mid + 1` (discard left half). If target is smaller, set
`high = mid - 1` (discard right half). Loop continues while `low <= high`.
When they cross, the element is not in the array.

**3. Time Complexity:**
Each comparison eliminates exactly half the remaining elements. Starting
from n: step 1 leaves n/2, step 2 leaves n/4, step k leaves n/2^k.
Algorithm stops when n/2^k = 1, so k = log2(n). In practice: searching
1 billion sorted records takes at most 30 comparisons. Always derive this
in the interview — Wipro interviewers often ask you to justify, not just
state the complexity.

**4. Space Complexity:**
The iterative version uses exactly three integer variables regardless of
input size: O(1) constant space. The recursive version makes one function
call per halving — each call sits on the call stack until base case,
consuming O(log n) stack frames. In interviews, implement iterative by
default unless explicitly asked for recursion — it shows awareness of
stack overflow risk on very large inputs.

**5. Variants:**
A common follow-up: "Find the first or last occurrence of a repeated
element in [1, 2, 2, 2, 3, 4]." When `arr[mid] == target`, do not return
immediately. For first occurrence, record the index and continue left
(`high = mid - 1`). For last occurrence, record and continue right
(`low = mid + 1`). Return the recorded index at the end. This tests
whether you understand the algorithm deeply enough to modify it — exactly
what Cognizant and Wipro test in coding rounds.

---

## CLAUDE — Conversation 3 (Polish)

**Prompt:**
```
Synthesise these 5 paragraphs into ONE concise 80-word interview-prep
explanation of Binary Search. Preserve all 5 sub-concepts. Conversational
tone. End with one practice question.

[pasted the 5 paragraphs from Conversation 2]
```

**Final Output (Claude):**

Binary Search finds a target in a **sorted array** — state this precondition
first. It uses `low`, `high`, and `mid = (low+high)//2` pointers, discarding
half the array each step. Time: **O(log n)** (30 steps finds 1 in a billion).
Use iterative for **O(1) space**; recursive adds O(log n) stack. For
duplicates, keep searching after a match — left for first occurrence,
right for last.

**Practice question:** Find the last occurrence of `2` in `[1,2,2,2,3,4]`
using Binary Search.

---

## CHATGPT — Conversation 1 (Extract)

**Prompt:** *(same as Claude Conversation 1)*

**Output saved (ChatGPT):**
1. Sorted array precondition
2. Pointer mechanics: low, mid, high
3. Time complexity: O(log n) derivation
4. Space: iterative O(1) vs recursive O(log n)
5. Answer-space Binary Search (e.g., integer square root, peak element)

> **Note:** ChatGPT chose "answer-space Binary Search" as sub-concept 5
> instead of "duplicate variants." Both are valid — this divergence shows
> that even Conversation 1 shapes the entire downstream chain differently
> between tools. An interesting structural difference to flag.

---

## CHATGPT — Conversation 2 (Expand)

**Prompt:** *(same structure, using ChatGPT's 5 sub-concepts)*

**Output saved (ChatGPT):**

**1. Sorted Array Precondition:**
The correctness of Binary Search rests entirely on one guarantee: the
array is sorted. Without it, comparing `arr[mid]` to the target gives
no information about which half to eliminate. Always lead your interview
answer with this constraint — even before describing the algorithm.
Interviewers intentionally wait for this before letting you write code.

**2. Pointer Mechanics:**
Binary Search tracks three indices: `low` (leftmost boundary), `high`
(rightmost boundary), and `mid = (low + high) // 2`. Each iteration,
compare `arr[mid]` to the target. Match — return index. Target larger
— `low = mid + 1`. Target smaller — `high = mid - 1`. The loop ends
when `low > high`. Note: always use `//` (floor division) for mid in
Python — do not use `/`.

**3. Time Complexity:**
At each step, Binary Search discards exactly half the remaining search
space. Starting from n elements, after k steps we have n/2^k elements.
Algorithm ends when n/2^k = 1, giving k = log2(n). Worst case: O(log n)
comparisons. To illustrate: 2^30 = ~1 billion, meaning only 30 steps
to search over a billion elements. This is why interviewers consider it
the benchmark for efficient search.

**4. Space Complexity:**
The iterative implementation uses O(1) space — just three variables.
The recursive version allocates a new stack frame for each recursive
call. Since recursion depth equals O(log n), space usage is O(log n).
For interviews, prefer iterative: it is memory-safe, avoids stack
overflow on massive arrays, and shows you understand the trade-off
between the two approaches.

**5. Answer-Space Binary Search:**
A more advanced pattern: sometimes you search a range of possible
answers, not an array. Example — find the integer square root of n.
Instead of checking 1 to n linearly, Binary Search the answer space:
if `mid*mid <= n`, go right; else go left. This pattern appears in
problems like minimum capacity to ship packages in D days, or finding
peak element. Mentioning this in an interview separates strong candidates
from the rest.

---

## CHATGPT — Conversation 3 (Polish)

**Prompt:** *(same polish prompt, using ChatGPT's expanded paragraphs)*

**Final Output (ChatGPT):**

Binary Search requires a **sorted array** — state this before anything else.
It tracks `low`, `high`, and `mid = (low+high)//2`, eliminating half the
array per step. Time: **O(log n)** — just 30 comparisons for 1 billion
elements. Use iterative for **O(1) space** (recursive costs O(log n) stack).
Advanced variant: search the *answer space*, not the array — e.g., integer
square root, minimum capacity problems.

**Practice question:** How would you find the minimum element in a
rotated sorted array like `[4, 5, 6, 1, 2, 3]` using Binary Search?

---

## Comparison — Pattern 6 (PROMPT CHAINING)

| Aspect | Claude (3-chain) | ChatGPT (3-chain) |
|---|---|---|
| Sub-concept 5 chosen | Duplicate first/last occurrence | Answer-space Binary Search |
| Conversation 2 depth | Strong — interview-contextual framing per concept | Strong — more mathematical derivation per concept |
| Final polish quality | All 5 concepts preserved, ~80 words | All 5 concepts preserved, ~80 words |
| Practice question difficulty | Standard (duplicate in sorted array) | Higher difficulty (rotated array) |
| Chain consistency | Conv 1 concepts flowed cleanly into Conv 3 | Conv 1 concepts flowed cleanly into Conv 3 |

**Self-Score (Claude): 5/5**
**Self-Score (ChatGPT): 5/5**

Prompt chaining produced the deepest, most structured explanations from
both tools — quality no single prompt could match. The key finding:
the two tools diverged at sub-concept 5 in Conversation 1, which led to
genuinely different final outputs. This is actually useful for a mentor
— run the chain on both tools to get two different pedagogical angles on
the same topic, then share both framings with students.

---

---

# CROSS-TOOL OBSERVATIONS

| Finding | Detail |
|---|---|
| **Where tools were equal** | Patterns 3, 5, 6 — CoT, System Prompt, and Chaining gave near-identical quality on both tools |
| **Where Claude had an edge** | Pattern 1 — warmer tone, more locally contextualised for Indian students |
| **Where ChatGPT had an edge** | Pattern 4 — flagged integer overflow in mid-calculation (unsolicited senior insight); Pattern 6 — chose a harder and more advanced 5th sub-concept (answer-space Binary Search) |
| **Consistent bug across both** | Pattern 4 — both tools added json fences despite being told not to. Free-tier limitation; requires response_schema enforcement in Lab 2B |
| **Most efficient daily pattern** | Pattern 5 (System Prompt) — both tools consistently respected word limit, tone, and domain-context from a 3-word user message |
| **Best for complex topics** | Pattern 6 (Chaining) — both tools produced significantly deeper output through 3-step decomposition |

---

---

# PEER-SCORE SUMMARY

*(To be completed by peer scorer after swapping scratch docs)*

| Pattern | Clarity (0-2) | Context (0-2) | Specificity (0-2) | Format (0-2) | Verification (0-2) | Total (/10) | Pass? (>=7) |
|---|---|---|---|---|---|---|---|
| 1 — PERSONA | | | | | | | |
| 2 — FEW-SHOT | | | | | | | |
| 3 — CHAIN-OF-THOUGHT | | | | | | | |
| 4 — STRUCTURED OUTPUT | | | | | | | |
| 5 — SYSTEM PROMPT | | | | | | | |
| 6 — PROMPT CHAINING | | | | | | | |

**Peer scorer name:** ___________________
**Disagreements noted:** ___________________

---

---

# SELF-SCORE SUMMARY

| Pattern | Claude (1-5) | ChatGPT (1-5) | Key Observation |
|---|---|---|---|
| 1 — PERSONA | 5 | 5 | Both warm; Claude more emotional, ChatGPT gave ready-to-speak script |
| 2 — FEW-SHOT | 4 | 4 | Both inherited format correctly; both skipped code since examples had none |
| 3 — CHAIN-OF-THOUGHT | 5 | 5 | Both followed all 5 steps; CoT is a reliable leveller across tools |
| 4 — STRUCTURED OUTPUT | 4 | 4 | Valid JSON from both; both ignored "no fences" — needs Lab 2B fix |
| 5 — SYSTEM PROMPT | 5 | 5 | 3-word prompt gave full coaching output on both; highest efficiency |
| 6 — PROMPT CHAINING | 5 | 5 | Both produced deepest output; tools diverged at sub-concept 5, giving two useful angles |

---

---

# REFLECTION PARAGRAPH

For my placement-prep students, the patterns I will use most are
**Pattern 5 (System Prompt)** and **Pattern 6 (Prompt Chaining)**.

I will use **System Prompt** because I teach the same student profile every
day — B.Tech CSE, 3rd year, preparing for TCS/Infosys/Wipro. Setting the
coaching persona once in Custom Instructions on both Claude and ChatGPT
means every subsequent question ("Explain recursion," "Explain hashing,"
"What is a BST?") automatically gets a domain-aware, word-limited,
interview-ready answer without me rewriting context each time. This pattern
directly multiplies how many concepts I can cover per coaching session on
either tool.

I will use **Prompt Chaining** for complex, multi-layered topics like
Dynamic Programming, Graph algorithms, or OS concepts, where a single
prompt produces surface-level answers. The 3-step Extract to Expand to
Polish chain forces the AI to first identify the real sub-concepts, then
develop each with depth, then compress into something students can study
and remember. Running this chain on both Claude and ChatGPT — as this lab
showed — sometimes produces different sub-concept choices at step 1,
giving me two pedagogically distinct explanations of the same topic that
I can share as "two ways to think about this."

