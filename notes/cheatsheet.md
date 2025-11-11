# Cheatsheet

My personal cheatsheet for some really useful commands on Neovim.

## General Use

| Command | Description | Extended Use |
| :--- | :--- | :--- |
| `gggqG` | Formats the entire file based on `shiftwidth`. | `gq` is the format operator; `gqap` formats a paragraph. |
| `K` | Works as "mouse hover" over code (LSP documentation). | Use `k` to quit the hover mode. |
| `q` | Your general quitting keybind. | Only works if you've mapped it, otherwise use `:q`. |
| `ESC` | Used for going into **NORMAL MODE** from any other mode. | Essential for all Vim/Neovim interaction. |
| `.` | **Repeat** the last text-changing command (e.g., repeating a deletion, change, or append). | Extremely high-value productivity command. |
| `Ctrl-O` | Jump back to the **previous position** in the jump list (useful after a search or `gd`). | |
| `Ctrl-I` | Jump forward to the **next position** in the jump list. | |
| `*` or `#` | Search for the word under the cursor. | `*` searches forward, `#` searches backward. |
| `ciw` | **Change Inner Word**: deletes the word under the cursor and enters **Insert Mode**. | |
| `H` | High | Moves the cursor to the top-most line visible on the screen. |
| `M` | Middle | Moves the cursor to the line in the exact middle of the visible screen. |
| `L` | Low | Moves the cursor to the bottom-most line visible on the screen. |

## Autocompletion Keybinds (`nvim-cmp`)

| Keybind | Action | Description |
| :--- | :--- | :--- |
| `<C-n>` / `<C-p>` | **Navigate** | Go to the **Next** (`<C-n>`) or **Previous** (`<C-p>`) item. |
| `<CR>` (Enter) | **Confirm/Accept** | Confirms the selected item (or first item). |
| `<Tab>` | **Next Item / Snippet Jump** | Moves to the next item in the list or next placeholder in a snippet. |
| `<S-Tab>` | **Previous Item** | Moves to the previous item in the list. |
| `<C-y>` | **Confirm/Accept** | Traditional Vim keybind for accepting the selected completion. |
| `<C-e>` | **Abort** | Closes the completion menu without selecting. |
| `<C-Space>` | **Trigger** | Manually forces the completion menu to appear. |
| `<C-f>` / `<C-b>` | **Scroll Docs** | Scrolls **forward** (`<C-f>`) or **backward** (`<C-b>`) in the documentation window. |
