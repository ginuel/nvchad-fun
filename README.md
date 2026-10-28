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

Open **Termux**, paste this command to update your system packages and run the setup, then press **Enter**:

```bash
pkg update && pkg upgrade -y && pkg install -y git && git clone https://github.com/diamond2sword/nvchad-fun ~/.config/nvim && source ~/.config/nvim/install.sh
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

## 📋 Copying & Pasting in Termux and Neovim

Your setup includes helper functions and extra touch keys to easily copy and paste text.

### 1. Copying & Pasting in Termux (Outside Neovim)
* **To Copy text from Termux to your phone clipboard**: 
  1. Long-press anywhere on the screen in Termux to select text.
  2. Tap **Copy** from the popup menu.
  * *(Alternative)*: You can also use commands directly in your terminal:
    * `termux-clipboard-set "Hello from Termux"` (copies text to phone clipboard).
    * `termux-clipboard-get` (prints out what's currently in your phone clipboard).
* **To Paste text from your phone clipboard into Termux**: 
  1. Long-press anywhere on the command line.
  2. Tap **Paste**. *(Alternatively, use your extra-keys toolbar and tap **`CTRL`** + **`V`** or **`SHIFT`** + **`INSERT`**)*.

### 2. Copying & Pasting Inside Neovim
If you want to copy code blocks or lines inside Neovim:
1. Press `v` to enter visual mode, highlight your text, and press **`CTRL`** + **`C`** to copy the selection directly to your Android system clipboard.
2. To paste system clipboard text into Neovim, press **`CTRL`** + **`V`** while in insert mode (`i`).

---

## 📑 Managing Termux Tabs (Sessions)

When coding, you will want one tab to edit your code and another tab to run your live website server. 

1. **Open the Session Drawer**: Swipe your finger **from the left edge of your phone screen toward the right**. A menu panel will slide out.
2. **Create a New Tab**: Tap the **`NEW SESSION`** button at the top of the menu.
3. **Switch Between Tabs**: Swipe from the left edge again and select whichever session you want to view (e.g., Session 1 for editing, Session 2 for running your server).

---

## 🌐 Running Your Website Locally & Viewing It

Thanks to your setup, you can easily host and view your websites directly on your phone using your mobile web browser (like Chrome or Firefox).

### 1. Vanilla HTML / JavaScript Websites
If your project is a standard static website (containing `index.html`):

1. Open a Termux tab and go to your project folder:
   ```bash
   cd ~/my-project
   ```
2. Start a simple Python web server on port `8000`:
   ```bash
   python3 -m http.server 8000
   ```
3. Open your mobile browser and go to:
   **`http://localhost:8000`**

### 2. PHP Websites
If your website uses PHP files (e.g., `index.php`), PHP is already pre-installed via your setup script:

1. Open a Termux tab and go to your project folder:
   ```bash
   cd ~/my-project
   ```
2. Start the built-in PHP server on port `8080`:
   ```bash
   php -S localhost:8080
   ```
3. Open your mobile browser and go to:
   **`http://localhost:8080`**

> 💡 **Tip**: Leave that tab running in the background! Use your **second Termux tab** to continue editing files in Neovim (`nvim index.html`), and refresh your browser page to see your live updates instantly.

---

## 🐙 Registering & Connecting Your GitHub Account

### Step 1: Configure Your Local Git Credentials
Set your global username and email address (use the email linked to your GitHub account):

```bash
git config --global user.name "Your Real Name or Handle"
git config --global user.email "your.email@example.com"
```

### Step 2: Interactive Browser Login using GitHub CLI (`gh`)
Run the following command to begin authentication:

```bash
gh auth login
```

Follow each terminal prompt step-by-step:

1. **What account do you want to log into?**  
   Select **`GitHub.com`** and press **Enter**.
2. **What is your preferred protocol for Git operations?**  
   Select **`HTTPS`** and press **Enter**.
3. **Authenticate Git with your GitHub credentials?**  
   Select **`Y`** (Yes) and press **Enter**.
4. **How would you like to authenticate GitHub CLI?**  
   Select **`Login with a web browser`** and press **Enter**.

#### Completing Browser & Code Authorization:
1. Terminal will show a message similar to:  
   `! First copy your one-time code: XXXX-XXXX`
2. **Copy the 8-character code** shown on your screen (e.g., `A1B2-C3D4`).
3. Press **Enter** to launch your mobile browser, or manually open [github.com/login/device](https://github.com/login/device).
4. Paste the **8-character code** into the browser box and tap **Continue**.
5. Tap **Authorize github** to give Termux access to your repositories.
6. Return to Termux. You will see:  
   `✓ Authentication complete.`

---

## 🔄 Switching GitHub Accounts

If you ever need to change your GitHub accounts or re-authenticate, go to your config directory and run `./git.bash login`:

```bash
cd ~/.config/nvim
./git.bash login
```

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
