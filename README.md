
# Here you will  know how to connect your github repository with cpanel.

### 1- Generate an SSH Key

Open the terminal in cPanel or your local machine.
Run the following command to generate a new SSH key:

 `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

Replace your_email@example.com with the email address associated with your GitHub account.
When prompted:
Press Enter to save the key in the default location (~/.ssh/id_rsa).
Optionally, set a passphrase for added security (or leave it blank for no passphrase).
### 2- View and Copy the Public Key
Display the public key:

`cat ~/.ssh/id_rsa.pub`

Copy the entire output (it starts with ssh-rsa).

### 3- Add the Public Key to GitHub
Log in to your GitHub account.
Go to Settings (click your profile picture in the top-right corner and select Settings).
In the left sidebar, click SSH and GPG keys.
Click New SSH Key.
Add a title (e.g., "cPanel Key" or "My Server Key") and paste the public key you copied.
Click Add SSH Key.

### 4- Test the SSH Connection
In the terminal, test the connection to GitHub:

 `ssh -T git@github.com`

If successful, you should see a message like:

D- `Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.`

### 5- Clone a Repository
Now that the SSH key is set up, you can clone a GitHub repository:

`cd ~/public_html`

Navigate to the directory where you want to clone the repository:

Clone the repository using SSH:

` git clone git@github.com:<username>/<repository>.git`

Replace <username> with your GitHub username and <repository> with the repository name.

