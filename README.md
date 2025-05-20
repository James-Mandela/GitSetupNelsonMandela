# How to setup Git Bash on Mandela Lab Pcs
##Clone This Repo
open git bash on the lab pc.
Go to the home directory by typing in this command:
```
cd
```
Then Clone this repo by typing:
```
https://github.com/James-Mandela/GitSetupNelsonMandela.git
```
> Remember if you want to paste something in git bash you use Shift+Insert
##Moving the .ssh File to Home directory
```
cp -r GitSetupNelsonMandela/.ssh .
```
##Generating ssh Keys
Now we need to generate your ssh keys and register them with the system.
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f $HOME/.ssh/YourKeyName
```
You should be prompted for a password just hit Enter twice
Two files will be generated a private key called "YourKeyName" and a public key called "YourKeyName.pub".
Git uses these keys to communicate securely with your remote repo host, in this case github. 

Your computer is not aware of these so we going to have to register them.
Firstly we need to make sure the ssh-agent is running in the back ground.
```
eval "$(ssh-agent -s)"
```
Next we're going to give the ssh-agent your private key:
```
ssh-add ~/.ssh/YourKeyName
```
Alrighty! Now we need to copy the public key and paste it in your GitHub profile
Firstly lets make sure we are the ".ssh" directory:
```
cd $HOME/.ssh/
```
Next lets open your public key with notepad
```
start notepad YourKeyName.pub
```
Copy the public key
##Adding the Public Key to Github
If you not already, sign into Github.
Next Click on your profile, its at top right
Click Settings.
On the Left-hand side click "SSH and GPG keys"
Click "New SSH Key"
Paste in your key, give it a title and then click "Add SSH Key"
BOOM you are now done.
>Remember to use the ssh option when cloning repo's and not the HTTPS one.
