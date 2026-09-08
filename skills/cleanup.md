# Cleanup mode

Use only when cleanup is explicitly requested. This is an IMPLEMENTATION mode:
state the cleanup plan and files, then wait for approval before editing.

Allowed work is behavior-preserving removal or simplification: dead code,
unused imports, variables, functions, types, obsolete comments/docstrings, and
local redundancy.

Do not make functional, API, architectural, dependency, or feature changes. If
the cleanup exposes a behavior question, stop and ask rather than folding a fix
into the cleanup. Report what was removed, validation, and any area intentionally
left untouched.
