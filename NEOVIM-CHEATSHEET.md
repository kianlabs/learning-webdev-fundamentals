# Neovim Cheat Sheet

**Learning Neovim alongside web development fundamentals.**

---

## Week 1: Survival Mode (Sept 3-9)

### Day 1-2: Basic Navigation & Editing

#### Modes
```
i       → Insert mode (start typing)
Esc     → Normal mode (navigate, command)
v       → Visual mode (select text)
V       → Visual line mode (select lines)
Ctrl-v  → Visual block mode (select columns)
:       → Command mode (type commands)
```

#### Navigation (Normal mode)
```
h       → Left
j       → Down
k       → Up
l       → Right

w       → Jump to next word
b       → Jump back one word
e       → Jump to end of word

0       → Start of line
$       → End of line
gg      → Top of file
G       → Bottom of file
5G      → Go to line 5

Ctrl-u  → Page up
Ctrl-d  → Page down
```

#### Editing
```
i       → Insert before cursor
a       → Insert after cursor
o       → Insert new line below
O       → Insert new line above

x       → Delete character
dd      → Delete line
yy      → Copy line
p       → Paste below
P       → Paste above

u       → Undo
Ctrl-r  → Redo
```

#### Save & Quit
```
:w      → Save
:q      → Quit
:wq     → Save & quit
:q!     → Quit without saving
:x      → Save & quit (shorter)
```

---

### Day 3-4: Search & Replace

#### Search
```
/pattern    → Search forward
?pattern    → Search backward
n           → Next match
N           → Previous match
*           → Search word under cursor forward
#           → Search word under cursor backward
```

#### Replace
```
:%s/old/new/g       → Replace all in file
:s/old/new/g        → Replace all in line
:%s/old/new/gc      → Replace with confirmation
```

#### Window Management
```
:split      → Horizontal split
:vsplit     → Vertical split
Ctrl-w h    → Move to left window
Ctrl-w j    → Move to down window
Ctrl-w k    → Move to up window
Ctrl-w l    → Move to right window
Ctrl-w q    → Close current window
```

---

### Day 5-7: Visual Mode & Macros

#### Visual Mode
```
v       → Visual mode (character selection)
V       → Visual line mode
Ctrl-v  → Visual block mode

d       → Delete selection
y       → Copy selection
c       → Change selection (delete and insert)
>       → Indent right
<       → Indent left
```

#### Macros
```
qa      → Start recording macro to register 'a'
q       → Stop recording
@a      → Play macro from register 'a'
@@      → Repeat last macro
```

#### Marks
```
ma      → Set mark 'a' at cursor
'a      → Jump to mark 'a'
'.      → Jump to last change
''      → Jump to previous position
```

---

## Week 2: Power User (Sept 10-16)

### Text Objects
```
ciw     → Change inner word
ci"     → Change inside quotes
ca{     → Change around curly braces
dit     → Delete inside HTML tag
yit     → Yank inside HTML tag
```

### Jump Navigation
```
f<char> → Jump forward to character
F<char> → Jump backward to character
t<char> → Jump forward before character
T<char> → Jump backward before character
;       → Repeat last f/F/t/T
,       → Repeat last f/F/t/T backward
```

### Registers
```
"ayy    → Copy line to register 'a'
"ap     → Paste from register 'a'
:reg    → Show all registers
"+y     → Copy to system clipboard
"+p     → Paste from system clipboard
```

### Buffers
```
:ls     → List all buffers
:b<n>   → Switch to buffer number n
:bn     → Next buffer
:bp     → Previous buffer
:bd     → Delete buffer
```

---

## Week 3-4: Customization (Sept 17-30)

### Config Files
- Neovim config: `~/.config/nvim/init.lua` or `~/.config/nvim/init.vim`
- Check current config: `:echo $MYVIMRC`

### Essential Settings (add to init.lua)
```lua
vim.opt.number = true           -- Show line numbers
vim.opt.relativenumber = true   -- Relative line numbers
vim.opt.tabstop = 2             -- Tab width
vim.opt.shiftwidth = 2          -- Indent width
vim.opt.expandtab = true        -- Use spaces instead of tabs
vim.opt.smartindent = true      -- Auto indent
vim.opt.wrap = false            -- No line wrap
vim.opt.ignorecase = true       -- Case insensitive search
vim.opt.smartcase = true        -- Case sensitive if uppercase used
vim.opt.hlsearch = false        -- No highlight search
vim.opt.incsearch = true        -- Incremental search
```

### Plugin Managers
- **lazy.nvim** (recommended)
- packer.nvim
- vim-plug

### Essential Plugins (to explore later)
- File explorer: nvim-tree, oil.nvim
- Fuzzy finder: telescope.nvim
- LSP: nvim-lspconfig
- Completion: nvim-cmp
- Syntax: nvim-treesitter
- Git: gitsigns.nvim

---

## Daily Practice Tips

1. **Force yourself**: No VSCode/other editors during learning hours
2. **One concept per day**: Don't overload
3. **Muscle memory**: Navigation shortcuts (h/j/k/l, w/b/e) become natural after 3-4 days
4. **Vimtutor**: Run `vimtutor` in terminal for interactive tutorial (30 mins)
5. **Keep this open**: Split screen with browser while coding

---

## Quick Reference Card (Print This)

```
MODES:           NAVIGATION:      EDITING:         SAVE/QUIT:
i  → Insert      h j k l          dd → Delete      :w  → Save
Esc → Normal     w b e            yy → Copy        :q  → Quit
v  → Visual      0 $ gg G         p  → Paste       :wq → Both
:  → Command     f<char> t<char>  u  → Undo        :q! → Force quit

SEARCH:          WINDOWS:         TEXT OBJECTS:
/pattern         :split :vsplit   ciw ci" ca{
n N              Ctrl-w h/j/k/l   dit yit
*  #             Ctrl-w q
```

---

## Resources

- **Vimtutor**: Run `vimtutor` in terminal (built-in interactive tutorial)
- **Vim Adventures**: vim-adventures.com (game to learn Vim)
- **Neovim docs**: `:help` in Neovim

---

**Remember:** Slow is smooth, smooth is fast. First week will feel slow — that's normal.
