E Mail Regex Tutorial

To validate email addresses, we use a regex pattern that checks for a proper structure. Here’s a pattern: ^([a-zA-Z0-9._%+-]+)@([a-zA-Z0-9.-]+)\.([a-zA-Z]{2,})(?:\.([a-zA-Z]{2}))?$. Let’s break down how this pattern works using key features.

Summary

The regex pattern ^([a-zA-Z0-9._%+-]+)@([a-zA-Z0-9.-]+)\.([a-zA-Z]{2,})(?:\.([a-zA-Z]{2}))?$ validates email addresses by splitting them into parts and checking each part with different rules.

Regex Breakdown
Anchors

^ and $: These anchors ensure that we check the entire email address from start (^) to end ($).
Quantifiers

+: In ([a-zA-Z0-9._%+-]+), the + means "one or more" of the characters in the brackets. This ensures the local part has at least one character.
{2,}: In ([a-zA-Z]{2,}), {2,} means "two or more" letters, making sure the top-level domain has at least two letters.
?: In (?:\.([a-zA-Z]{2}))?, the ? makes the extra domain part optional (like .uk in .co.uk). It’s lazy, meaning it will only match if it’s there.

Grouping

([a-zA-Z0-9._%+-]+): This captures the local part of the email. It allows letters, numbers, dots, underscores, percent signs, plus signs, and hyphens.
@: Separates the local part from the domain part.
([a-zA-Z0-9.-]+): This captures the domain part. It includes letters, numbers, dots, and hyphens.
.([a-zA-Z]{2,}): Captures the top-level domain (TLD) after a dot, with at least two letters.
(?:.([a-zA-Z]{2}))?: Optionally captures a second-level domain (like .uk in .co.uk) after another dot.

Bracket Expressions

[a-zA-Z0-9._%+-]: Matches any letter (uppercase or lowercase), digit, dot (.), underscore (_), percent sign (%), plus sign (+), or hyphen (-) in the local part.
[a-zA-Z0-9.-]: Matches letters, digits, dots, and hyphens in the domain part.
Character Classes

[a-zA-Z]: Matches any letter (uppercase or lowercase).

Example
Here’s how this pattern works with different email addresses:

Valid:
user@example.com
Local part: user
Domain: example
TLD: com
user.name@sub-domain.co
Local part: user.name
Domain: sub-domain
TLD: co
user.name@domain.com.au
Local part: user.name
Domain: domain
TLD: com
Extra: au
user123@domain.co.uk
Local part: user123
Domain: domain
TLD: co
Extra: uk
Invalid:
user@domain..com (invalid due to double dots in the domain)
user@domain (missing TLD)
user@-domain.com (invalid due to leading hyphen in the domain)

Author
Check out my projects on GitHub: https://github.com/ekookten?tab=repositories