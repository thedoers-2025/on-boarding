# How to Create SSH Keys and Add to GitHub Profile

## 1. Generate SSH Key Pair

Open your terminal and run:
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
- Press Enter to accept the default file location.
- Set a passphrase (optional).

## 2. Add SSH Key to SSH Agent

Start the SSH agent:
```bash
eval "$(ssh-agent -s)"
```
Add your SSH private key:
```bash
ssh-add ~/.ssh/id_ed25519
```

## 3. Copy Public Key

Copy your public key to clipboard:
```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

## 4. Add SSH Key to GitHub

- Go to [GitHub SSH keys settings](https://github.com/settings/keys).
- Click **New SSH key**.
- Paste your key and give it a title.
- Click **Add SSH key**.

## 5. Test SSH Connection

Run:
```bash
ssh -T git@github.com
```
You should see a success message.

## 6. Clone Repositories Using SSH

Use the SSH URL from GitHub (e.g., `git@github.com:username/repo.git`):
```bash
git clone git@github.com:username/repo.git
```

**You can now clone, pull, and push to all your GitHub repositories using SSH.**