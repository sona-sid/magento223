# magento223

=> Create new repository in Git interface to get the git url 'https://github.com/sona-sid/magento223.git'

	* Create a new repository on the command line
		echo "# testm2" >> README.md
		git init
		git add README.md
		git commit -m "first commit"
		git remote add origin https://github.com/sona-sid/magento223.git
		git push -u origin master

				Sometimes you may get the error as below: (this is because the SSH key is not generated or added to github)
					trusttech-12@trusttech-12:/var/www/html/magento223$ git push -u origin master
					git@github.com: Permission denied (publickey).
					fatal: Could not read from remote repository.

					Please make sure you have the correct access rights
					and the repository exists.

					=> TO DO: After you've checked for existing SSH keys, you can generate a new SSH key to use for authentication, then add it to the ssh-agent.

					step 1: Checking for existing SSH keys
						$ ls -al ~/.ssh
						# Lists the files in your .ssh directory, if they exist
							By default, the filenames of the public keys are one of the following:
							id_dsa.pub
							id_ecdsa.pub
							id_ed25519.pub
							id_rsa.pub

					step 2: Generating a new SSH key
						$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
						> Enter a file in which to save the key (/home/you/.ssh/id_rsa): [Press enter]  (or type another name if you want another file)
						> Enter passphrase (empty for no passphrase): [Type a passphrase]  (passpharse is a long password)

					step 3: Adding your SSH key to the ssh-agent
						$ eval "$(ssh-agent -s)"		(Start the ssh-agent in the background)
						> Agent pid 59566

						$ ssh-add ~/.ssh/id_rsa
							(Add your SSH private key to the ssh-agent. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.)

					step 4: Add the SSH key to your GitHub account.
						- Copy content of the ssh key file :
						$ gedit ~/.ssh/id_rsa.pub  ( to open the file with geditor )

						- Go to Github.com account
							> Settings > SSH and GPG Keys (or https://github.com/settings/keys )
							> Click 'New SSH Key' and paste the copied SSH key file content in the field Key.
							> In the "Title" field, add a descriptive label for the new key. (to denote the machine on which key used)

* push an existing repository from the command line
	git remote add origin https://github.com/sona-titech/testm2.git
	git push -u origin master
