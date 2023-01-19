In Java and Python 3.11+, quantifiers may be made possessive by appending a plus sign, which disables backing off (in a backtracking engine), even if doing so would allow the overall match to succeed: While the regex ".*" applied to the string

"Ganymede," he continued, "is the largest moon in the Solar System."
matches the entire line, the regex ".*+" does not match at all, because .*+ consumes the entire input, including the final ". Thus, possessive quantifiers are most useful with negated character classes, e.g. "[^"]*+", which matches "Ganymede," when applied to the same string.

Another common extension serving the same function is atomic grouping, which disables backtracking for a parenthesized group. The typical syntax is (?>group). For example, while ^(wi|w)i$ matches both wi and wii, ^(?>wi|w)i$ only matches wii because the engine is forbidden from backtracking and so cannot try setting the group to "w" after matching "wi".

Possessive quantifiers are easier to implement than greedy and lazy quantifiers, and are typically more efficient at runtime