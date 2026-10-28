# ReDoS Backtracking Lab

An interactive, browser-based teaching module for **SE/CprE 4210, Learning Sprint #3, Problem 5**.

## What it teaches

The visualization demonstrates the algorithmic complexity risk behind regular-expression denial of service (ReDoS). It uses the example `^(a+)+$` and shows why a string of repeated `a` characters followed by an invalid `!` may require a backtracking engine to explore many potential groupings.

For `n` repeated letters, there are `2^(n-1)` possible partitions into consecutive nonempty groups. This is an **illustrative combinatorial model**, not a timing benchmark or an exact trace of Java's regex implementation.

## Running the app

1. Download or clone this repository.
2. Open `dist/index.html` in Chrome, Edge, Firefox, or another modern browser.
3. No installation, server, API key, or internet connection is required.

## How to interact

- Move the slider to change the number of `a` characters (4–16).
- Switch between a valid string and an invalid string ending in `!`.
- Observe the possible groupings and the logarithmically scaled bar chart.
- Click **Next grouping** to see alternative ways the `a` characters can be partitioned.
- Click **Reset** to return to the initial example.

## Safety and limitations

The visualization does **not** execute a vulnerable regular expression on user-controlled input. It simulates and counts a bounded set of possibilities, avoiding the browser-freezing behavior associated with real ReDoS. Its counts describe potential groupings, not the exact number of steps Java or JavaScript takes.
