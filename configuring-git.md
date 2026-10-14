
# Git & GitHub Setup Guide for IntelliJ IDEA 2026

## Step 1: Configure Git Global Settings

Before connecting IntelliJ to GitHub, set your identity and default preferences in Git.

1. Open your terminal:
* **In IntelliJ:** Go to **View > Tool Windows > Terminal** (or press `Alt + F12` on Windows / `Option + F12` on macOS).
* **Outside IntelliJ:** Open your system Terminal (macOS) or Git Bash / Command Prompt (Windows).


2. Run the following commands line-by-line, **substituting your own name and email address**:

```bash
git config --global user.name "FIRST_NAME LAST_NAME"
git config --global user.email "my_name@example.com"
git config --global init.defaultBranch main
git config --global push.default current
git config --global push.autoSetupRemote true

```

> **Verify Settings:** Run `git config --list --global` to print your active settings and confirm your name, email, and branch settings are saved correctly.

---

## Step 2: Connect GitHub Account to IntelliJ IDEA

### Primary Method: Log In via Browser (Recommended)

1. Open IntelliJ IDEA settings:
* **Windows/Linux:** Go to **File > Settings** (or `Ctrl + Alt + S`).
* **macOS:** Go to **IntelliJ IDEA > Settings** (or `Cmd + ,`).


2. In the left navigation menu, expand **Version Control** and select **GitHub**.
3. Click the **`+`** (Add) icon near the top-right of the window and choose **Log In via GitHub...**.
4. A web browser window will open automatically:
* Click **Authorize in GitHub**.
* If prompted, sign in to your GitHub account.


5. Once authorized, return to IntelliJ. You will see your GitHub username and profile picture listed. Click **Apply**, then **OK**.

---

### Fallback Method: Log In with Token (If Browser Redirect Fails)

If the browser login page gets stuck, fails to redirect back to IntelliJ, or fails due to network/VPN restrictions, use a Personal Access Token instead.

#### A. Generate the Token on GitHub

1. Sign in to [github.com](https://github.com) in your browser.
2. Click your profile picture in the top-right corner and select **Settings**.
3. In the left sidebar, scroll down to the bottom and click **Developer settings**.
4. Navigate to **Personal access tokens > Tokens (classic)**.
5. Click **Generate new token** (select **Generate new token (classic)**).
6. Give your token a **Note** (e.g., `IntelliJ IDEA - Laptop`).
7. Check the following scopes/permissions:
* `repo` (Full control of private repositories)
* `workflow` (Update GitHub Action workflows)
* `read:org` (Read org and team membership)
* `gist` (Optionally create code gists)


8. Scroll to the bottom and click **Generate token**.
9. **Copy the token string immediately** (you will not be able to see it again after navigating away).

#### B. Add the Token to IntelliJ

1. Open IntelliJ Settings (**Version Control > GitHub**).
2. Click the **`+`** icon and select **Log In with Token...**.
3. Paste your generated token into the **Token** field.
4. Click **Generate / Save** or **Log In**. Click **Apply**, then **OK**.

---