GNU Screen Notes
================

No vertical split support for Screen 4.0 unless apply patch.
Alternatively, use 4.1.


Basics
------

Note: ^ means control

Create new screen

    ^a c

Split screen horizontally

    ^a S

Switch between screens
    
    ^a tab

Remove region
    
    ^a x


Attach / Detach
---------------

Pick from sessions

    $ screen -r

Detach

    ^a d


Todo
----

Source: http://stackoverflow.com/questions/70614/gnu-screen-survival-guide

    ^A ^W - window list, where am I
    ^A ^C - create new window
    ^A space - next window
    ^A p - previous window
    ^A ^A - switch to previous screen (toggle)
    ^A [0-9] - go to window [0-9]
    ^A esc - copy mode, which I use for scrollback

Etc:

http://aperiodic.net/screen/quick_reference#split_screen



