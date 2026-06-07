# Codility Pre-Submit Checklist

A 60-second ritual to run before submitting **any** Codility task.
Built from recurring bug patterns — the algorithms are usually right; the last 5% (typos + edges + perf) is where points leak.

---

## ✅ The 60-second ritual

1. **Compile it.** Hit run once. Catches rename-mismatches and dead code for free.
2. **Find every `return`.** Does the main path return the *computed* variable the prompt actually asked for? Any path that falls through to `undefined`?
3. **Grep for `...` (spread).** `Math.min(...A)`, `Math.max(...A)`, `push(...arr)` blow the stack at N=100,000. Replace with a loop or `.size`.
4. **Say the boundaries out loud.** Inclusive or exclusive? Does my loop / `slice` include the last element? (`slice(P, Q)` drops `Q` — use `Q+1` for inclusive.)
5. **Test 3 edge inputs in your head:** empty / size-1, the value `0`, and the maximum (`K > N`, duplicates, all-same).
6. **Delete debug `console.log`.**

---

## 🐛 My recurring bug signature

| # | Pattern | Example slip |
|---|---------|--------------|
| 1 | **Rename mismatch** — renamed a var but missed its uses | `i` vs `target`; `x` vs `item` |
| 2 | **Wrong / missing return** — returns related-but-wrong value, or falls off the end | `return 0` instead of `return largest`; returned the *average* instead of its *index* |
| 3 | **Operator direction** — `>` vs `<` for min/max | used `>` while tracking a minimum |
| 4 | **Inclusive vs exclusive boundary** | `slice(P, Q)` missing `+1`; loop runs one too far/short |
| 5 | **Spread footgun** at large N | `Math.min/max(...A)`, `push(...arr)` → stack overflow |
| 6 | **`.size` vs materializing** | `[...set].length` instead of `set.size` |
| 7 | **Edge values** | `K > N` needs `% N`; `A = 0` negative modulo; odd-count > 1 |
| 8 | **Leftover `console.log`** | debug noise + tiny perf cost |
| 9 | **"more than half" boundary** | `ceil(N/2)` + `>=` wrongly accepts exactly-half on even N → use strict `count * 2 > N` |
| 10 | **Window index gaps** | summing a fixed window must use consecutive indices `p, p+1, p+2` — `p+3` is a typo (and can read `undefined` → `NaN`, which silently skips) |

---

## ⚡ Performance instinct

- See **"M queries / M operations"** over an array of size N? Ask: *am I doing O(N) work per query?*
  → If yes, that's **O(N·M)** → **precompute** so each query is O(1).
- Avoid repeating work inside a loop (e.g. re-scanning, `Math.max` on every operation).

---

## 📐 Prefix sums (precalc) — the mental model

- **One sentence:** `prefix[i]` = "the answer for everything **up to** position `i`."
- **Range query = two rulers, subtracted:** measure from `0` twice, take the difference.
  ```
  count in [lo..hi] = prefix[hi+1] - prefix[lo]      (leading-zero style — preferred)
  count in [lo..hi] = prefix[hi] - (lo>0 ? prefix[lo-1] : 0)   (inclusive style — needs guard)
  ```
- **Pick ONE convention and stamp it.** Leading-zero style (array length `N+1`, `prefix[0]=0`) avoids the `lo-1 = -1` edge case.
- **Build = copy the neighbor, then nudge:** `prefix[i] = prefix[i-1] + (new thing at i)`.
  If your build loops *forward* to the end per element → that's O(N²); lean on the previous cell instead.

---

## 🥞 Stack pattern (Fish, StoneWall, brackets, stock spans)

- **Shape:** keep a stack of *unresolved* items in **monotonic order**; when a new element arrives, **pop the ones it invalidates**, then decide what to do with the survivor on top.
- **Always guard emptiness first** in the `while`: `while (stack.length > 0 && top <relation> x)`. Reading the top of an empty stack gives `undefined` → broken comparisons. The `length > 0` short-circuits it.
- **Amortized O(N):** each item is pushed once and popped once → ≤ 2N ops, even though the inner `while` looks nested.
- **Fish:** stack of downstream fish; each upstream fish pops smaller ones (eats) or hits a bigger one (dies). Survivors = counted + stack left.
- **StoneWall:** stack of open block heights (increasing); pop taller-than-current, then reuse if top === h else push + count.

---

## 📊 Running-count split (TapeEquilibrium, EquiLeader)

- Track a quantity on the **left** as you sweep; derive the **right** by subtraction: `right = total - left`. (Same two-rulers idea as prefix sums.)
- **EquiLeader = Dominator + this sweep:** find the global leader first; a split `S` is an equi-leader iff the leader is a strict majority in *both* halves (`leftCount*2 > leftLen && rightCount*2 > rightLen`).

---

## 🔢 Float-precision rule

- **Dividing an integer by 2 is EXACT** — halves are representable in binary. `count > len/2` is safe. (I over-feared this once.)
- The trap is **non-power-of-2 division** (`/3`, averages) and accumulated decimals (`0.1 + 0.2 !== 0.3`). There, cross-multiply into integers: `a/b > c/d` → `a*d > c*b`.
- Habit: prefer the integer form anyway (`count*2 > len`) — keeps the `>` vs `>=` boundary crisp and transfers to the cases that *do* need it.

---

## 🎯 Known problem-specific tricks

- **MinAvgTwoSlice:** the minimal-average slice is always length **2 or 3** — only check those. O(N).
- **MaxCounters:** don't rewrite all counters on "max" — track a lazy `floor` + `currentMax`, apply floor at the end. O(N+M).
- **OddOccurrences:** XOR everything (`acc ^ x`) → pairs cancel, odd one remains. O(1) space.
- **CountDiv:** `floor(B/K) - floor((A-1)/K)` — handles `A=0` and inclusive ends cleanly.
- **MissingInteger / PermCheck:** use a `Set`; check range + duplicates, not just `max === length`.
- **Rotation:** always reduce `K % N` first; guard `N = 0`.
- **MaxProductOfThree:** sort, then `max(top3, bottom2 × top1)` — two negatives can beat three positives. Use a **numeric comparator** `(a,b)=>a-b`.
- **Triangle:** sort, check **consecutive** triplets; only `A[i]+A[i+1] > A[i+2]` matters. Loop bound must reach `i = N-3` → `i < N-2`.
- **Dominator / EquiLeader:** leader = strict majority (`count*2 > N`). If no leader, EquiLeader answer is 0.
- **PassingCars:** scan once; each west car (`1`) pairs with all east cars (`0`) seen so far → add running `eastSeen`. Cap at 1e9 → -1.
- **GenomicRange:** 4 prefix-count arrays (one per nucleotide); per query check A→C→G→T, first present = min impact.

---

> **Bottom line:** thinking is solid — tighten *mechanical discipline*. Compile before submitting, watch boundaries, kill spreads, re-read the "returns ..." sentence right before writing `return`.
