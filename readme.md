md -> markdown
# Git_commands
1. cd -> change directory
2. push -> to add a file/change
3. commit -> save a file
4. pull -> download a file
5. git add . -> include all the files
6. git status -> check file status
7. git push -> push to git repo

# Creating a SSH Git key
✅ Step 1 — Create the .ssh directory
Run:
mkdir -p ~/.ssh
chmod 700 ~/.ssh

✅ Step 2 — Generate a new SSH key
Choose the key name you want.
If you want to name it gitkey:
ssh-keygen -t ed25519 -f ~/.ssh/gitkey -C "your_email@example.com"
Press Enter for passphrase (or add one if you want).

✅ Step 3 — Add it to the macOS keychain
ssh-add --apple-use-keychain ~/.ssh/gitkey

✅ Step 4 — Update your SSH config
Edit (or create) ~/.ssh/config:
nano ~/.ssh/config
Add:
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/gitkey
If macOS complains about UseKeychain, add:
  IgnoreUnknown UseKeychain

🛑 To exit nano:
Press
Ctrl + X
Nano will ask:
Save modified buffer? (Y/N)
If you want to save:
Press:
Y
Then it will ask for a filename — just press:
Enter

✅ If you're using the Terminal
Run:
ls -la ~
This shows all files, including hidden ones.
Look for a folder named:
.ssh
If you want to go into it:
cd ~/.ssh

Then list its contents:
ls -la

ls | grep gitkey
cat gitkey.pub

// to copy the key to clipboard
pbcopy < ~/.ssh/gitkey.pub 
