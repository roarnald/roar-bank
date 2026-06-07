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

## 🎯 Known problem-specific tricks

- **MinAvgTwoSlice:** the minimal-average slice is always length **2 or 3** — only check those. O(N).
- **MaxCounters:** don't rewrite all counters on "max" — track a lazy `floor` + `currentMax`, apply floor at the end. O(N+M).
- **OddOccurrences:** XOR everything (`acc ^ x`) → pairs cancel, odd one remains. O(1) space.
- **CountDiv:** `floor(B/K) - floor((A-1)/K)` — handles `A=0` and inclusive ends cleanly.
- **MissingInteger / PermCheck:** use a `Set`; check range + duplicates, not just `max === length`.
- **Rotation:** always reduce `K % N` first; guard `N = 0`.

---

> **Bottom line:** thinking is solid — tighten *mechanical discipline*. Compile before submitting, watch boundaries, kill spreads, re-read the "returns ..." sentence right before writing `return`.
