# 8. Command Line Editing

- Emacs-style commands (vi-style available)
  - `$ set -o emacs`
  - `$ set -o vi`
- Editing enabled by default unless the 'noediting' option is given to the shell
  at invokation.
  - `$ bash --noediting`
- Uses the Readline library
- The bash 'read' built-in also uses line editing (Readline) when given option
  '-e'
  1. `$ read -e`
  2. `$ echo $REPLY`

## [8.4 Bindable Readline Commands](https://www.gnu.org/software/bash/manual/bash.html#Bindable-Readline-Commands)

The Bash manual has a very comprehensive list of commands and default
keybindings in sections 8.4.1-8.4.8.

```bash
# list keybindings
$ bind -P
```

### [8.4.1 Commands For Moving](https://www.gnu.org/software/bash/manual/bash.html#Commands-For-Moving)

| Key Binding | Description     |
| :---------- | :-------------- |
| C-a         | Start of line   |
| C-e         | End of line     |
| C-f         | Forward         |
| M-f         | Forward a word  |
| C-b         | Back            |
| M-b         | Backward a word |

_**Note: M (Meta), by loose convention, operates on words, not individual
characters.**_

### [8.4.2 Commands For Manipulating The History](https://www.gnu.org/software/bash/manual/bash.html#Commands-For-History)

There are two types of search modes: incremental and non-incremental. The
'isearch-terminators' variable is used to set the incremental search termination
character.

| Key Binding                             | Description                                        |
| :-------------------------------------- | :------------------------------------------------- |
| C-r                                     | Search history backwards                           |
| C-s                                     | Search history forwards                            |
| C-r C-r                                 | The last incremental search string                 |
| Incremental search + "movement command" | Terminates and moves cursor                        |
| RET                                     | Terminate and execute                              |
| ESC                                     | Terminate incremental search                       |
| C-J                                     | Terminate incremental search                       |
| C-g                                     | Abort incremental search and restore original line |

### [8.4.3 Commands For Changing Text](https://www.gnu.org/software/bash/manual/bash.html#Commands-For-Text)

| Key Binding | Description |
| :---------- | :---------- |
| C-d         | Delete      |
| C-_         | Undo        |
| C-x C-u     | Undo        |

### [8.4.4 Killing and Yanking](https://www.gnu.org/software/bash/manual/bash.html#Commands-For-Killing) (Cut and Paste)

| Key Binding | Description                   |
| :---------- | :---------------------------- |
| C-k         | Delete to end of line         |
| M-d         | Delete to end of word         |
| M-DEL       | Delete to start of word       |
| C-w         | Delete to previous whitespace |
| C-y         | Paste                         |
| M-y         | Rotate kill-ring              |

### [8.4.5 Specifying Numeric Arguments](https://www.gnu.org/software/bash/manual/bash.html#Numeric-Arguments)

You can pass numeric arguments to Readline commands. Meta key plus first number
charater initiates the start of the number. Following digits don't require the
meta key to be pressed. Finally, the command can be entered. Below, is an
example that illustrates this with the C-d command.

| Key Binding                  | Description                      |
| :--------------------------- | :------------------------------- |
| M-:digit: [:digit:]* command | Pass numeric argument to command |
| M-1 0 C-d                    | Deletes next 10 characters       |
