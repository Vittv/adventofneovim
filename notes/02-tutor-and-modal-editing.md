# II - Tutor and Modal Editing

Press :Tutor to open Tutor

Tutor is the Neovim Tutorial which will walk us through a lot of very important concepts.

## 1. Moving around

- Never use the arrows keys
- Get used to moving around with HJKL
```
H - left
J - down
K - up
L - right
```
Another way to quit vim is to `:q!`.

> The "!" indicates that something really should be done, just like in CSS' "!important"

## 2. Appending commands

Lowercase `a` can be used to move to the next character

Capital A can be used to go to the end of a line and entering `INSERT` mode

> In a lot of cases, a capitalized version of a command, such as `A`, is a stronger version of such command.

## 3. Deletion commands

- `x` deletes a single character, unless a line or block is targeted.
- `dw` deletes a word.
- `d$` deletes to the end of the line.
- `dd` deletes a line.

Because $ goes to the end of the line, not to confused with A, A specifically starts `INSERT` at the end of the line.

Same case with `d0` since 0 represents the start of an array, it also puts you at the start of a line, thus `d0` would delete to the start of the line.

## 4. Operators and Motions

Operators are the main action, like how `d` deletes, and `a` appends.

Motions are where the operator will operate on, like how `w` picks the word or `$` picks the end of the line.

(Grabbed from the Tutor itself)
A short list of motions:

- w - until the start of the next word, EXCLUDING its first character.
- e - to the end of the current word, INCLUDING the last character.
- $ - to the end of the line, INCLUDING the last character.

## 5. Combining commands

Because this is a language, you can combine commands to do specific things. The habit of using `count + operator + motion` is one of the main points of using Neovim.

For instance:

- 2w moves the cursor two words forward.
- 3e moves the cursor to the end of the third word forward.
- d2w deletes two words forward.
- 4dw deletes the four words forward. (yes the order doesn't matter)

### Undo commands

- u undo's previous actions
- U undo's all the changes on a line
- Ctrl + R undo's the undos

### Put command

- p puts previously deleted text after the cursor

The use of this is specific, but basically by storing the deleted line, you can quickly paste it somewhere using p.
This makes organizing orders like a), b), c), d) and moving and swapping them around a lot faster.

> Note: You can also put the text before the cursor with `P`

### Replace command

- rx replaces the character at the cursor with "x".

Very useful for some situations, but by itself it doesn't seem that powerful unless for minor fixes.

### The Change Operator

- ce deletes the word and places you on `INSERT MODE`

The change operator works in the same way as delete, thus, using the same motions.

- c$ erases everything forward from the point used, putting you in `INSERT MODE`

## 6. Navigating through the file

- C-g shows your location in a file and the file status.
- {count}G moves to line {count} in the file.
- G moves you to the bottom of the file.
- gg moves you to the start of the file.

### The Search Command

- / followed by a phrase will search for such phrase.
- To search for the same phrase again, type n.
- To search for the same phrase in the opposite direction, type n".
- To search for a phrase in the backward direction, use ? instead of /.
- To go back where you came from press C-o.
- For going forward instead, press C-i.

### Matching Parentheses Search

- % finds a matching ), ] or }.

This can be useful for debugging unmatching parentheses, but I'm not sure how often this would even happen, considering linters and formatters really help with that.

### The Substitute Command

- Typing `:s/old/new/g` substitutes "new" for "old".

Adding the g flag makes it change globally, so every occurrence of it. `:s/thee/the/g` would change every "thee"s found.

To change every occurrence of a character string between two lines, type `:#,#s/old/new/g`. # are the line numbers of the range of lines where the substitution is to be done (i.e., 1,3 means from line 1 to line 3, inclusive).

To change every occurrence in the whole file type `%s/old/new/g`. Adding a `c` at the end adds a prompt whether to substitute or not. `%s/old/new/g`.

## 7. Executing External Commands

- :! followed by an external command will execute it.

You can use any terminal commands this way, for example `:! ls` will show you a listing of your directory as if you were at your shell prompt rather than inside nvim. You can also include arguments. All ":" commands are executed once you press `ENTER`.

### More on Writing Files

- `:w FILENAME` saves changes made.
- `:!{unix:(ls),win:(dir)} shows your directory

:w TEST would save the current file under the name TEST. Using `:!{unix:(ls),win:(dir)} you can verify this. You can remove the file by typing :!{unix:(rm),win:(del)} TEST

- v motion :w FILENAME saves the visually selected lines in file
- :r FILENAME retrieves disk file FILENAME and puts it below the cursor position.

## 8. More ways to replace and fix text

- o opens a line BELOW the cursor, starting `INSERT MODE`.
- O does the same but above.

- a to insert text AFTER the cursor.
- A to insert text after the end of the line.

- e moves to the end of a word.
- y copies text, p pastes it.

- R enters `REPLACE MODE` until ESC is pressed.

- :set xxx sets the option xxx. Some options while searching are:
  - ic to ignore case
  - is to show partial matches
  - hls to highlight all matching

  > Long options also work:

  - ignorecase
  - incsearch
  - hlsearch

- :set noic switches an option off.
- :set invic inverts an option.

## 9. Getting Help

You can get help by pressing F1 and typing `:help`. Jump through windows with C-w. Close the help window with :q.

You can find help on any subject by giving an argument to the :help command.

- :help w
- :help c_CTRL-D
- :help insert-index
- :help user-manual

While in command mode, press C-d to see possible completions. Press Tab to use the completion menu and select a match.

We can make our config file to save our preferred settings by making an `init.lua` file and configuring it.

Nvim can be extended a lot more than this, `:help nvim-quickstart` shows a few of the options to make it a proper IDE. But it is also incentivized that you learn first and understand what you need, before using a premade distribution.
