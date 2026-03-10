# 🐧 Core Linux & Vim Skills (Cloud Dev / K8s Essentials)

## 1. Linux Command Line Refresher
When managing Kubernetes (minikube) or AWS EC2 instances, these commands are essential for navigating the system and debugging.

| Command | Purpose | Real-world Example |
| :--- | :--- | :--- |
| `ls -la` | List all files (including hidden and permissions) | Check `.kube` or `.ssh` directories |
| `chmod 400` | Change file permissions (Read-only) | Set permissions for AWS `.pem` keys |
| `grep` | Filter text/search for keywords | `kubectl get pods \| grep "Error"` |
| `tail -f` | Follow file output in real-time | Monitor system logs or container logs |
| `curl -I` | Fetch HTTP headers only | Check if a Load Balancer (ALB) is alive |
| `>` / `>>` | Redirect output (Overwrite / Append) | `k get pod -o yaml > pod.yaml` |
| `\|` (Pipe) | Pass output of one command to another | `cat log.txt \| grep "fail" \| wc -l` |

---

## 2. Vim Editor Essentials
Since YAML files **prohibit the use of Tab keys** and require strict indentation, mastering Vim is non-negotiable for Cloud Engineers.

### A. Mode Switching
* **Normal Mode:** Press `Esc`. Used for navigation, deleting, and copying.
* **Insert Mode:** Press `i` (insert at cursor) or `o` (open new line below and insert).
* **Command Mode:** Press `:`. Used for saving, quitting, and settings.

### B. Navigation (Normal Mode)
* `h` `j` `k` `l`: Left, Down, Up, Right.
* `gg`: Jump to the first line of the document.
* `G`: Jump to the last line of the document.
* `0`: Jump to the start of the current line.
* `$`: Jump to the end of the current line.
* `/keyword`: Search for text (Press `n` to find the next occurrence).

### C. Editing & History (Normal Mode)
* `dd`: Delete (cut) the entire line.
* `yy`: Yank (copy) the entire line.
* `p`: Paste the copied/cut text.
* **`u`**: **Undo (The most important command!)**
* `Ctrl + r`: Redo the last undone action.
* `x`: Delete a single character.

### D. Saving & Exiting (Command Mode)
* `:w`: Save (write) the file.
* `:wq`: Save and quit.
* `:q!`: Force quit without saving.
* `:set nu`: Show line numbers (essential for finding YAML syntax errors).

---

## 3. Optimizing Vim for YAML
To prevent indentation issues, it is highly recommended to configure your Vim environment. Run `vim ~/.vimrc` and add these lines:

```vim
" Enable line numbers
set number
" Convert Tabs to Spaces (Essential for YAML)
set expandtab
" Set indentation to 2 spaces
set shiftwidth=2
set softtabstop=2
" Enable auto-indentation
set autoindent.