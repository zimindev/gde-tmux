## 🧭 Tmux Setup Guide

### ✅ What is Tmux?

**Tmux** (Terminal Multiplexer) lets you manage multiple terminal sessions in one window. You can split panes, detach and reattach sessions, and work more efficiently from the terminal.

---

### 🖥️ Step 1: Install Tmux

#### **Debian/Ubuntu:**

```bash
sudo apt install tmux
```

#### **Arch Linux:**

```bash
sudo pacman -S tmux
```

#### **Fedora:**

```bash
sudo dnf install tmux
```

#### **macOS (Homebrew):**

```bash
brew install tmux
```

#### **Windows:**

Use [WSL](https://learn.microsoft.com/en-us/windows/wsl/) (Windows Subsystem for Linux) and install tmux inside your WSL distro.

---

### 🚀 Step 2: Start Tmux

To start a new session:

```bash
tmux
```

To start a session with a name:

```bash
tmux new -s mysession
```

---

### 🔁 Step 3: Detach & Reattach Sessions

* Detach from current session:

  ```
  Ctrl + b, then d
  ```

* List all sessions:

  ```bash
  tmux ls
  ```

* Reattach to a session:

  ```bash
  tmux attach -t mysession
  ```

---

### 🪟 Step 4: Split Windows & Panes

* **Horizontal split:**

  ```
  Ctrl + b, then "
  ```

* **Vertical split:**

  ```
  Ctrl + b, then %
  ```

* **Switch between panes:**

  ```
  Ctrl + b, then arrow key
  ```

* **Resize panes:**
  Press `Ctrl + b`, then hold `Ctrl` and use arrow keys.

---

### 📁 Step 5: Manage Windows (Tabs)

* **New window:**

  ```
  Ctrl + b, then c
  ```

* **Next window:**

  ```
  Ctrl + b, then n
  ```

* **Previous window:**

  ```
  Ctrl + b, then p
  ```

* **Rename window:**

  ```
  Ctrl + b, then ,
  ```

---

### ⚙️ Step 6: Tmux Configuration

Create a `.tmux.conf` file in your home directory:

```bash
nano ~/.tmux.conf
```

Example config:

```bash
# Use vim-style keybindings
setw -g mode-keys vi

# Set prefix from Ctrl+b to Ctrl+a (optional)
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix

# Mouse support
set -g mouse on

# Better status bar
set -g status-bg colour235
set -g status-fg colour136
```

Apply changes without restarting:

```bash
tmux source-file ~/.tmux.conf
```

---

### 🎨 Bonus: Tmux Plugin Manager (TPM)

Install [TPM](https://github.com/tmux-plugins/tpm) to manage tmux plugins:

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Add this to the bottom of your `.tmux.conf`:

```bash
# Tmux Plugin Manager
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Initialize TPM
run '~/.tmux/plugins/tpm/tpm'
```

Reload config and press `Ctrl + b`, then `I` (capital i) to install plugins.

---

### 📚 Additional Resources

* GitHub: [https://github.com/tmux/tmux](https://github.com/tmux/tmux)
* TPM (Plugin Manager): [https://github.com/tmux-plugins/tpm](https://github.com/tmux-plugins/tpm)
* Cheatsheet: [https://tmuxcheatsheet.com/](https://tmuxcheatsheet.com/)
* Guide for `.tmux.conf`: [https://github.com/gpakosz/.tmux](https://github.com/gpakosz/.tmux)
