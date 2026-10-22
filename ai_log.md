# AI log: Lab 3, fit_zipf

Your name: Nghia Tran

Tool: ChatGPT Edu

## The prompt I gave it

(paste your prompt here, including the docstring)
    """Fit c_k = C * k**m to the counts of ranks kmin to kmax.

    c: numpy array of word counts, largest first; c[0] is rank 1.
    kmin, kmax: the first and last rank to fit; both are included.
    Fits a straight line, log10(c_k) = m * log10(k) + b, by least
    squares (np.polyfit) to the ranks k = kmin, kmin + 1, ..., kmax.
    Returns (m, C), where C = 10**b.

    Examples (rounded to 6 decimal places):
    fit_zipf(np.array([600, 300, 200, 150]), 1, 4)
        returns (-1.0, 600.0)
    fit_zipf(np.array([5000, 900, 400, 1]), 2, 3)
        returns (-2.0, 3600.0)
    """
## The code it gave me

(paste its answer here)
ranks = np.arange(kmin, kmax + 1)
selected_counts = c[kmin - 1:kmax]
x = np.log10(ranks)
y = np.log10(selected_counts)
m, b = np.polyfit(x, y, 1)
C = 10 ** b
return m, C
## What I checked

- Example 1, `fit_zipf(np.array([600, 300, 200, 150]), 1, 4)`: I got 
    Example 1: (-1.0, 600.0) — Passed
- Example 2, `fit_zipf(np.array([5000, 900, 400, 1]), 2, 3)`: I got
    Example 2: (-2.0, 3600.0) — Passed
- Anything else I checked:

## What I changed, and why

(write "nothing" if you used it as is; you must still be able to explain every line)
