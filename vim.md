# VIM cheat sheet

> My VIM cheat sheet to handle interaction in terminal. Make sure the syntax highlighting is already enabled in your .vimrc to have a better user experience.

## Menu
- [iTerm](#iTerm)
- [General](#general)
- [Editing](#editing)

## iTerm

#### move cursor with mouse click

```sh
option + click
```

#### search in your command history and auto complete

```sh
control + r
```

__Tip:__ to cancel the search, just press `control + k`

## General

#### Quit the terminal

```sh
:q
```

#### Quit the terminal in case you did some changes and want to discard these changes.

```sh
:q!
```

#### Enter edit mode

```sh
i
```

## Editing

#### Delete(cut) a line (non edit mode)

```sh
dd
```

#### Copy(yank) a line (non edit mode)

```sh
y
```

#### Paste the line or previous copied visual (non edit mode)

```sh
p
```

#### Select text you want to copy and paste (non edit mode)

```sh
v
```

__Tip:__ use `y` to copy the visual selection or `d` to cut it.
