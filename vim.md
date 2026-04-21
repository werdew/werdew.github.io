Normal mode:

undo:u
redo: Ctrl + r

Creating macros:
start recording -> q
choose register -> a (example)
record actions -> jxx (down and delete two characters)
stop recording -> q

run macro 10x -> 10@a


Visual block option:
Go to the first line
Press Ctrl+v (block visual mode)
Select down 10 lines (9j)
Move right 1 chars (l)
Press d

subsitute/replace
```vim
:%s/current_string/substitute_string
```
you can also use # as a delimiter in case you use / in the string

run commands:
```vim
:g#^</code></pre>$#d
```

:g → run a command on all matching lines
^ → start of line
$ → end of line (ensures nothing else is on the line)
d → delete the line


(remove) the pattern everywhere
```vim
:%s/pattern//g
```
% → whole file
s → substitute
pattern → what you match
empty replacement (//) → deletes it
g → all occurrences per line
