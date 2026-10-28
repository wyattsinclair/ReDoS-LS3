# Reflection — ReDoS Backtracking Lab

Creating this visualization helped me understand why a small change to an input can have a large effect on an algorithm's running time. In Module 5, we learned that the regex `^(a+)+$` can have many possible ways to divide a sequence of `a` characters. The interactive grouping display made it easier to see why a final invalid character matters. When the input matches, the engine can accept a successful path; when the input fails at the end, it may have to reconsider many earlier decisions.

I used an AI-assisted development workflow to plan the interface and generate the initial HTML, CSS, and JavaScript. I then reviewed the explanation against the course slides and focused the controls on one main concept: changing the input length and watching the possible groupings grow. The slider makes the exponential relationship visible, and the Next Grouping button shows how the same characters can be separated in different ways.

An important design decision was to simulate the possible groupings rather than run a dangerous regular expression repeatedly. This lets users explore the vulnerability without freezing their browser. I also learned to distinguish a theoretical count of possible groupings from actual runtime measurements: the visualization shows why backtracking can be costly, but it does not claim to measure the exact number of engine operations.


