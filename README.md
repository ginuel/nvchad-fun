# 📱 Easy Termux & Neovim Coding Environment (`nvchad-fun`)

Turn your Android phone into a powerful, easy-to-use coding workstation! 

This project sets up a complete terminal coding environment on your phone. It gives you custom dark themes, extra touch-screen keys, a visual file manager, clipboard integration, and **Neovim** (a fast code editor).

---

## 🚀 Step 1: Install Termux Apps from GitHub

To make clipboard sharing and system tools work properly, install both **Termux** and **Termux:API** from GitHub Releases.

1. **Download Termux**: Go to [Termux GitHub Releases](https://github.com/termux/termux-app/releases), open **Assets**, and download the `.apk` file for your device (choose `...universal.apk` if unsure).
2. **Download Termux:API**: Go to [Termux:API GitHub Releases](https://github.com/termux/termux-api/releases), open **Assets**, and download the latest `.apk` file.
   > 🛑 **Warning**: Do **NOT** install Termux or Termux:API from the Google Play Store. The Play Store versions are outdated and broken!
3. Install both `.apk` files on your device.
4. Launch **Termux** once to initialize it.

---

## ⚡ Step 2: One-Line Automatic Setup

Open **Termux**, paste this command, and press **Enter**:

```bash
pkg install -y git && git clone https://github.com/diamond2sword/nvchad-fun ~/.config/nvim && source ~/.config/nvim/install.sh
```

Wait a few minutes while it installs and configures all your tools. Termux will automatically restart when complete!

---

## 📂 Where Should You Put Your Files?

Always create and keep your coding projects inside your **home folder** (`~`):

```bash
# Go to your home folder
cd ~

# Create a project folder (example: my-project)
mkdir my-project
cd my-project
```

> ⚠️ **Avoid** editing inside system configuration directories like `~/.config/` unless you intend to tweak your settings.

---

## 🐣 Terminal & Editing Basics

Before working with Git or writing code, learn these core commands in Termux:

### Essential Terminal Commands
* **`ls`**: List all files and folders in your current directory.
* **`cd <folder>`**: Change directory (e.g., `cd my-project`). Use `cd ~` to go home, or `cd ..` to go up one folder.
* **`touch <filename>`**: Create a new empty file (e.g., `touch index.html`).
* **`cat <filename>`**: Print the contents of a file directly in the terminal screen.

### Editing Files with Neovim (`vi` / `nvim`)
Neovim is your text editor. Open a file by typing `vi filename.txt` or `nvim filename.txt`.

* **Insert Mode (Typing)**: Press `i` to start typing text into the file.
* **Normal Mode (Command Mode)**: Press `Esc` (on the screen touch bar) to stop typing and enter command mode.
* **Save & Quit Options**:
  * `:w` + `Enter`: Save changes without quitting.
  * `:wq` + `Enter`: Save changes and quit Neovim.
  * `:q!` + `Enter`: Quit without saving changes.

---

## 🐙 Registering & Connecting Your GitHub Account

### Step 1: Configure Your Git Credentials
Set your global name and email (use the email attached to your GitHub account):

```bash
git config --global user.name "Your Real Name or Handle"
git config --global user.email "your.email@example.com"
```

### Step 2: Log in with GitHub CLI (`gh`)
Log in interactively using the official GitHub tool:

```bash
gh auth login
```
1. Select **GitHub.com**.
2. Select **HTTPS** as the preferred protocol.
3. Choose **Y** to authenticate Git credentials.
4. Select **Login with a web browser**, copy the displayed 8-character code, press Enter, and authorize it in your mobile browser.

---

## 🛠️ Working with Repositories & Git Workflow

### 1. Creating a Brand-New Repo & Pushing Code
If you created a new folder on your phone and want to publish it to GitHub:

```bash
# 1. Initialize Git in your folder
cd ~/my-project
git init

# 2. Create a file and commit it locally
touch README.md
git add .
git commit -m "Initial commit"

# 3. Create the remote repository on GitHub and push in one step
gh repo create my-project --public --source=. --remote=origin --push
```

### 2. General Day-to-Day Workflow (Making Changes)
Whenever you make updates to your files:

1. **Check status**: `git status` (shows changed files).
2. **Stage files**: `git add .` (prepares changes for saving).
3. **Commit changes**: `git commit -m "Explain what you changed here"`
4. **Push to GitHub**: `git push`

---

## 👥 How to Contribute to Projects

### Option A: As the Owner or a Direct Collaborator
If you own the repository or have write access added by the owner:

```bash
# Clone the repository to your phone
git clone https://github.com/username/repository-name.git
cd repository-name

# Make changes, then commit and push directly
git add .
git commit -m "Add new feature"
git push
```

### Option B: As a Visitor / Open-Source Contributor (Fork & PR)
If you don't have write permissions to someone else's repository:

1. **Fork and clone** the repo automatically using `gh`:
   ```bash
   gh repo fork owner-username/repository-name --clone
   cd repository-name
   ```
2. **Create a new branch** for your fix or feature:
   ```bash
   git checkout -b my-feature
   ```
3. **Edit files, commit changes, and push**:
   ```bash
   git add .
   git commit -m "Fix typo in documentation"
   git push -u origin my-feature
   ```
4. **Open a Pull Request (PR)**:
   ```bash
   gh pr create --title "Fix typo in documentation" --body "Describe your fix here"
   ```

---

## 🧰 Summary of Other Included Tools

* 📁 **`vifm`**: A visual file manager for browsing folders with file previews.
* 🚀 **`z <folder>`**: Jump straight to frequently visited directories.
* 🔍 **`fzf`**: Interactive file filter and search tool.

---

## 📄 License

Released into the public domain under [The Unlicense](./LICENSE).
