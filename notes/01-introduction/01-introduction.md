# I - Introduction

## 1. Why use Neovim 

- Open-source text editor
- In-depth customization to serve your exact developer needs

## 2. Installing Neovim

[Neovim Documentation](https://neovim.io/doc/)

> This video recommends building it from source.

## 3. Getting started

We'll be making an example file to practice nvim.

```
# If on WSL, we'll have to create the .config directory first
cd
mkdir -p ~/.config/nvim
```
```
cd .config
mkdir nvimexample
cd nvimexample
NVIM_APPNAME=nvimexample nvim init.lua
```

## 4. Neovim Modes

As a brief introduction:

- PRESS I to enter INSERT MODE
- PRESS V to enter VISUAL MODE
- PRESS ESC to enter NORMAL MODE

Once you're done you might notice a [+] on the bottom. Which means you have changes that haven't been saved.

## 5. Saving

To save we will need to go into `NORMAL MODE` by pressing `ESCAPE`.

Then `SHIFT + :`.

Type `w` to write. Which will save the changes.

Then `qa` to quit.

We can also use `dd` to delete an entire line.

## 6. Running code

> From now on I will be referencing the `SHIFT + :` command as simply ":"

By typing `:source %`, % is a placeholder and means to be everything inside such file. That means it will run the file iteratively (top to bottom). When running the file, if you have a `print()` statement for example, you will see its output at the very bottom.

Now, if we select a `VISUAL LINE` by pressing `SHIFT + V`, proceeded by a :lua, we will run the code ONLY on those lines we chose, rather than the entire file.

Another way to run code is to make a function

`MyCoolFunction = function() print "hello" end`

Then do :lua MyCoolFunction(). That would also print `hello`
